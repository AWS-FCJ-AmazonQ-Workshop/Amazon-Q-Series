---
title: "Dịch vụ Amazon DynamoDB với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.11.2 </b> "
---

#### Dịch vụ Amazon DynamoDB với Amazon Q Developer

Amazon Q Developer giúp bạn sinh mã cho các thao tác DynamoDB phổ biến bằng nhiều ngôn ngữ lập trình. Dưới đây là ví dụ ngắn gọn với Python. Bạn có thể yêu cầu mã tương tự cho JavaScript, TypeScript, C#, Java, Scala, Go hoặc PHP.

##### Ví dụ 1: Tạo bảng
**Prompt:**
Tạo một bảng DynamoDB với tên và các thuộc tính cho trước.

```python
import boto3

def create_table(table_name, key_schema, attribute_definitions, session):
    dynamodb = session.resource('dynamodb')
    try:
        table = dynamodb.create_table(
            TableName=table_name,
            KeySchema=key_schema,
            AttributeDefinitions=attribute_definitions,
            ProvisionedThroughput={
                'ReadCapacityUnits': 5,
                'WriteCapacityUnits': 5
            }
        )
        table.wait_until_exists()
        return table
    except Exception as e:
        print(e)
        return None
```

##### Ví dụ 2: Thêm một item
**Prompt:**
Thêm một item vào bảng DynamoDB.

```python
def put_item(table, item):
    try:
        table.put_item(Item=item)
        return True
    except Exception as e:
        print(e)
        return False
```

##### Ví dụ 3: Lấy một item
**Prompt:**
Lấy một item từ bảng DynamoDB theo khóa chính.

```python
def get_item(table, key):
    try:
        response = table.get_item(Key=key)
        return response.get('Item')
    except Exception as e:
        print(e)
        return None
```

##### Ví dụ 4: Xóa một item
**Prompt:**
Xóa một item khỏi bảng DynamoDB theo khóa chính.

```python
def delete_item(table, key):
    try:
        table.delete_item(Key=key)
        return True
    except Exception as e:
        print(e)
        return False
```

> **Lưu ý:** Amazon Q Developer có thể sinh mã cho các thao tác DynamoDB khác và nhiều ngôn ngữ khác nhau theo yêu cầu của bạn.