---
title: "Amazon SQS Service with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.11.3. </b> "
---

#### Amazon SQS Service with Amazon Q Developer

Amazon Q Developer helps you generate code for common SQS operations in multiple programming languages. Below are concise examples for typical SQS tasks using Python. You can request similar code for JavaScript, TypeScript, C#, Java, Scala, Go, or PHP.

##### Example 1: Create a Queue
**Prompt:**
Create a queue if it does not exist, and return the queue object.

```python
import boto3

def create_queue(queue_name):
    sqs = boto3.resource('sqs')
    try:
        queue = sqs.create_queue(QueueName=queue_name)
        return queue
    except Exception as e:
        print(e)
        return None
```

##### Example 2: Check if Queue Exists
**Prompt:**
Check if a queue exists, return the queue object if it does, otherwise return None.

```python
def check_queue(queue_name):
    sqs = boto3.resource('sqs')
    try:
        queue = sqs.get_queue_by_name(QueueName=queue_name)
        return queue
    except Exception as e:
        print(e)
        return None
```

##### Example 3: Put Item on Queue
**Prompt:**
Put an item on the queue, create the queue if it does not exist. Return True if successful, otherwise return False.

```python
def put_item_on_queue(queue_name, item):
    sqs = boto3.resource('sqs')
    queue = check_queue(queue_name)
    if queue is None:
        queue = create_queue(queue_name)
    if queue is not None:
        queue.send_message(MessageBody=item)
        return True
    else:
        return False
```

##### Example 4: Get Item from Queue
**Prompt:**
Retrieve an item from the queue, return True if successful, otherwise return False.

```python
def get_item_from_queue(queue_name):
    sqs = boto3.resource('sqs')
    queue = check_queue(queue_name)
    if queue is not None:
        response = queue.receive_messages(MessageAttributeNames=['All'])
        for message in response:
            print(message.body)
            message.delete()
        return True
    else:
        return False
```

> **Note:** Prompts with the same intent may generate different code in different languages due to SDK differences. Amazon Q Developer can provide code for your preferred language.