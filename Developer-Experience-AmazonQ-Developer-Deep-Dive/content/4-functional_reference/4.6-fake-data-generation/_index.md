---
title: "Fake Data Generation"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 4.6 </b> "
---

#### Overview of Fake Data Generation

One of the major challenges in software development is creating fake data. Amazon Q Developer can help you quickly generate fake data through appropriate prompts.

##### Example 1: Generate Fake Stock Data

**Sample Prompt:**
```
fake_stock_prices = {
    {…}
}
```

**Supported Languages:** Python, JavaScript, TypeScript, C#, Java, Go, PHP

**Generated Result:**
```python
fake_stock_prices = {
    {
        'symbol': 'AAPL',
        'price': '100.00'
    },,
}
```

##### Example 2: Generate Multiple Data Sets

Add a comma after the first data set and press Enter, Amazon Q Developer will continue generating data:

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

##### Example 3: Generate Automatic Stock Symbols

**Prompt:**
```python
"""
create a list of fake stock symbols by
generating random 4 letter stock names
"""
```

**Generated Result:**
```python
import random
import string

def generate_stock_symbols(n):
    return [random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) for i in range(n)]
```

##### Example 4: Generate Detailed Data with a Function

**Prompt:**
```python
"""
Create a function to generate a fake stock prices
    - ticker
    - return it as a dictionary object
The function should have a default value of 100 data
the function should create a list of random stock tickers, date of sale and price of sale
"""
```

**Generated Result:**
```python
import random
import datetime

def generate_fake_stock_prices(num_data=100):
    """
    return stock_prices
```

##### Example 5: Use the Faker Library

**Prompt:**
```python
"""
import the Faker package
use the Faker package to create a list of fake users
    - first_name
    - return it as a dictionary object

The function should have a default value of 100 data
"""
```