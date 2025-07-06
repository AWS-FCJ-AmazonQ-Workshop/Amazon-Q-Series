---
title: "Amazon Q: Generate Code"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.10.2 </b> "
---

#### Amazon Q: Generate Code

Amazon Q Developer có thể sinh mã cho các lệnh CLI và tự động hóa hạ tầng. Mở bảng Amazon Q Developer trong IDE, nhập câu hỏi và nhấn Enter để nhận gợi ý mã nguồn.

##### Ví dụ 1: Sinh lệnh CLI
**Prompt:**
Làm thế nào để kiểm tra số lượng Amazon S3 bucket tôi có bằng AWS CLI?

**Amazon Q Trả lời:**
```sh
aws s3api list-buckets --query "length(Buckets)"
```

##### Ví dụ 2: Sinh mã hạ tầng tự động (IaC)
**Prompt:**
Viết template để tạo một S3 bucket.

**Amazon Q Trả lời:**
```yaml
AWSTemplateFormatVersion: 2010-09-09
Resources:
  MyS3Bucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: my-sample-bucket
      PublicAccessBlockConfiguration:
        BlockPublicAcls: true
        BlockPublicPolicy: true
        IgnorePublicAcls: true
        RestrictPublicBuckets: true
```

##### Ví dụ 3: Sinh mã SDK
**Prompt:**
Viết chương trình Python để tạo một Amazon S3 Bucket.

**Amazon Q Trả lời:**
```python
import boto3

def create_s3_bucket(bucket_name, region=None):
    try:
        if region is None:
            s3_client = boto3.client('s3')
            s3_client.create_bucket(Bucket=bucket_name)
        else:
            s3_client = boto3.client('s3', region_name=region)
            location = {'LocationConstraint': region}
            s3_client.create_bucket(
                Bucket=bucket_name,
                CreateBucketConfiguration=location
            )
        print(f"S3 bucket {bucket_name} created successfully")
        return True
    except Exception as e:
        print(f"Error creating bucket: {e}")
        return False

# Sử dụng hàm
create_s3_bucket('my-example-bucket', 'us-west-2')
```

##### Ví dụ 4: Sinh mã COBOL
**Prompt:**
Cho một đối tượng JSON có các dòng mục, viết chương trình COBOL tính tổng các dòng mục và tính thuế 7%.

**Amazon Q Trả lời:**
```cobol
identification division.
program-id. json-sum-tax.

data division.
working-storage section.
   01 totals.
      05 total-amount                  pic 9(7)v99.
      05 total-tax-amount              pic 9(7)v99.

   01 line-item occurs 100 times. 
      05 amount                        pic 9(5)v99.
      05 filler                        redefines amount.
         10 dollars                    pic 9(3).
         10 cents                      pic 99.

procedure division.
   perform initialize-totals
   perform calculate-totals
   perform calculate-tax
   display-results.

   initialize-totals.
      move 0 to total-amount
      move 0 to total-tax-amount.

   calculate-totals.
      perform varying i from 1 by 1 until i > 100
         add amount(i) to total-amount
      end-perform.

   calculate-tax.
      compute total-tax-amount = total-amount * 0.07.

   display-results.
      display "Total amount: " total-amount
      display "Tax amount: " total-tax-amount.

   stop run.
```

> **Lưu ý:** Amazon Q có thể sinh mã cho nhiều nhà cung cấp và trường hợp sử dụng khác nhau. Câu trả lời có thể bao gồm đoạn mã và giải thích.