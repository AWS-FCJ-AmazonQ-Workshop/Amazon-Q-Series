---
title: "Merge Sort"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.4.2. </b> "
---

#### Merge Sort Algorithm

Merge Sort is an efficient sorting algorithm that uses the divide and conquer technique. Amazon Q Developer will automatically generate all the necessary functions.

#### How to Perform

**General Prompt:**
```
create a merge_sort function
```

**Supported Languages:** Python, JavaScript, TypeScript, C#, Java, Scala, Go, PHP

#### Demo with Python

1. Create a file `merge_sort.py` in VSCode
2. Enter the comment prompt:
```python
# create a merge_sort function
```
3. Accept the suggestions from Amazon Q Developer

**Generated Result:**
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
