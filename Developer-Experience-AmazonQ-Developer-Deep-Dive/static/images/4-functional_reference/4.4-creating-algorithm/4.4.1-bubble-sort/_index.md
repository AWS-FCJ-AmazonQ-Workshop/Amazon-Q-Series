---
title: "Bubble Sort"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.4.1. </b> "
---

Bubble Sort
Amazon Q Developer and Amazon Q Developer can provide suggestions for the common algorithms. Example:

Example #1:
Bubble Sort
General Prompt
create a bubble_sort function


Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In your VSCode create a file bubble_sort.py and type the following code:

Prompt:
1
    # create a bubble_sort function

Amazon Q Developer Suggestion:
Bubble Sort
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
def bubble_sort(array):
    # loop through the array
    for i in range(len(array)):
        # loop through the array again
        for j in range(len(array)):
            # if the element is greater than the next element, swap them
            if array[i] > array[j]:
                array[i], array[j] = array[j], array[i]
    return array
   