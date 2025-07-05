---
title: "Amazon S3 Service with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Amazon S3 Service with Amazon Q Developer

Amazon Q Developer can generate code for common S3 operations in multiple programming languages. Below are concise examples for typical S3 tasks using Python. You can request similar code for JavaScript, TypeScript, C#, Java, Scala, Go, or PHP.

#### Example 1: Create a Bucket
**Prompt:**
Tạo một bucket với tên cho trước và trả về đối tượng bucket nếu thành công, ngược lại trả về None.

```python
import boto3

def create_bucket(bucket_name, session):
    s3 = session.resource('s3')
    try:
        bucket = s3.create_bucket(Bucket=bucket_name)
        return bucket
    except Exception as e:
        print(e)
        return None
```

#### Example 2: List Buckets
**Prompt:**
Trả về danh sách tất cả các bucket trong tài khoản nếu thành công, ngược lại trả về None.

```python
def list_buckets(session):
    s3 = session.resource('s3')
    try:
        return s3.buckets.all()
    except Exception as e:
        print(e)
        return None
```

#### Example 3: Recursive Delete Bucket
**Prompt:**
Xóa đệ quy tất cả các folder, object và bucket. Trả về True nếu thành công, ngược lại trả về False.

// ...code sample for recursive delete (add as needed)...

#### Example 4: Check if Bucket Exists
**Prompt:**
Kiểm tra bucket có tồn tại không, trả về True nếu có, ngược lại trả về False.

```python
import boto3

def check_bucket_exists(bucket_name):
    s3 = boto3.client('s3')
    try:
        s3.head_bucket(Bucket=bucket_name)
        return True
    except Exception as e:
        print(e)
        return False
```

> **Note:** Prompts with the same intent may generate different code in different languages due to SDK differences. Amazon Q Developer can provide code for your preferred language.


