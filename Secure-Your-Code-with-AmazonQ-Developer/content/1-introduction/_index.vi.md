---
title: "Giới thiệu về Secure Code Với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Giới thiệu về Secure Code Với Amazon Q Developer

Chào mừng bạn đến với Workshop Secure Your Code With Amazon Q Developer! Đây là buổi thực hành về bảo mật mã nguồn bằng AI với Amazon Q Developer – trợ lý AI hội thoại giúp bạn hiểu, xây dựng và bảo vệ ứng dụng AWS hiệu quả[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[2]](https://aws.amazon.com/q/developer/features/).

Amazon Q Developer không chỉ hỗ trợ code completion mà còn có thể quét mã nguồn, phát hiện và đề xuất sửa các lỗ hổng bảo mật, cập nhật, debug và tối ưu code[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[3]](https://dev.to/__spyros/revolutionizing-code-security-how-amazon-q-developer-safeguards-modern-applications-19f7).

#### Mục tiêu workshop

Workshop này tập trung vào tính năng **Security Scanning (/review)** của Amazon Q Developer để phát hiện các vi phạm chính sách bảo mật và lỗ hổng trong mã nguồn của bạn, từ đó cải thiện chất lượng bảo mật tổng thể[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[4]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/). Amazon Q Developer sử dụng **Static Application Security Testing (SAST)**, **secrets detection**, **software composition analysis** và **Infrastructure as Code (IaC) scanning** để phát hiện các vấn đề bảo mật[[5]](https://www.blackduck.com/glossary/what-is-sast.html)[[6]](https://orca.security/glossary/secrets-detection/)[[7]](https://www.wiz.io/academy/iac-scanning).

Công cụ này được hỗ trợ bởi **Amazon CodeGuru Detector Library** với hàng nghìn detectors bảo mật trên nhiều ngôn ngữ lập trình khác nhau[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[8]](https://aws.amazon.com/blogs/aws/new-for-amazon-codeguru-reviewer-detector-library-and-security-detectors-for-log-injection-flaws/). Khi các chính sách bảo mật được cập nhật và các detector mới được thêm vào, Amazon Q tự động tích hợp để đảm bảo mã nguồn của bạn tuân thủ các chính sách mới nhất[[4]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/).

#### Tính năng Security Scanning

Amazon Q Developer có thể quét toàn bộ codebase của bạn hoặc tự động quét code khi bạn viết. Workshop này sẽ tập trung vào **project-based scanning** với khả năng quét lên đến **100 MB code** mỗi lần.

Công cụ này giúp phát hiện các vấn đề bảo mật như:

- **Cross-site scripting vulnerabilities (XSS)**: Chèn mã độc vào trang web.
- **Log injections**: Chèn dữ liệu độc hại vào log.
- **Loose file permissions**: Quyền truy cập file quá rộng.
- **Hardcoded credentials**: Lưu mật khẩu/API key trong mã nguồn.
- **SQL Injection**: Chèn mã SQL độc hại vào truy vấn.
- **Secrets exposure**: Lộ thông tin nhạy cảm trong code hoặc log.

#### Prompt Library

Amazon Q Developer hiện tại cho phép xây dựng thư viện các prompt thông dụng, được lưu trữ dưới dạng file Markdown trong thư mục **~/.aws/amazonq/prompts**. Điều này giúp tái sử dụng các prompt trên nhiều cuộc hội thoại và dự án khác nhau, đặc biệt hữu ích cho việc tạo các loại diagram như **Entity-Relationship (ER) diagram** hoặc **sequence diagram**.

#### Tại sao Workshop này quan trọng?

Phát hiện sớm lỗ hổng giúp giảm chi phí và công sức khắc phục. Amazon Q Developer hỗ trợ "**shift-left security**" - tích hợp bảo mật sớm trong vòng đời phát triển phần mềm (SDLC) thay vì xem xét bảo mật như một bước cuối cùng[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[4]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/).

Với khả năng phân tích tĩnh tiên tiến và machine learning, Amazon Q Developer không chỉ phát hiện lỗ hổng mà còn cung cấp **auto-generated code fixes** cho các lỗ hổng đã xác định[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[3]](https://dev.to/__spyros/revolutionizing-code-security-how-amazon-q-developer-safeguards-modern-applications-19f7). Điều này giúp các developer không chỉ biết vấn đề là gì mà còn biết cách khắc phục một cách hiệu quả.

Workshop này sẽ cung cấp cho bạn kiến thức thực tiễn và kỹ năng cần thiết để sử dụng Amazon Q Developer một cách hiệu quả trong việc xây dựng các ứng dụng an toàn và bảo mật hơn.
