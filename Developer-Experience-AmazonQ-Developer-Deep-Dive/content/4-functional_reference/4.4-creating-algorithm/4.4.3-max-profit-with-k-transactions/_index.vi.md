---
title: "Max Profit With K Transactions"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.4.3. </b> "
---

#### Bài toán tối đa hóa lợi nhuận với k giao dịch

Amazon Q Developer có thể sinh mã cho các bài toán thuật toán phức tạp như tối đa hóa lợi nhuận với k lần giao dịch (Max Profit With K Transactions).

##### Ví dụ prompt
Bạn được cung cấp một mảng `prices` trong đó `prices[i]` là giá cổ phiếu tại ngày thứ i. Hãy tìm lợi nhuận tối đa có thể đạt được với tối đa hai lần giao dịch. Lưu ý: Không được thực hiện nhiều giao dịch cùng lúc (phải bán xong mới được mua tiếp).

#### Ngôn ngữ hỗ trợ
Python, JavaScript, TypeScript, C#, Java, Go, PHP

#### Hướng dẫn thực hiện
1. Tạo file `max_profit_k_transactions.py` trong VSCode
2. Nhập prompt:
```python
# Bạn được cung cấp một mảng prices, hãy tìm lợi nhuận tối đa với tối đa hai lần giao dịch.
# Không được thực hiện nhiều giao dịch cùng lúc.
```
3. Nhấn Enter để nhận gợi ý từ Amazon Q Developer

#### Kết quả được generate
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