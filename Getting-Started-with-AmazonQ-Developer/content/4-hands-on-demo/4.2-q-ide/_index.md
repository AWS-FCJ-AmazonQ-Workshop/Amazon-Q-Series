---
title: "Building and Deploying a Sample Application on IDE"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

In this section, we will use Amazon Q Developer to build a complete BMI Calculator application. The app is written in TypeScript, uses the Hono framework, and is deployed on AWS Lambda.

#### Application Overview

The BMI Calculator API includes the following endpoints:
- GET `/healthcheck` - check system status
- GET `/bmi-calculator?gender={gender}&height={height}&weight={weight}` - calculate BMI

{{% notice note %}}
Reference source code: https://github.com/AWS-FCJ-AmazonQ-Workshop/bmi-calculator
{{% /notice %}}

#### Step 1: Set up environment and project

##### 1.1 Create project directory
```bash
mkdir bmi-calculator-app
cd bmi-calculator-app
```

##### 1.2 Initialize Node.js project
```bash
npm init -y
```

##### 1.3 Create the app with Amazon Q Developer

Open VS Code in the project folder and use Amazon Q Developer:

```
/dev Create a BMI Calculator application using TypeScript with Hono framework. 
Expose API GET "/healthcheck" and "/bmi-calculator?gender={gender}&height={height}&weight={weight}"
```

{{% notice tip %}}
Amazon Q Developer will automatically generate the project structure and necessary files.
{{% /notice %}}

##### 1.4 Check the generated project structure

After Amazon Q completes, you will have a structure like:
```
bmi-calculator-app/
├── package.json
├── tsconfig.json
├── src/
│   └── index.ts
└── node_modules/
```

##### 1.5 Review generated package.json

```json
// package.json
{
  "name": "bmi-calculator",
  "version": "1.0.0",
  "scripts": {
    "dev": "tsx src/index.ts",
    "build": "tsc",
    "start": "node dist/index.js"
  },
  "dependencies": {
    "hono": "^3.12.0"
  },
  "devDependencies": {
    "@types/node": "^20.0.0",
    "tsx": "^4.0.0",
    "typescript": "^5.0.0"
  }
}
```

##### 1.6 Install dependencies

```bash
npm install
```

#### Step 2: Review the generated code

##### 2.1 Check src/index.ts

```typescript
// src/index.ts
import { Hono } from 'hono'
import { handle } from 'hono/aws-lambda'

const app = new Hono()

app.get('/healthcheck', (c) => {
  return c.json({ status: 'OK', timestamp: new Date().toISOString() })
})

app.get('/bmi-calculator', (c) => {
  const { gender, height, weight } = c.req.query()
  const h = parseFloat(height), w = parseFloat(weight)
  
  if (!height || !weight || isNaN(h) || isNaN(w) || h <= 0 || w <= 0) {
    return c.json({ error: 'Invalid parameters' }, 400)
  }
  
  const bmi = w / (h * h)
  const category = bmi < 18.5 ? 'Underweight' : bmi < 25 ? 'Normal' : bmi < 30 ? 'Overweight' : 'Obese'
  
  return c.json({ bmi: Math.round(bmi * 100) / 100, category, gender, height: h, weight: w })
})

export const handler = handle(app)
```

##### 2.2 Test the app locally

```bash
npm run dev
```

Open your browser and visit:
- `http://localhost:3000/healthcheck`
- `http://localhost:3000/bmi-calculator?height=1.75&weight=70&gender=male`

#### Step 3: Create unit tests

##### 3.1 Ask Amazon Q to generate unit tests

Use the `/test` command in Amazon Q Developer:

```
/test Create unit tests for BMI Calculator application
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-1.png?width=90pc)

*Figure 1: Generate unit tests for BMI Calculator*

##### 3.2 Install testing dependencies

Amazon Q will add the necessary dependencies to package.json:

```bash
npm install --save-dev vitest @vitest/ui
```

##### 3.3 Review generated unit tests

```typescript
// tests/index.test.ts
import { describe, it, expect } from 'vitest'
import app from '../src/index'

describe('BMI Calculator', () => {
  it('should return health check', async () => {
    const res = await app.request('/healthcheck')
    expect(res.status).toBe(200)
    const data = await res.json()
    expect(data.status).toBe('OK')
  })

  it('should calculate BMI correctly for normal weight', async () => {
    const res = await app.request('/bmi-calculator?height=1.75&weight=70&gender=male')
    expect(res.status).toBe(200)
    const data = await res.json()
    expect(data.bmi).toBeCloseTo(22.86, 2)
    expect(data.category).toBe('Normal')
  })

  it('should return error for invalid parameters', async () => {
    const res = await app.request('/bmi-calculator?height=invalid&weight=70')
    expect(res.status).toBe(400)
    const data = await res.json()
    expect(data.error).toBe('Invalid parameters')
  })
})
```

##### 3.4 Add test script to package.json

```json
{
  "scripts": {
    "test": "vitest",
    "test:ui": "vitest --ui"
  }
}
```

##### 3.5 Run unit tests

```bash
npm test
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-2.png?width=90pc)

*Figure 2: Run unit tests*

#### Step 4: Prepare for AWS deployment

##### 4.1 Install AWS CDK

```bash
npm install -g aws-cdk
npm install --save-dev aws-cdk-lib constructs
```

##### 4.2 Initialize CDK project

```bash
cdk init --language typescript
```

##### 4.3 Ask Amazon Q to generate CDK stack

```
/dev Create AWS CDK stack to deploy Lambda function with Function URL for BMI Calculator
```

##### 4.4 Review generated CDK stack

```typescript
// lib/bmi-stack.ts:
import * as cdk from 'aws-cdk-lib'
import * as lambda from 'aws-cdk-lib/aws-lambda'
import * as nodejs from 'aws-cdk-lib/aws-lambda-nodejs'
import { Construct } from 'constructs'

export class BmiStack extends cdk.Stack {
  constructor(scope: Construct, id: string, props?: cdk.StackProps) {
    super(scope, id, props)

    const bmiFunction = new nodejs.NodejsFunction(this, 'BmiFunction', {
      entry: 'src/index.ts',
      handler: 'handler',
      runtime: lambda.Runtime.NODEJS_18_X,
      bundling: { 
        minify: true,
        externalModules: ['aws-sdk']
      }
    })

    const functionUrl = bmiFunction.addFunctionUrl({
      authType: lambda.FunctionUrlAuthType.NONE,
      cors: { 
        allowedOrigins: ['*'], 
        allowedMethods: [lambda.HttpMethod.GET] 
      }
    })

    new cdk.CfnOutput(this, 'FunctionUrl', { 
      value: functionUrl.url,
      description: 'BMI Calculator API URL'
    })
  }
}
```

##### 4.5 Update CDK app

```typescript
// bin/bmi-calculator.ts:
import 'source-map-support/register'
import * as cdk from 'aws-cdk-lib'
import { BmiStack } from '../lib/bmi-stack'

const app = new cdk.App()
new BmiStack(app, 'BmiCalculatorStack', {
  env: {
    account: process.env.CDK_DEFAULT_ACCOUNT,
    region: process.env.CDK_DEFAULT_REGION,
  },
})
```

#### Step 5: Deploy to AWS

##### 5.1 Configure AWS credentials

Make sure AWS CLI is configured:
```bash
aws configure
```

##### 5.2 Bootstrap CDK (run once)

```bash
cdk bootstrap
```

##### 5.3 Build and deploy

```bash
npm run build
cdk deploy
```

{{% notice warning %}}
Deployment may take 2-3 minutes. Confirm when CDK asks about creating IAM resources.
{{% /notice %}}

##### 5.4 Check deployment result

After successful deployment, you will see output:
```
BmiCalculatorStack.FunctionUrl = https://xxxxxxxx.lambda-url.us-east-1.on.aws/
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-3.png?width=90pc)
*Figure 3: Successfully deployed AWS Lambda Stack*

##### 5.5 Test API on AWS

```bash
# Test healthcheck
curl "https://your-function-url/healthcheck"

# Test BMI calculator
curl "https://your-function-url/bmi-calculator?height=1.75&weight=70&gender=male"
```

#### Step 6: Generate documentation

##### 6.1 Ask Amazon Q to generate documentation

```
/doc Generate API documentation for BMI Calculator with healthcheck and bmi-calculator endpoints
```

##### 6.2 Documentation is generated automatically

Documentation is generated automatically, content in **README.md:**

#### Step 7: Code review and quality check

##### 7.1 Use Amazon Q to review code

```
/review Check code quality and security for BMI Calculator
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-4.png?width=30pc)
*Figure 4: Review code quality*

##### 7.2 Automated review checklist:
- ✅ **Input validation**: Check input parameters
- ✅ **Error handling**: Proper error handling  
- ✅ **Type safety**: Use TypeScript types
- ✅ **Test coverage**: Full unit test coverage
- ✅ **Security**: Follow security best practices
- ✅ **Performance**: Code is optimized

##### 7.3 Run quality checks

```bash
# Run tests
npm test

# Build to check TypeScript errors
npm run build

# Lint code (if ESLint is set up)
npm run lint
```

#### Step 8: Clean up resources

##### 8.1 Delete AWS resources

```bash
cdk destroy
```

##### 8.2 Confirm deletion

Type `y` to confirm deleting the CloudFormation stack and all resources.

#### Lab summary

After completing this lab, you have successfully:

1. **✅ Created a project from scratch** with Amazon Q Developer using `/dev`
2. **✅ Developed the BMI Calculator API** with TypeScript and Hono framework
3. **✅ Written and run unit tests** automatically with `/test`
4. **✅ Deployed to AWS Lambda** with CDK infrastructure as code
5. **✅ Generated documentation** automatically with `/doc`
6. **✅ Reviewed code quality** with `/review`
7. **✅ Tested production API** on AWS Lambda Function URL

#### Knowledge gained

- **Amazon Q Developer commands**: `/dev`, `/test`, `/doc`, `/review`
- **TypeScript development**: Type safety, modern JavaScript
- **Hono framework**: Lightweight web framework for Edge/Lambda
- **AWS CDK**: Infrastructure as Code with TypeScript
- **AWS Lambda**: Serverless function deployment
- **Unit testing**: Vitest framework and test automation
- **API development**: RESTful API design and best practices

{{% notice tip %}}
**Tip for real projects**: Amazon Q Developer can help you implement all the above extensions with simple prompts!
{{% /notice %}}

Amazon Q Developer helps accelerate the entire development process from project initialization to production deployment efficiently and professionally.
