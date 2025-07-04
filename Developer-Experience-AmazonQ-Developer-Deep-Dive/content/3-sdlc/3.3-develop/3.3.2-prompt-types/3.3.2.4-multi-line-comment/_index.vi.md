---
title: "Multi Line Comment"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: "<b>3.3.2.4 </b>"
---

Multi Line Comment
Amazon Q Developer hiểu ý định của bạn và đưa ra gợi ý dựa trên các comment nhiều dòng. Cách này rất phù hợp cho các logic phức tạp, nơi bạn có thể mô tả chi tiết yêu cầu, ràng buộc và hành vi mong đợi.

#### Tại sao nên dùng comment nhiều dòng?
- **Diễn đạt rõ ràng:** Mô tả yêu cầu và logic phức tạp
- **Rõ ràng:** Cung cấp ngữ cảnh, các trường hợp đặc biệt và ràng buộc
- **Kiểm soát:** Dẫn dắt AI sinh mã đúng với ý định của bạn

**Khuyến nghị:** Dùng comment nhiều dòng để phân tích bài toán, chỉ rõ input/output và nhấn mạnh các trường hợp đặc biệt.

---

#### Ví dụ #1: Định dạng số và chuỗi
**Prompt:**

```python
# Given a list that contains some numbers and strings, 
# format the list elements into a string in which the numbers are prepended with a "#" 
# and check for strings and wrap in a double quote.
```

Gợi ý của Amazon Q Developer:

```python
def format_list(lst):
    formatted = []
    for item in lst:
        if isinstance(item, int) or isinstance(item, float):
            formatted.append(f"#{item}")
        elif isinstance(item, str):
            formatted.append(f'"{item}"')
    return ', '.join(formatted)
```

---

#### Ví dụ #2: Lọc số chẵn
**Prompt:**

```python
# Given number list
# return new list contains odd numbers.
```

Gợi ý của Amazon Q Developer:

```python
def filter_even(numbers):
    return [n for n in numbers if n % 2 == 0]
```

---

#### Tổng kết
- Dùng comment nhiều dòng cho các yêu cầu và logic phức tạp
- Mô tả rõ bài toán, ràng buộc và kết quả mong muốn
- Càng nhiều ngữ cảnh, gợi ý mã càng sát với nhu cầu của bạn
