---
title: "Tối ưu mã với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.4.2. </b> "
---

Amazon Q Developer giúp bạn tối ưu mã để đạt hiệu năng và hiệu quả tốt hơn. Tính năng này đặc biệt hữu ích để phát hiện thuật toán kém hiệu quả và đề xuất cải tiến.

#### Cách tối ưu mã
1. **Tạo file mới** (ví dụ: `inefficientsort.py`) trong VSCode và dán đoạn mã sau:

```python
def inefficient_sort(arr):
    for i in range(len(arr)):
        for j in range(len(arr) - 1):
            if arr[j] > arr[j + 1]:
                # Swap elements
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    return arr
```

2. **Bôi đen toàn bộ đoạn mã, nhấp chuột phải và chọn** `Amazon Q Developer > Optimize`.
3. **Xem phản hồi.** Amazon Q Developer sẽ giải thích cách tối ưu đoạn mã và có thể đề xuất thuật toán hiệu quả hơn (ví dụ: dùng hàm sort tích hợp hoặc thuật toán sắp xếp nâng cao).

#### Best practices
- Luôn review mã quan trọng về hiệu năng để tìm cơ hội tối ưu
- Ưu tiên dùng hàm thư viện tích hợp hoặc đã được kiểm thử kỹ
- Hiểu rõ sự đánh đổi giữa khả năng đọc hiểu và hiệu năng