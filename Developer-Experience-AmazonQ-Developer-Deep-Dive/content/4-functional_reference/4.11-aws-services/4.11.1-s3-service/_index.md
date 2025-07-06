---
title: "Amazon S3 Service with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.11.1. </b> "
---

#### Amazon S3 Service with Amazon Q Developer

Amazon Q Developer can generate code for common S3 operations in multiple programming languages. Below are concise examples for typical S3 tasks using Python. You can request similar code for JavaScript, TypeScript, C#, Java, Scala, Go, or PHP.

##### Example 1: Create a Bucket
**Prompt:**
Create a bucket with a given name and return the bucket object if successful, otherwise return None.

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

##### Example 2: List Buckets
**Prompt:**
Return a list of all buckets in the account if successful, otherwise return None.

```python
def list_buckets(session):
    s3 = session.resource('s3')
    try:
        return s3.buckets.all()
    except Exception as e:
        print(e)
        return None
```

##### Example 3: Recursive Delete Bucket
**Prompt:**
Recursively delete all folders, objects, and the bucket. Return True if successful, otherwise return False.

```python
def delete_bucket_recursive(bucket_name, session):
    s3 = session.resource('s3')
    try:
        bucket = s3.Bucket(bucket_name)
        # Delete all objects
        bucket.objects.all().delete()
        # Delete all object versions (if versioning is enabled)
        bucket.object_versions.all().delete()
        # Delete bucket
        bucket.delete()
        return True
    except Exception as e:
        print(e)
        return False
```

##### Example 4: Check if Bucket Exists
**Prompt:**
Check if a bucket exists, return True if it does, otherwise return False.

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


