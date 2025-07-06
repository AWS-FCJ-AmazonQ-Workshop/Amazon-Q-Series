---
title: "Single Line Prompt"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: "<b>3.3.2.3 </b>"
---

Single Line Prompt
Amazon Q Developer sẽ hiểu ý định của bạn và đưa ra gợi ý dựa trên các prompt hoặc comment một dòng mang tính chỉ thị rõ ràng. Cách này đặc biệt hữu ích khi bạn muốn hướng dẫn AI thực hiện các hành động như CREATE, RETURN hoặc các thao tác cụ thể khác.

#### Tại sao nên dùng Single Line Prompt?
- **Chỉ thị rõ ràng:** Dẫn dắt AI bằng các hành động cụ thể (ví dụ: CREATE, RETURN)
- **Hiệu quả:** Sinh mã nhanh cho các tác vụ phổ biến
- **Rõ ràng:** Hướng dẫn hành động rõ ràng sẽ cho kết quả tốt hơn

**Khuyến nghị:** Sử dụng động từ mệnh lệnh và mô tả cụ thể mục đích, kết quả mong muốn của hàm.

---

##### Ví dụ #1: Hàm lấy tuổi người dùng
**Prompt:**

```python
# create a function called get user age
# ask the user to input their age
# return the user's age
```

Gợi ý của Amazon Q Developer:

```python
def get_user_age():
    age = input("Please enter your age: ")
    return age
```

---

##### Ví dụ #2: Tính diện tích
**Prompt:**

```python
# create a function to calculate the area of a rectangle
# return the area
```

Gợi ý của Amazon Q Developer:

```python
def calculate_area(length, width):
    return length * width
```

---

#### Tổng kết
- Dùng single line prompt với chỉ thị rõ ràng để sinh mã nhanh, chính xác
- Kết hợp nhiều prompt một dòng cho logic phức tạp hơn
- Xem xét và chỉnh sửa gợi ý để phù hợp nhất với nhu cầu của bạn
