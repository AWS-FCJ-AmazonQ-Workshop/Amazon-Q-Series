---
title: "Dịch vụ Amazon S3 với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.11.1 </b> "
---

#### Dịch vụ Amazon S3 với Amazon Q Developer

Amazon Q Developer giúp bạn sinh mã cho các thao tác S3 phổ biến bằng nhiều ngôn ngữ lập trình. Dưới đây là ví dụ ngắn gọn với Python. Bạn có thể yêu cầu mã tương tự cho JavaScript, TypeScript, C#, Java, Scala, Go hoặc PHP.

##### Ví dụ 1: Tạo bucket
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

##### Ví dụ 2: Liệt kê buckets
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

##### Ví dụ 3: Xóa đệ quy bucket
**Prompt:**
Xóa đệ quy tất cả các folder, object và bucket. Trả về True nếu thành công, ngược lại trả về False.

```python
def delete_bucket_recursive(bucket_name, session):
    s3 = session.resource('s3')
    try:
        bucket = s3.Bucket(bucket_name)
        # Xóa tất cả các objects
        bucket.objects.all().delete()
        # Xóa tất cả các phiên bản objects (nếu versioning được bật)
        bucket.object_versions.all().delete()
        # Xóa bucket
        bucket.delete()
        return True
    except Exception as e:
        print(e)
        return False
```

##### Ví dụ 4: Kiểm tra bucket tồn tại
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

> **Lưu ý:** Cùng một ý định prompt có thể sinh mã khác nhau ở các ngôn ngữ do SDK khác biệt. Amazon Q Developer có thể sinh mã cho ngôn ngữ bạn chọn.