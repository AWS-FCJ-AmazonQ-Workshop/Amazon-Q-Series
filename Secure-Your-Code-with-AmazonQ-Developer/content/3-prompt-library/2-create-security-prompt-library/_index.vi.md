---
title: "Tạo Security Prompt Library"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

Bây giờ chúng ta sẽ tạo một thư viện prompt chuyên biệt cho security analysis. Các prompt này sẽ giúp chuẩn hóa quá trình đánh giá bảo mật và đảm bảo phát hiện đầy đủ các vulnerabilities.

#### Tạo Prompt Multi-Vulnerability-Scan

1. Trong IDE của bạn, mở cửa sổ chat Amazon Q.

2. Gõ **@**, và chọn **Prompts**.

![Prompt-Library](/images/7/prompt-lib-1.png?width=90pc)
_Hình 1: Chọn Prompts trong cửa sổ chat với Amazon Q_

3. Chọn **Create a new prompt**.

![Prompt-Library](/images/7/prompt-lib-2.png?width=90pc)
_Hình 2: Tạo prompt mới_

4. Ở **Prompt name**, nhập tên prompt như sau `Multi-Vulnerability-Scan` và nhấn **Enter**.

![Prompt-Library](/images/7/prompt-lib-3.png?width=90pc)
_Hình 3: Đặt tên cho prompt mới_

Amazon Q sẽ tạo một file prompt tên **Multi-Vulnerability-Scan.md** trong thư mục _~/.aws/amazonq/prompts_, và mở file này trong IDE của bạn.

5. Trong file prompt, thêm nội dung chi tiết như sau:

```
Scan Python Flask application for these vulnerabilities:
- SQL injection in database queries
- Open redirect in route handlers
- Command injection in subprocess calls
- Path traversal in file operations
- Privilege escalation in access controls
- Hardcoded credentials and API keys

Report: vulnerability type, line number, risk level, exploit scenario, secure code fix.
```

6. Lưu file prompt.

#### Tạo Prompt Database-Security-Check

Lặp lại các bước trên với tên prompt là `Database-Security-Check` và nội dung sau:

```
Focus on database security issues:
- SQL injection via string concatenation
- Unsafe query construction
- Missing parameterized queries
- Database credential exposure

Provide secure SQLite/PostgreSQL examples.

```

#### Tạo Prompt Web-App-Security-Audit

Tạo thêm một prompt tên `Web-App-Security-Audit` với nội dung sau:

```
Audit Flask web application for:
- Unvalidated redirects
- Command injection via user input
- File path manipulation
- Missing input sanitization
- Unsafe subprocess execution

Include Flask security best practices.
```

#### Sử Dụng Security Prompts

1. Trong IDE của bạn, mở cửa sổ chat Amazon Q.

2. Gõ **@**, và chọn **Prompts**.

3. Chọn prompt đã lưu, ví dụ **Multi-Vulnerability-Scan**.

4. (Tùy chọn) Trong ô chat, bạn có thể thêm chi tiết hoặc ngữ cảnh nếu cần. Ví dụ:

```
@Multi-Vulnerability-Scan analyze the @vulnerable_app.py using the files in the @security-test folder
```

5. Gửi prompt và chờ Amazon Q trả về kết quả.

![Prompt-Library](/images/7/prompt-lib-4.png?width=90pc)
_Hình 4: Sử dụng prompt bảo mật để kiểm tra lỗ hổng với Amazon Q_

Thư viện security prompt của bạn đã sẵn sàng để kiểm thử vulnerabilities toàn diện ở phần tiếp theo.
