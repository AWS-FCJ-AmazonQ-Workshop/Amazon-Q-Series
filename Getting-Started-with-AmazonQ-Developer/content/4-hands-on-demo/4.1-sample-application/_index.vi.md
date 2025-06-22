---
title: "Xây dựng và triển khai ứng dụng mẫu"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

Trong phần này, chúng ta sẽ sử dụng Amazon Q Developer để xây dựng một ứng dụng BMI Calculator hoàn chỉnh. Ứng dụng được viết bằng TypeScript, sử dụng Hono framework và triển khai trên AWS Lambda.

#### Tổng quan ứng dụng

API BMI Calculator gồm các endpoint:
- GET `/healthcheck` - kiểm tra trạng thái hệ thống
- GET `/bmi-calculator?gender={gender}&height={height}&weight={weight}` - tính BMI

{{% notice note %}}
Source code tham khảo: https://github.com/AWS-FCJ-AmazonQ-Workshop/bmi-calculator
{{% /notice %}}

#### Bước 1: Tạo ứng dụng với /dev

Sử dụng Amazon Q Developer với lệnh `/dev` để tạo ứng dụng:

```
/dev Create a BMI Calculator application using TypeScript with Hono framework. 
Expose API GET "/healthcheck" and "/bmi-calculator?gender={gender}&height={height}&weight={weight}"
```

##### Code chính được tạo:

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

#### Bước 2: Tạo unit tests với /test

Sử dụng lệnh `/test` để tạo unit tests:

```
/test Create unit tests for BMI Calculator application
```

![alt text](/images/4-hands-on-demo/4.1-sample-application/image-1.png?width=90pc)

*Hình 1: Tạo unit test cho BMI Calculator*

##### Unit tests được tạo:
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

*Hình 2: Chạy unit test*

#### Bước 3: Triển khai với AWS CDK

Sử dụng Amazon Q để tạo CDK stack:

```
/dev Create AWS CDK stack to deploy Lambda function with Function URL for BMI Calculator
```

##### CDK Stack được tạo:

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
*Hình 3: Deploy thành công AWS Lambda Stack*

#### Bước 4: Tạo documentation với /doc

Sử dụng lệnh `/doc` để tự động tạo tài liệu API:

```
/doc Generate API documentation for BMI Calculator with healthcheck and bmi-calculator endpoints
```

##### Documentation được tạo:

**API Endpoints:**

- **GET /healthcheck** - Kiểm tra trạng thái ứng dụng
- **GET /bmi-calculator** - Tính BMI với các tham số: height (m), weight (kg), gender (optional)

**Ví dụ:**
```bash
curl "https://your-function-url/bmi-calculator?height=1.75&weight=70&gender=male"
```

**Response:**
```json
{"gender":"male","height":1.75,"weight":70,"bmi":22.86,"category":"Normal"}
```

#### Bước 5: Code review với /review

Sử dụng `/review` để kiểm tra chất lượng code:

```
/review Check code quality and security for BMI Calculator
```

![alt text](/images/4-hands-on-demo/4.1-sample-application/image-4.png?width=30pc)
*Hình 4: Review code quality*

#### Checklist review:
- ✅ Kiểm tra input validation
- ✅ Xử lý lỗi hợp lý
- ✅ Sử dụng TypeScript types
- ✅ Đầy đủ unit test coverage
- ✅ Tuân thủ best practices về bảo mật

#### Kết quả

Sau khi hoàn thành, bạn sẽ có:
1. **BMI Calculator API** hoạt động trên AWS Lambda
2. **Unit tests** đầy đủ
3. **Triển khai tự động với CDK**
4. **Tài liệu API** được tạo tự động
5. **Chất lượng code** được đảm bảo qua review

Amazon Q Developer giúp tăng tốc toàn bộ quy trình từ phát triển đến triển khai một cách hiệu quả.