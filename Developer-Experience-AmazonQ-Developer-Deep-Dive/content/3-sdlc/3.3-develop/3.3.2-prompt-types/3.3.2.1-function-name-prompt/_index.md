---
title: "Function Name Prompt"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.3.2.1. </b> "
---

Function Name Prompt
Amazon Q Developer can understand your intent and provides suggestions based on the function names. The more descriptive the function name is, the better the suggestions.

Example #1
Towers of Hanoi
General Prompt
1
 In this case,  the prompt is the function name and there is no other information need to be provided


Python

JavaScript

TypeScript

C#

Java

Scala

Go

PHP

Rust
Prompt
1
2

def towers_of_hanoi(


Create a file in your VSCode and name it basic.py.

In your VSCode If you start typing def towers_of_hanoi( and wait a few seconds, Amazon Q Developer will provide the following suggestion:

Amazon Q Developer Suggestion #1
Towers of hanoi
1
2
3
4
5
6
7
def towers_of_hanoi(n, source, destination, auxiliary):
    if n == 1:
        print(source, destination)
        return
    towers_of_hanoi(n - 1, source, auxiliary, destination)
    print(source, destination)
    towers_of_hanoi(n - 1, auxiliary, destination, source)


Example #2:
Average
General Prompt:
 In this case,  the prompt is the function name and there is no other information need to be provided

Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
Prompt:
1
def get_average(numbers):


In your VSCode If you type def get_average(numbers): and press enter, Amazon Q Developer will provide the following suggestion:

Amazon Q Developer Suggestion:
def get_average
1
2
3
def get_average(numbers): 
    mean = sum(numbers) / len(numbers) 
    return mean


Sometimes you have multiple code suggestions. If you hover over the suggestion, you will see a popup with the following information:

Multiple Options

The number of suggestions is shown in the left corner of the popup. You can use the arrow keys to navigate through the suggestions. Once you want to accept a suggestion, press Tab.

Example #3:
Standard Deviation
General Prompt:
 In this case,  the prompt is the function name and there is no other information need to be provided

Python

JavaScript

TypeScript

C#

Java

Scala

Go

PHP

Rust
Prompt:
1
def standard_deviation(numbers):


In your VSCode If you type def standard_deviation(numbers): and press enter, Amazon Q Developer will provide the following suggestion:

Amazon Q Developer Suggestion #1:
def standard_deviation
1
2
3
def standard_deviation(numbers): 
    mean = sum(numbers) / len(numbers) 
    return (sum((x - mean) ** 2 for x in numbers) / len(numbers)) ** 0.5


Amazon Q Developer Suggestion #2:
def standard_deviation
1
2
3
4
5
6
7
8
import math
def standard_deviation(numbers):

    return math.sqrt(variance(numbers))

def variance(numbers): 
    mean = sum(numbers) / len(numbers) 
    return sum([(x - mean) ** 2 for x in numbers]) / len(numbers)
