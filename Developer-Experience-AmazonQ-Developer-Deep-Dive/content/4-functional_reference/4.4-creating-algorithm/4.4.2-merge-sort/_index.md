---
title: "Merge Sort"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.4.2. </b> "
---

Merge Sort
Amazon Q Developer and Amazon Q Developer Will create all the necessary functions for you. Example:

Example #1:
Merge Sort
General Prompt
create a merge_sort function


Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In your VSCode create a file merge_sort.py and type the following code:

Prompt:
1
    # create a merge_sort function

Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
Merge Sort
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
   #create a merge_sort function
def merge_sort(list):
    if len(list) <= 1:
        return list
    mid = len(list) // 2
    left = merge_sort(list[:mid])
    right = merge_sort(list[mid:])
    return merge(left, right)


  #create a merge function
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
