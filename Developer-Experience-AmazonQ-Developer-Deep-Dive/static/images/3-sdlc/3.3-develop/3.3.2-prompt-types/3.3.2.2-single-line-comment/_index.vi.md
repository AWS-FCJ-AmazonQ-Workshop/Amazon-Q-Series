---
title: "Single Line Comment"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b>3.3.2.2 </b> "
---

Single Line Comment
Amazon Q Developer có thể hiểu ý định của bạn và đưa ra gợi ý mã thông minh dựa trên comment một dòng ngắn gọn. Cách này rất phù hợp cho các hàm đơn giản hoặc khi bạn muốn prototype nhanh mà không cần viết tài liệu chi tiết.

#### Tại sao nên dùng comment một dòng?
- **Nhanh chóng:** Sinh mã cho các tác vụ phổ biến ngay lập tức
- **Rõ ràng:** Comment tốt sẽ thể hiện rõ mục đích
- **Đơn giản:** Lý tưởng cho các hàm nhỏ, tập trung

**Khuyến nghị:** Viết comment mang tính hành động và cụ thể về mục đích của hàm.

---

##### Ví dụ #1: In ra một thông điệp
**Prompt:**

```python
# function to print a message
```

Gợi ý của Amazon Q Developer:

```python
def print_message(message):
    print(message)
    return
```

---

##### Ví dụ #2: Cộng hai số
**Prompt:**

```python
# function to add two numbers
```

Gợi ý của Amazon Q Developer:

```python
def add_numbers(a, b):
    return a + b
```

---

#### Tổng kết
- Dùng comment một dòng để sinh mã nhanh cho các hàm đơn giản
- Hãy cụ thể trong comment để nhận được gợi ý phù hợp nhất
- Với logic phức tạp, hãy cân nhắc dùng comment nhiều dòng hoặc prompt chi tiết hơn
