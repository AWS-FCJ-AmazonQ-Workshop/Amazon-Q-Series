---
title: "Custom Algo 01"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4.4. </b> "
---

Custom Algo 01
Let's try to create some random algorithms using Amazon Q Developer and Amazon Q Developer .

General Prompt:
Given a list of prices for a stock,
Find the minimum price 
Find the maximum profit
Find the average

then subtract the average from the maximum profit
then add the average to the minimum price

return the difference
Example #1:
Custom Algo 01

Python

JavaScript

TypeScript

C#

Java

Go

php
In your VSCode create a file custom_algo_1.py and type the following code:

Prompt:
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

""" 
Given a list of prices for a stock, Find the minimum price Find the maximum
profit Find the average

then subtract the average from the maximum profit then add the average to the
minimum price

return the difference 
"""


Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
Custom 01
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
def  average(list):
    return sum(list)/len(list)

def  max_profit(list):
    return max(list) - min(list)

def  min_price(list):
    return min(list)

def  max_price(list):
    return max(list)

def  difference(list):
    return max_profit(list) - average(list)

def  main():
    list = [1,2,3,4,5,6,7,8,9,10]
    print(difference(list))
    print(average(list))
    print(max_profit(list))
    print(min_price(list))
    print(max_price(list))