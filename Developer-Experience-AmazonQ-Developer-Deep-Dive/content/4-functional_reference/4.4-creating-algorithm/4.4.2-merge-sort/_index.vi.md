---
title: "Merge Sort"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.4.2. </b> "
---

#### Thuật toán Merge Sort

Merge Sort là thuật toán sắp xếp hiệu quả sử dụng kỹ thuật chia để trị (divide and conquer). Amazon Q Developer sẽ tự động tạo ra tất cả các function cần thiết.

#### Cách thực hiện

**Prompt chuẩn:**
```
create a merge_sort function
```

**Ngôn ngữ hỗ trợ:** Python, JavaScript, TypeScript, C#, Java, Scala, Go, PHP

#### Demo với Python

1. Tạo file `merge_sort.py` trong VSCode
2. Nhập comment prompt:
```python
# create a merge_sort function
```
3. Chấp nhận các suggestion từ Amazon Q Developer

**Kết quả được generate:**
```python
# create a merge_sort function
def merge_sort(list):
    if len(list) <= 1:
        return list
    mid = len(list) // 2
    left = merge_sort(list[:mid])
    right = merge_sort(list[mid:])
    return merge(left, right)

# create a merge function
def merge(left, right):
    result = []
    i, j = 0, 0
    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1
    result += left[i:]
    result += right[j:]
    return result
```