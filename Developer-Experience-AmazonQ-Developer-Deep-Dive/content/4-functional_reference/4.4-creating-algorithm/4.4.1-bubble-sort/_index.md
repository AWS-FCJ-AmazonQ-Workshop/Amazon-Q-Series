---
title: "Bubble Sort"
date: "July 6, 2025"
weight: 1
chapter: false
pre: " <b> 4.4.1. </b> "
---

#### Bubble Sort Algorithm

Bubble Sort is one of the most basic sorting algorithms. Amazon Q Developer can automatically generate code implementations with just a simple prompt.

#### How to Perform

**General Prompt:**
```
create a bubble_sort function
```

**Supported Languages:** Python, JavaScript, TypeScript, C#, Java, Scala, Go, PHP

#### Demo with Python

1. Create a file `bubble_sort.py` in VSCode
2. Enter the comment prompt:
```python
# create a bubble_sort function
```
3. Use the suggestion from Amazon Q Developer

**Generated Result:**
```python
def bubble_sort(array):
    for i in range(len(array)):
        for j in range(len(array)):
            if array[i] > array[j]:
                array[i], array[j] = array[j], array[i]
    return array
```
