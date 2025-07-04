---
title: "Max Profit With K Transactions"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.4.3. </b> "
---

Max Profit With K Transactions
Amazon Q Developer understands your intent and provide suggestions comments for most complex algorithms. Example from LeetCode 

General Prompt:
1
2
3
You are given an array prices where prices[i] is the price of a given stock on the ith day.
Find the maximum profit you can achieve. You may complete at most two transactions.
Note: You may not engage in multiple transactions simultaneously (i.e., you must sell the stock before you buy again).

Example #1:
Max Profit With K Transactions

Python

JavaScript

TypeScript

C#

Java

Go

php
In your VSCode create a file max_profit_k_transactions.py and type the following code:

Prompt:
1
2
3
#You are given an array prices where prices[i] is the price of a given stock on the i^th^ day.
#Find the maximum profit you can achieve. You may complete at most two transactions.
#Note: You may not engage in multiple transactions simultaneously (i.e., you must sell the stock before you buy again).

Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
Max Profit
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
25
26
27
28
29
30
31
32
33
import List

class Solution: 
    def maxProfit(self, prices: List[int]) -> int: 
    if not prices:
        return 0

        buy1 = buy2 = float('inf')
        sell1 = sell2 = 0

        for price in prices:
            buy1 = min(buy1, price)
            sell1 = max(sell1, price - buy1)
            buy2 = min(buy2, price - sell1)
            sell2 = max(sell2, price - buy2)

        return sell2

    def maxProfit2(self, prices: List[int]) -> int:
        if not prices:
            return 0

        n = len(prices)
        k = 2
        dp = [[0 for _ in range(n)] for _ in range(k + 1)]

        for t in range(1, k + 1):
            max_diff = float('-inf')
            for d in range(1, n):
                max_diff = max(max_diff, dp[t - 1][d - 1] - prices[d - 1])
                dp[t][d] = max(dp[t][d - 1], prices[d] + max_diff)

        return dp[k][-1]