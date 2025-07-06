---
title: "Amazon Q: Generate Code"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.10.2 </b> "
---

#### Amazon Q: Generate Code

Amazon Q Developer can generate code for CLI commands and infrastructure automation. Open the Amazon Q Developer panel in your IDE, type your question, and press Enter to get code suggestions.

##### Example 1: Generate CLI Command
**Prompt:**
How can I check the number of Amazon S3 buckets I have using the AWS CLI?

**Amazon Q Answer:**
```sh
aws s3api list-buckets --query "length(Buckets)"
```

##### Example 2: Generate Infrastructure as Code
**Prompt:**
Write a template to create an S3 bucket.

**Amazon Q Answer:**
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

##### Example 3: Generate SDK Code
**Prompt:**
Write a Python program to create an Amazon S3 Bucket.

**Amazon Q Answer:**
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

# Use the function
create_s3_bucket('my-example-bucket', 'us-west-2')
```

##### Example 4: Generate COBOL Code
**Prompt:**
Given a JSON object with line items, write a COBOL program to calculate the sum of the line items and apply a 7% tax.

**Amazon Q Answer:**
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

> **Note:** Amazon Q can generate code for various providers and use cases. Answers may include code snippets and explanations.
