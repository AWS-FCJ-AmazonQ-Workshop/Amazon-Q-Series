---
title: "Giới thiệu về Amazon Q Developer Security"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Giới thiệu về Amazon Q Developer Security

Amazon Q Developer là AI assistant thế hệ mới, tích hợp bảo mật ngay trong quá trình phát triển phần mềm[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[2]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/)
. Công cụ này giúp phát hiện, cảnh báo và đề xuất sửa lỗi bảo mật tự động khi bạn code, nhờ hàng nghìn security detectors cập nhật liên tục từ AWS[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html).

#### Tổng quan về Security Capabilities

- **Static Application Security Testing (SAST):** Phát hiện lỗi bảo mật phổ biến như SQL injection, XSS, OS command injection, path traversal...[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[4]](https://blog.getsetbuild.cloud/post/secure-coding-with-amazon-q/)

- **Secrets Detection:** Tự động tìm kiếm và cảnh báo khi phát hiện hardcoded passwords, API keys, AWS credentials trong code[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[5]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/code-reviews.html).

- **Infrastructure as Code (IaC) Scanning:** Kiểm tra cấu hình hạ tầng (CloudFormation, Terraform...) để phát hiện misconfiguration và vi phạm bảo mật[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[5]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/code-reviews.html).

#### Hiểu về Security Scanning Modes

Amazon Q Developer cung cấp hai chế độ security scanning chính để phù hợp với different workflows[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[6]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/start-scan.html):

- **Auto Scans (Real-time):** Quét tự động và cảnh báo ngay khi bạn viết code (chỉ có ở bản Pro).

- **Project Scans:** Quét toàn bộ project theo yêu cầu, phù hợp với kiểm tra định kỳ hoặc trước khi release.

Lưu ý: Nên duy trì Auto Scan để phát hiện sớm lỗ hổng, kết hợp Project Scan định kỳ để đảm bảo toàn bộ codebase an toàn.

#### Ứng dụng thực tiễn

- **Phát hiện lỗ hổng sớm:** Chủ động phát hiện và xử lý các vấn đề bảo mật trước khi code lên production.

- **Tự động hóa sửa lỗi:** Đề xuất bản sửa lỗi bảo mật tự động, giúp tiết kiệm thời gian và giảm rủi ro.

- **Đảm bảo tuân thủ tiêu chuẩn:** Code luôn đáp ứng các tiêu chuẩn bảo mật mới nhất của AWS và ngành công nghiệp.

#### Mục tiêu workshop

- ✅ Hiểu rõ vai trò và lợi ích của Amazon Q Developer Security
- ✅ Trải nghiệm thực tế các tính năng quét và sửa lỗi bảo mật
- ✅ Nắm best practices để bảo mật code xuyên suốt quá trình phát triển
- ✅ Phát triển kỹ năng sử dụng AI để nâng cao chất lượng và an toàn phần mềm
