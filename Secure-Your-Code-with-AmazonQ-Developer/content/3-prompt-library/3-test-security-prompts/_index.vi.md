---
title: "Kiểm tra Security Prompt"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3 </b> "
---

Bây giờ khi chúng ta đã tạo xong vulnerable code samples và thư viện security prompt, hãy kiểm tra xem Amazon Q Developer có thể phát hiện các security issues hiệu quả như thế nào với các chiến lược prompt khác nhau.

#### Testing Different Prompt Approaches

**1. General Security Review**

Sử dụng security prompt tổng quát để quét một file:

```
@Multi-Vulnerability-Scan @vulnerable_app.py
```

![Prompt-Library](/images/7/prompt-lib-5.png?width=90pc)
_Hình 1: Thực hiện đánh giá bảo mật tổng quát trên một file_

- **Purpose**: Thực hiện phân tích bảo mật tổng thể, bao phủ cả 6 loại vulnerability chỉ trong một lần quét.
- **Expected Output**: Tổng quan về tất cả các vulnerabilities cùng với các gợi ý khắc phục cơ bản.

**2. Specialized Database Security Check**

Tập trung kiểm tra các vulnerabilities liên quan đến database:

```
@Database-Security-Check @vulnerable_app.py @file_handler.py
```

![Prompt-Library](/images/7/prompt-lib-6.png?width=90pc)
_Hình 2: Thực hiện kiểm tra bảo mật chuyên sâu cho database_

- **Purpose**: Phân tích sâu về các vấn đề SQL injection và credential exposure.
- **Expected Output**: Phân tích chi tiết về database security kèm ví dụ cho SQLite/PostgreSQL.

**3. Web Application Security Audit**

Tập trung vào các vulnerabilities đặc thù của web application:

```
@Web-App-Security-Audit @vulnerable_app.py
```

![Prompt-Library](/images/7/prompt-lib-7.png?width=90pc)
_Hình 3: Thực hiện đánh giá bảo mật ứng dụng web_

- **Purpose**: Nhấn mạnh các vấn đề bảo mật riêng cho Flask như redirects và command injection.
- **Expected Output**: Đưa ra best practices về web security cùng các giải pháp khắc phục cho Flask.

**4. Comprehensive Multi-File Analysis**

Phân tích đồng thời tất cả các file có lỗ hổng:

```
@Multi-Vulnerability-Scan @vulnerable_app.py @file_handler.py @auth_service.py
```

![Prompt-Library](/images/7/prompt-lib-8.png?width=90pc)
_Hình 4: Thực hiện phân tích bảo mật toàn diện trên nhiều file_

- **Purpose**: Đánh giá bảo mật toàn diện trên toàn bộ codebase.

- **Expected Output**: Báo cáo tổng hợp, thể hiện mối liên hệ giữa các vulnerabilities ở nhiều file.

#### Tiêu chí đánh giá chất lượng

Với mỗi phát hiện về security, kiểm tra xem Amazon Q có cung cấp:

- ✅ **Exact line number** và đoạn code gây lỗi
- ✅ **Severity level** (Critical/High/Medium/Low)
- ✅ **Exploitation scenario** giải thích rủi ro bảo mật
- ✅ **Secure remediation** với ví dụ code đã sửa an toàn
- ✅ **Prevention best practices** để phòng tránh lỗi tương tự

#### So sánh hiệu quả của các prompt

Sau khi test tất cả các scenario, hãy so sánh kết quả:

- **General prompts** cho coverage rộng nhưng có thể thiếu chiều sâu
- **Specialized prompts** cung cấp phân tích chi tiết cho từng loại vulnerability
- **Multi-file scans** giúp phát hiện các mối liên hệ và phụ thuộc về bảo mật giữa nhiều file
