---
title: "Xây dựng và triển khai ứng dụng mẫu trên IDE"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.2. </b> "
---

Trong phần này, chúng ta sẽ sử dụng Amazon Q Developer để xây dựng một ứng dụng BMI Calculator hoàn chỉnh. Ứng dụng được viết bằng TypeScript, sử dụng Hono framework và triển khai trên AWS Lambda.

#### Tổng quan ứng dụng

API BMI Calculator gồm các endpoint:
- GET `/healthcheck` - kiểm tra trạng thái hệ thống
- GET `/bmi-calculator?gender={gender}&height={height}&weight={weight}` - tính BMI

{{% notice note %}}
Source code tham khảo: https://github.com/AWS-FCJ-AmazonQ-Workshop/bmi-calculator
{{% /notice %}}

#### Bước 1: Thiết lập môi trường và project

##### 1.1 Tạo thư mục dự án
```bash
mkdir bmi-calculator-app
cd bmi-calculator-app
```

##### 1.2 Khởi tạo dự án Node.js
```bash
npm init -y
```

##### 1.3 Tạo ứng dụng với Amazon Q Developer

Mở VS Code trong thư mục dự án và sử dụng Amazon Q Developer:

```
/dev Create a BMI Calculator application using TypeScript with Hono framework. 
Expose API GET "/healthcheck" and "/bmi-calculator?gender={gender}&height={height}&weight={weight}"
```

{{% notice tip %}}
Amazon Q Developer sẽ tự động tạo cấu trúc project và các file cần thiết
{{% /notice %}}

##### 1.4 Kiểm tra cấu trúc project được tạo

Sau khi Amazon Q hoàn thành, bạn sẽ có cấu trúc như sau:
```
bmi-calculator-app/
├── package.json
├── tsconfig.json
├── src/
│   └── index.ts
└── node_modules/
```

##### 1.5 Xem lại package.json được tạo

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

##### 1.6 Cài đặt dependencies

```bash
npm install
```

#### Bước 2: Xem và hiểu code được tạo

##### 2.1 Kiểm tra file src/index.ts

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

##### 2.2 Test ứng dụng local

```bash
npm run dev
```

Mở browser và truy cập:
- `http://localhost:3000/healthcheck`
- `http://localhost:3000/bmi-calculator?height=1.75&weight=70&gender=male`

#### Bước 3: Tạo unit tests

##### 3.1 Yêu cầu Amazon Q tạo unit tests

Sử dụng lệnh `/test` trong Amazon Q Developer:

```
/test Create unit tests for BMI Calculator application
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-1.png?width=90pc)

*Hình 1: Tạo unit test cho BMI Calculator*

##### 3.2 Cài đặt testing dependencies

Amazon Q sẽ thêm các dependencies cần thiết vào package.json:

```bash
npm install --save-dev vitest @vitest/ui
```

##### 3.3 Kiểm tra unit tests được tạo

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

##### 3.4 Thêm test script vào package.json

```json
{
  "scripts": {
    "test": "vitest",
    "test:ui": "vitest --ui"
  }
}
```

##### 3.5 Chạy unit tests

```bash
npm test
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-2.png?width=90pc)

*Hình 2: Chạy unit test*

#### Bước 4: Chuẩn bị triển khai AWS

##### 4.1 Cài đặt AWS CDK

```bash
npm install -g aws-cdk
npm install --save-dev aws-cdk-lib constructs
```

##### 4.2 Khởi tạo CDK project

```bash
cdk init --language typescript
```

##### 4.3 Yêu cầu Amazon Q tạo CDK stack

```
/dev Create AWS CDK stack to deploy Lambda function with Function URL for BMI Calculator
```

##### 4.4 Kiểm tra CDK stack được tạo

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

##### 4.5 Cập nhật CDK app

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

#### Bước 5: Triển khai lên AWS

##### 5.1 Cấu hình AWS credentials

Đảm bảo AWS CLI đã được cấu hình:
```bash
aws configure
```

##### 5.2 Bootstrap CDK (chỉ chạy lần đầu)

```bash
cdk bootstrap
```

##### 5.3 Build và deploy

```bash
npm run build
cdk deploy
```

{{% notice warning %}}
Quá trình deploy có thể mất 2-3 phút. Xác nhận khi CDK hỏi về việc tạo IAM resources.
{{% /notice %}}

##### 5.4 Kiểm tra kết quả deploy

Sau khi deploy thành công, bạn sẽ thấy output:
```
BmiCalculatorStack.FunctionUrl = https://xxxxxxxx.lambda-url.us-east-1.on.aws/
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-3.png?width=90pc)
*Hình 3: Deploy thành công AWS Lambda Stack*

##### 5.5 Test API trên AWS

```bash
# Test healthcheck
curl "https://your-function-url/healthcheck"

# Test BMI calculator
curl "https://your-function-url/bmi-calculator?height=1.75&weight=70&gender=male"
```

#### Bước 6: Tạo documentation

##### 6.1 Yêu cầu Amazon Q tạo documentation

```
/doc Generate API documentation for BMI Calculator with healthcheck and bmi-calculator endpoints
```

##### 6.2 Documentation được tạo tự động

Document được tạo tự động, nội dung trong file **README.md:**

#### Bước 7: Code review và quality check

##### 7.1 Sử dụng Amazon Q để review code

```
/review Check code quality and security for BMI Calculator
```

![alt text](/images/4-hands-on-demo/4.2-q-ide/image-4.png?width=30pc)
*Hình 4: Review code quality*

##### 7.2 Checklist review tự động:
- ✅ **Input validation**: Kiểm tra tham số đầu vào
- ✅ **Error handling**: Xử lý lỗi hợp lý  
- ✅ **Type safety**: Sử dụng TypeScript types
- ✅ **Test coverage**: Unit test đầy đủ
- ✅ **Security**: Tuân thủ best practices bảo mật
- ✅ **Performance**: Code được tối ưu hóa

##### 7.3 Chạy quality checks

```bash
# Chạy tests
npm test

# Build kiểm tra lỗi TypeScript
npm run build

# Lint code (nếu có ESLint)
npm run lint
```

#### Bước 8: Clean up resources

##### 8.1 Xóa AWS resources

```bash
cdk destroy
```

##### 8.2 Xác nhận xóa

Gõ `y` để xác nhận xóa CloudFormation stack và tất cả resources.

#### Tổng kết lab

Sau khi hoàn thành lab này, bạn đã thành công:

1. **✅ Tạo project từ đầu** với Amazon Q Developer sử dụng `/dev`
2. **✅ Phát triển API BMI Calculator** với TypeScript và Hono framework
3. **✅ Viết và chạy unit tests** tự động với `/test`
4. **✅ Triển khai lên AWS Lambda** với CDK infrastructure as code
5. **✅ Tạo documentation** tự động với `/doc`
6. **✅ Review chất lượng code** với `/review`
7. **✅ Test API production** trên AWS Lambda Function URL

#### Kiến thức đã học

- **Amazon Q Developer commands**: `/dev`, `/test`, `/doc`, `/review`
- **TypeScript development**: Type safety, modern JavaScript
- **Hono framework**: Lightweight web framework cho Edge/Lambda
- **AWS CDK**: Infrastructure as Code với TypeScript
- **AWS Lambda**: Serverless function deployment
- **Unit testing**: Vitest framework và test automation
- **API development**: RESTful API design và best practices

{{% notice tip %}}
**Tip cho dự án thực tế**: Amazon Q Developer có thể giúp bạn implement tất cả các tính năng mở rộng trên chỉ bằng các prompts đơn giản!
{{% /notice %}}

Amazon Q Developer đã giúp tăng tốc toàn bộ quy trình phát triển từ khởi tạo project đến production deployment một cách hiệu quả và chuyên nghiệp.