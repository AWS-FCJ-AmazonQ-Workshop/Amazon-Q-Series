---
title: "Tính năng bổ sung với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.5.1. </b> "
---

Giả sử bạn có một mã nguồn hiện tại là máy tính đơn giản. Giờ đây, yêu cầu nghiệp vụ thay đổi và bạn cần mở rộng để hỗ trợ các chức năng máy tính khoa học.

Trong phần này, bạn sẽ trải nghiệm sử dụng Amazon Q Developer Agent for Software Development để bổ sung tính năng mới. Trong IDE, mở bảng chat Amazon Q Developer, gõ `/dev` và nhấn Enter hai lần để mở Agent ở tab mới.

#### Ví dụ:

**Bước 1:** Tạo file mới tên `calculator.py` trong VSCode và dán mã máy tính đơn giản hiện có.

```python
class Calculator:
    def add(self, a, b):
        return a + b
    def subtract(self, a, b):
        return a - b
    def multiply(self, a, b):
        return a * b
    def divide(self, a, b):
        return a / b
```

**Bước 2:** Dùng Agent để bổ sung các hàm (ví dụ: sin, cos, tan, sqrt, power).

Prompt:

```text
Extend this calculator to be a scientific calculator that supports sin, cos, tan and log10 functionality. Do this as separate class that extends the basic calculator. While you're at it, generate the unit tests as well.
```

![alt text](image.png?width=40pc)

**Bước 3:** Xem xét, chấp nhận hoặc lặp lại các gợi ý mã cho phù hợp.

#### Best practices
- Đưa ra prompt rõ ràng mô tả tính năng mới bạn muốn
- Xem xét mã sinh ra về độ chính xác và style
- Kiểm thử kỹ các tính năng mới trước khi triển khai