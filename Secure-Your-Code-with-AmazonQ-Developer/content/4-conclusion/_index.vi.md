---
title: "Kết luận và Bước tiếp theo"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4. </b> "
---

#### Tóm tắt

Trong workshop này, chúng ta đã học cách sử dụng Amazon Q Developer để phát hiện các vi phạm chính sách bảo mật và lỗ hổng trong mã nguồn thông qua kiểm thử bảo mật ứng dụng tĩnh (SAST), phát hiện secrets, phân tích thành phần phần mềm và quét Infrastructure as Code (IaC). Các lần quét bảo mật của Amazon Q Developer không chỉ xác định lỗ hổng mà còn đề xuất cải tiến để nâng cao chất lượng và bảo mật mã nguồn của bạn.

#### Lợi ích khi bảo mật code của bạn với Amazon Q Developer

Tích hợp Amazon Q Developer trực tiếp vào môi trường phát triển, đặc biệt là trong IDE, mang lại nhiều lợi ích quan trọng:

Phát hiện theo thời gian thực: Developer nhận được phản hồi ngay lập tức về các lỗ hổng, vi phạm tiêu chuẩn mã hóa và lỗi cú pháp khi viết mã, giúp học hỏi và sửa lỗi ngay tại chỗ.

- **Phát hiện lỗ hổng sớm**: Phát hiện vấn đề sớm giúp giảm chi phí và công sức khắc phục, thường trước khi merge code hoặc triển khai.
- **Thực hành mã hóa an toàn hơn**: Các đề xuất khắc phục giúp developer liên tục áp dụng các thực tiễn lập trình bảo mật tốt nhất.
- **Giảm thời gian khắc phục**: Xử lý vấn đề bảo mật ngay trong quá trình phát triển nhanh hơn và tiết kiệm chi phí hơn so với sửa sau khi triển khai.

#### Tài nguyên học tập & cộng đồng

- Tài liệu & hướng dẫn AWS: https://aws.amazon.com/codeguru/
- OWASP Top Ten: https://owasp.org/www-project-top-ten/
- Blog bảo mật AWS & Diễn đàn Developer để cập nhật và hỗ trợ cộng đồng.

#### Hướng phát triển nâng cao & tích hợp bảo mật sâu

- Tích hợp Amazon Q Developer với pipeline CI/CD để kiểm tra bảo mật tự động.
- Kết hợp với AWS Security Hub và Amazon Inspector để bảo mật đám mây toàn diện.
- Sử dụng quét IaC để bảo vệ các template hạ tầng đám mây.
- Tùy chỉnh thư viện prompt phù hợp với quy trình làm việc của nhóm.

#### Tài liệu tham khảo

- [Amazon Q Developer Security Scans](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)
- [Amazon Q Developer Code Reviews](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/code-reviews.html)
- [Saving prompts to a library for use with Amazon Q Developer chat](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/context-prompt-library.html)
- [Code Security Scanning with Amazon Q Developer](https://aws.amazon.com/vi/blogs/devops/code-security-scanning-with-amazon-q-developer/)
- [Amazon Q Developer Context Features](https://aws.amazon.com/vi/blogs/devops/amazon-q-developers-new-context-features/)
- [Secure Coding with Amazon Q](https://blog.getsetbuild.cloud/post/secure-coding-with-amazon-q/)
- [AWS Well-Architected Security Pillar](https://docs.aws.amazon.com/wellarchitected/latest/security-pillar/welcome.html)
- [AWS Security Best Practices](https://aws.amazon.com/vi/architecture/security-identity-compliance/?cards-all.sort-by=item.additionalFields.sortDate&cards-all.sort-order=desc&awsf.content-type=*all&awsf.methodology=*all)
- [AWS Prescriptive Guidance: Security](https://docs.aws.amazon.com/prescriptive-guidance/latest/security-reference-architecture/welcome.html)
- [OWASP Top 10 Web Application Security Risks](https://owasp.org/www-project-top-ten/)
- [Securing Your Code Workshop](https://catalog.us-east-1.prod.workshops.aws/workshops/fe2c944b-f014-44d6-a243-1fc2e30b5f73/en-US)

Hãy tiếp tục thực hành với Amazon Q Developer và tận dụng AI để không ngừng nâng cao kỹ năng lập trình và bảo mật của bạn. Cảm ơn bạn đã tham gia và hãy tiếp tục hành trình xây dựng các ứng dụng an toàn, vững chắc hơn!

![Security Journey](/images/7/conclusion-Amazon-Q.png)
