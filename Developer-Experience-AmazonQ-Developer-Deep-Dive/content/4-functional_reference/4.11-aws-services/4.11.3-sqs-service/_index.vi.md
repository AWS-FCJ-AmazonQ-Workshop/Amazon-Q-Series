---
title: "Dịch vụ Amazon SQS với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.11.3 </b> "
---

## Dịch vụ Amazon SQS với Amazon Q Developer

Amazon Q Developer giúp bạn sinh mã cho các thao tác SQS phổ biến bằng nhiều ngôn ngữ lập trình. Dưới đây là ví dụ ngắn gọn với Python. Bạn có thể yêu cầu mã tương tự cho JavaScript, TypeScript, C#, Java, Scala, Go hoặc PHP.

### Ví dụ 1: Tạo queue
**Prompt:**
Tạo một queue nếu chưa tồn tại, trả về đối tượng queue.

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

### Ví dụ 2: Kiểm tra queue tồn tại
**Prompt:**
Kiểm tra queue có tồn tại không, trả về đối tượng queue nếu có, ngược lại trả về None.

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

### Ví dụ 3: Đưa item vào queue
**Prompt:**
Đưa một item vào queue, tạo queue nếu chưa tồn tại. Trả về True nếu thành công, ngược lại trả về False.

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

### Ví dụ 4: Lấy item từ queue
**Prompt:**
Lấy item từ queue, trả về True nếu thành công, ngược lại trả về False.

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

> **Lưu ý:** Cùng một ý định prompt có thể sinh mã khác nhau ở các ngôn ngữ do SDK khác biệt. Amazon Q Developer có thể sinh mã cho ngôn ngữ bạn chọn.