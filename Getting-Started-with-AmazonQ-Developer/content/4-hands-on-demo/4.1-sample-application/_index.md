---
title: "Building and Deploying a Sample Application"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

In this section, we will use Amazon Q Developer to build a complete BMI Calculator application. The app is written in TypeScript, uses the Hono framework, and is deployed on AWS Lambda.

#### Application Overview

The BMI Calculator API includes the following endpoints:
- GET `/healthcheck` - system health check
- GET `/bmi-calculator?gender={gender}&height={height}&weight={weight}` - calculate BMI

{{% notice note %}}
Reference source code: https://github.com/AWS-FCJ-AmazonQ-Workshop/bmi-calculator
{{% /notice %}}

#### Step 1: Create the application with /dev

Use Amazon Q Developer with the `/dev` command to create the application:

```
/dev Create a BMI Calculator application using TypeScript with Hono framework. 
Expose API GET "/healthcheck" and "/bmi-calculator?gender={gender}&height={height}&weight={weight}"
```

##### Main generated code:

**package.json:**
```json
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

**src/index.ts:**
```typescript
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

#### Step 2: Create unit tests with /test

Use the `/test` command to generate unit tests:

```
/test Create unit tests for BMI Calculator application
```

![alt text](/images/4-hands-on-demo/4.1-sample-application/image-1.png?width=90pc)

*Figure 1: Generate unit tests for BMI Calculator*

##### Generated unit tests:
```typescript
import { describe, it, expect } from 'vitest'
import app from '../src/index'

describe('BMI Calculator', () => {
  it('should return health check', async () => {
    const res = await app.request('/healthcheck')
    expect(res.status).toBe(200)
  })

  it('should calculate BMI correctly', async () => {
    const res = await app.request('/bmi-calculator?height=1.75&weight=70&gender=male')
    const data = await res.json()
    expect(data.bmi).toBeCloseTo(22.86, 2)
    expect(data.category).toBe('Normal')
  })
})
```

![alt text](/images/4-hands-on-demo/4.1-sample-application/image-2.png?width=90pc)

*Figure 2: Running unit tests*

#### Step 3: Deploy with AWS CDK

Use Amazon Q to generate a CDK stack:

```
/dev Create AWS CDK stack to deploy Lambda function with Function URL for BMI Calculator
```

##### Generated CDK Stack:

**lib/bmi-stack.ts:**
```typescript
import * as cdk from 'aws-cdk-lib'
import * as lambda from 'aws-cdk-lib/aws-lambda'
import * as nodejs from 'aws-cdk-lib/aws-lambda-nodejs'

export class BmiStack extends cdk.Stack {
  constructor(scope: Construct, id: string, props?: cdk.StackProps) {
    super(scope, id, props)

    const bmiFunction = new nodejs.NodejsFunction(this, 'BmiFunction', {
      entry: 'src/index.ts',
      handler: 'handler',
      runtime: lambda.Runtime.NODEJS_18_X,
      bundling: { minify: true }
    })

    const functionUrl = bmiFunction.addFunctionUrl({
      authType: lambda.FunctionUrlAuthType.NONE,
      cors: { allowedOrigins: ['*'], allowedMethods: [lambda.HttpMethod.GET] }
    })

    new cdk.CfnOutput(this, 'FunctionUrl', { value: functionUrl.url })
  }
}
```

##### Deploy:
```bash
npm run build
cdk deploy
```

![alt text](/images/4-hands-on-demo/4.1-sample-application/image-3.png?width=90pc)
*Figure 3: Successfully deployed AWS Lambda Stack*

#### Step 4: Generate documentation with /doc

Use the `/doc` command to automatically generate API documentation:

```
/doc Generate API documentation for BMI Calculator with healthcheck and bmi-calculator endpoints
```

##### Generated documentation:

**API Endpoints:**

- **GET /healthcheck** - Check application status
- **GET /bmi-calculator** - Calculate BMI with parameters: height (m), weight (kg), gender (optional)

**Example:**
```bash
curl "https://your-function-url/bmi-calculator?height=1.75&weight=70&gender=male"
```

**Response:**
```json
{"gender":"male","height":1.75,"weight":70,"bmi":22.86,"category":"Normal"}
```

#### Step 5: Code review with /review

Use `/review` to check code quality:

```
/review Check code quality and security for BMI Calculator
```

![alt text](/images/4-hands-on-demo/4.1-sample-application/image-4.png?width=30pc)
*Figure 4: Review code quality*

#### Review checklist:
- ✅ Input validation checked
- ✅ Proper error handling
- ✅ TypeScript types used
- ✅ Full unit test coverage
- ✅ Security best practices followed

#### Result

After completion, you will have:
1. **BMI Calculator API** running on AWS Lambda
2. **Full unit tests**
3. **Automated deployment with CDK**
4. **Automatically generated API documentation**
5. **Code quality ensured via review**

Amazon Q Developer accelerates the entire process from development to deployment efficiently.
