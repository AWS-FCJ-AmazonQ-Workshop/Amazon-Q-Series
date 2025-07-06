---
title: "Tạo dữ liệu giả lập"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 4.6 </b> "
---

#### Tổng quan về tạo dữ liệu giả lập (Fake Data)

Một trong những thách thức lớn khi phát triển phần mềm là tạo dữ liệu giả lập (fake data). Amazon Q Developer có thể giúp bạn sinh dữ liệu giả nhanh chóng thông qua các prompt phù hợp.

##### Ví dụ 1: Sinh dữ liệu giả cho cổ phiếu

**Prompt mẫu:**
```
fake_stock_prices = {
    {

    }
}
```

**Ngôn ngữ hỗ trợ:** Python, JavaScript, TypeScript, C#, Java, Go, PHP

**Kết quả được generate:**
```python
fake_stock_prices = {
    {
        'symbol': 'AAPL',
        'price': '100.00'
    },
}
```

##### Ví dụ 2: Sinh nhiều bộ dữ liệu

Thêm dấu phẩy sau bộ dữ liệu đầu tiên và nhấn Enter, Amazon Q Developer sẽ tiếp tục sinh thêm dữ liệu:

```python
fake_data = {
    {
        "ticker": "AAPL",
        "price": "100.00",
        "date": "2020-01-01"
    },
    {
        "ticker": "AMZN",
        "price": "200.00",
        "date": "2020-01-01"
    },
    {
        "ticker": "MSFT",
        "price": "300.00",
        "date": "2020-01-01"
    }
}
```

##### Ví dụ 3: Sinh mã tự động cho ký hiệu cổ phiếu

**Prompt:**
```python
"""
create a list of fake stock symbols by
generating random 4 letter stock names
"""
```

**Kết quả:**
```python
import random
import string

def generate_stock_symbols(n):
    return [random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) for i in range(n)]
```

##### Ví dụ 4: Sinh dữ liệu chi tiết với function

**Prompt:**
```python
"""
Create a function to generate a fake stock prices
    - ticker
    - price
    - date
    - return it as a dictionary object
The function should have a default value of 100 data
the function should create a list of random stock tickers, date of sale and price of sale
"""
```

**Kết quả:**
```python
import random
import datetime

def generate_fake_stock_prices(num_data=100):
    """
    Generate fake stock prices
    :param num_data:
    :return:
    """
    stock_tickers = ["AAPL", "MSFT", "AMZN", "GOOG"]
    stock_prices = []
    for i in range(num_data):
        ticker = random.choice(stock_tickers)
        price = round(random.uniform(10, 100), 2)
        date = datetime.datetime.now()
        stock_prices.append({"ticker": ticker, "price": price, "date": date})
    return stock_prices
```

##### Ví dụ 5: Sử dụng thư viện Faker

**Prompt:**
```python
"""
import the Faker package
use the Faker package to create a list of fake users
    - first_name
    - last_name
    - user_id
    - full_name
    - email
    - return it as a dictionary object

The function should have a default value of 100 data
the function should create a list of random first names, last names, user_ids, full names, emails
"""
```

**Kết quả:**
```python
from faker import Faker

def generate_fake_users(num_data=100):
    fake = Faker()
    data = []
    for i in range(num_data):
        data.append({
            "first_name": fake.first_name(),
            "last_name": fake.last_name(),
            "user_id": fake.user_id(),
            "full_name": fake.name(),
            "email": fake.email()
        })
    return data
```