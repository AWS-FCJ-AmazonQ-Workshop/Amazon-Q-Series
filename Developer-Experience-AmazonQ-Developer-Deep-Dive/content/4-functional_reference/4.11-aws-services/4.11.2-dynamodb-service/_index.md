---
title: "Amazon DynamoDB Service with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.11.2. </b> "
---

#### Amazon DynamoDB Service with Amazon Q Developer

Amazon Q Developer can generate code for common DynamoDB operations in multiple programming languages. Below are concise examples for typical DynamoDB tasks using Python. You can request similar code for JavaScript, TypeScript, C#, Java, Scala, Go, or PHP.

##### Example 1: Create Table
**Prompt:**
Create a DynamoDB table with a given name and attributes.

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

##### Example 2: Add an Item
**Prompt:**
Add an item to the DynamoDB table.

```python
def put_item(table, item):
    try:
        table.put_item(Item=item)
        return True
    except Exception as e:
        print(e)
        return False
```

##### Example 3: Retrieve an Item
**Prompt:**
Retrieve an item from the DynamoDB table by primary key.

```python
def get_item(table, key):
    try:
        response = table.get_item(Key=key)
        return response.get('Item')
    except Exception as e:
        print(e)
        return None
```

##### Example 4: Delete an Item
**Prompt:**
Delete an item from the DynamoDB table by primary key.

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

