---
title: "Max Profit With K Transactions"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.4.3. </b> "
---

#### Maximize Profit with K Transactions

Amazon Q Developer can generate code for complex algorithmic problems like maximizing profit with k transactions (Max Profit With K Transactions).

##### Example Prompt
You are given an array `prices` where `prices[i]` is the price of a stock on the i-th day. Find the maximum profit you can achieve with at most two transactions. Note: You may not engage in multiple transactions simultaneously (i.e., you must sell the stock before buying again).

#### Supported Languages
Python, JavaScript, TypeScript, C#, Java, Go, PHP

#### How to Perform
1. Create a file `max_profit_k_transactions.py` in VSCode
2. Enter the prompt:
```python
# You are given an array prices, find the maximum profit with at most two transactions.
# Note: You may not engage in multiple transactions simultaneously.
```
3. Press Enter to receive suggestions from Amazon Q Developer

#### Generated Result
```python
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
```