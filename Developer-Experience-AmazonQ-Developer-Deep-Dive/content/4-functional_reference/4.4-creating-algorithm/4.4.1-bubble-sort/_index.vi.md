---
title: "Bubble Sort"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.4.1. </b> "
---

#### Thuật toán Bubble Sort

Bubble Sort là một trong những thuật toán sắp xếp cơ bản nhất. Amazon Q Developer có thể tự động generate code implementation chỉ thông qua một prompt đơn giản.

#### Cách thực hiện

**Prompt chuẩn:**
```
create a bubble_sort function
```

**Ngôn ngữ hỗ trợ:** Python, JavaScript, TypeScript, C#, Java, Scala, Go, PHP

#### Demo với Python

1. Tạo file `bubble_sort.py` trong VSCode
2. Nhập comment prompt:
```python
# create a bubble_sort function
```
3. Sử dụng suggestion của Amazon Q Developer

**Kết quả được generate:**
```python
def bubble_sort(array):
    for i in range(len(array)):
        for j in range(len(array)):
            if array[i] > array[j]:
                array[i], array[j] = array[j], array[i]
    return array
```