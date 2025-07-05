---
title: "Amazon Q: Generate Code"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.10.2. </b> "
---


#### Amazon Q: Generate Code

Amazon Q Developer can generate code for CLI commands and infrastructure automation. Open the Amazon Q Developer panel in your IDE, type your question, and press Enter to get code suggestions.

### Example 1: Generate CLI Command
**Prompt:**
How can I check the number of Amazon S3 buckets I have using the AWS CLI?

**Amazon Q Answer:**
```sh
aws s3api list-buckets --query "length(Buckets)"
```

#### Example 2: Generate Infrastructure as Code
**Prompt:**
Write a template to create an S3 bucket.

> **Note:** Amazon Q can generate code for various providers and use cases. Answers may include code snippets and explanations.



AWS

Azure

GCP
Prompt
1
Write a Amazon CloudFormation template to create an S3 bucket?


Amazon Q Answer #2
AWS Cloudformation
1
2
3
4
5
6
7
8
9
10
11
12
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



Example #3
Generating Code for SDK
General Prompt
1
 Write a program in <PROGRAMMING LANGUAGE> to create a <RESOURCE>.



AWS

Azure

GCP

Python

node.js

C#
Prompt
1
 Write a program in python to create an Amazon S3 Bucket.

Amazon Q Answer S3 Bucket - Python
SDK - AWS S3 Bucket
Example #4
Generating Code for COBOL
Prompt
1
2
3
 Given a json object has line items, 
 write a cobol program that calculates the sum of the line items 
 and calculates the tax of 7%


Cobol Generation
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39

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
