---
title: "Custom Algo 01"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4.4. </b> "
---

#### Developing Custom Algorithms

Amazon Q Developer not only supports classical algorithms but can also develop complex custom algorithms tailored to specific business logic.

#### Problem Requirements

Given a list of stock prices, perform the following steps:
1. Calculate the minimum, maximum, and average prices
2. Calculate the max profit (max - min)
3. Compute (max_profit - average) and (min_price + average)
4. Return the difference between the two values

#### Supported Languages
Python, JavaScript, TypeScript, C#, Java, Go, PHP

#### Demo with Python

1. Create a file `custom_algo_1.py`
2. Describe the requirements in a comment
3. Accept suggestions from Amazon Q Developer

#### Generated Result
```python
def average(list):
    return sum(list)/len(list)

def max_profit(list):
    return max(list) - min(list)

def min_price(list):
    return min(list)

def max_price(list):
    return max(list)

def difference(list):
    return max_profit(list) - average(list)

def main():
    list = [1,2,3,4,5,6,7,8,9,10]
    print(difference(list))
    print(average(list))
    print(max_profit(list))
    print(min_price(list))
    print(max_price(list))
```