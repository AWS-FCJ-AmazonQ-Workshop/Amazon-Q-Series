---
title: "Custom Algo 01"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4.4. </b> "
---

#### Phát triển Custom Algorithm

Amazon Q Developer không chỉ hỗ trợ các thuật toán cổ điển mà còn có thể phát triển các thuật toán custom phức tạp theo business logic cụ thể.

#### Yêu cầu bài toán

Cho danh sách giá cổ phiếu, thực hiện các bước:
1. Tính giá minimum, maximum và average
2. Tính max profit (max - min)
3. Tính (max_profit - average) và (min_price + average)
4. Return hiệu số của hai giá trị trên

#### Cách thực hiện

**Ngôn ngữ hỗ trợ:** Python, JavaScript, TypeScript, C#, Java, Go, PHP

#### Demo với Python

1. Tạo file `custom_algo_1.py`
2. Mô tả yêu cầu trong comment
3. Chấp nhận suggestion từ Amazon Q Developer

**Kết quả được generate:**
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