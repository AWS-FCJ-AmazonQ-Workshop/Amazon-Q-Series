---
title: "Multi Line Prompt"
date: 2023-08-17T00:00:00-00:00
weight: 5
chapter: false
pre: "<b>3.3.2.5 </b>"
---

Multi Line Prompt
Amazon Q Developer hiểu ý định của bạn và đưa ra gợi ý dựa trên các chỉ thị trong prompt nhiều dòng. Việc sử dụng các chỉ thị rõ ràng (ví dụ: CREATE, FORMAT, RETURN) trong prompt giúp hướng dẫn AI sinh ra kết quả đúng mong muốn, đặc biệt với các yêu cầu phức tạp.

#### Tại sao nên dùng Multi Line Prompt?
- **Rõ ràng:** Chỉ thị giúp AI hiểu chính xác ý định của bạn
- **Xử lý phức tạp:** Phù hợp cho logic nhiều bước, nhiều yêu cầu
- **Tùy chỉnh:** Sinh mã sát với nhu cầu thực tế

**Khuyến nghị:** Dùng ngôn ngữ mệnh lệnh rõ ràng và phân tích bài toán thành các bước logic trong prompt.

---

#### Ví dụ #1: Định dạng số và chuỗi
**Prompt:**

```python
# Given a list that contains some numbers and strings,
# **CREATE** a function called `format_list` and
# format the numbers in the list into a string in which the numbers are prepended with a "#"
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

#### Ví dụ #2: Tìm giá trị lớn nhất
**Prompt:**

```python
# **CREATE** a find max function
# **RETURN** a max number.
```

Gợi ý của Amazon Q Developer:

```python
def find_max(numbers):
    return max(numbers)
```

---

#### Tổng kết
- Dùng multi-line prompt với chỉ thị rõ ràng cho logic phức tạp hoặc nhiều bước
- Phân tích yêu cầu thành các bước cụ thể, dễ thực hiện
- Càng chi tiết, gợi ý mã càng sát với nhu cầu của bạn
