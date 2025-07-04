---
title: "Amazon Q: Thêm chú thích cho mã nguồn"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.10.5 </b> "
---

## Amazon Q: Thêm chú thích cho mã nguồn

Amazon Q Developer có thể tự động thêm chú thích cho mã nguồn của bạn. Chọn đoạn mã trong IDE, nhấn chuột phải và gửi đến Q để nhận chú thích. Có thể nhập prompt nếu cần.

### Ví dụ: Thêm chú thích cho mã
**Prompt:**
Thêm chú thích cho đoạn mã sau:
```python
sum = 0
line_items = [{'amount': 0} for i in range(100)]

for j in range(len(line_items)):
  sum += line_items[j]

tax = sum * tax_rate
total = sum + tax  

print(f"Sum: {sum}")
print(f"Tax: {tax}")
print(f"Total: {total}")
```

**Amazon Q Trả lời:**
```python
# Khởi tạo biến tổng bằng 0 
sum = 0

# Tạo danh sách 100 mục với giá trị amount = 0
line_items = [{'amount': 0} for i in range(100)]

# Lặp qua từng mục trong danh sách line_items
for j in range(len(line_items)):
  # Cộng giá trị của mục hiện tại vào tổng
  sum += line_items[j]

# Tính thuế bằng cách nhân tổng với thuế suất
tax = sum * tax_rate  

# Tính tổng cộng bằng cách cộng tổng và thuế
total = sum + tax

# In ra tổng
print(f"Sum: {sum}")

# In ra thuế
print(f"Tax: {tax}") 

# In ra tổng cộng
print(f"Total: {total}")
```

> **Lưu ý:** Amazon Q hỗ trợ chú thích cho nhiều ngôn ngữ lập trình.