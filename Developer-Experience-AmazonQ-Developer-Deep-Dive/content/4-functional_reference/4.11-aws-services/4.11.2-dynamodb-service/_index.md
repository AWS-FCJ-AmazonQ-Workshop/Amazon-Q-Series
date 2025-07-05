---
title: "Amazon DynamoDB Service with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Amazon DynamoDB Service with Amazon Q Developer

Amazon Q Developer can generate code for common DynamoDB operations in multiple programming languages. Below are concise examples for typical DynamoDB tasks using Python. You can request similar code for JavaScript, TypeScript, C#, Java, Scala, Go, or PHP.

#### Example 1: Create Table
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

#### Example 2: Put Item
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

#### Example 3: Get Item
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

#### Example 4: Delete Item
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

> **Note:** Amazon Q Developer can generate code for other DynamoDB operations and in different languages as needed.

