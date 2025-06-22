---
title: "Kiến trúc và cách hoạt động"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Kiến trúc tổng quan & tích hợp IDE

Amazon Q Developer là AI assistant tích hợp sâu vào các IDE phổ biến như Visual Studio Code, JetBrains. Developer có thể tương tác trực tiếp với Q ngay trong IDE qua code suggestion đa dòng, chat inline, và tự động hóa task. Ngoài ra, Q hỗ trợ CLI, dịch natural language sang bash command, tăng tốc thao tác terminal.

![Amazon Q in VSCode](/images/2-architecture/image.png?width=90pc)

*Hình 1: Minh họa tích hợp Amazon Q Developer trong Visual Studio Code*

#### Hỗ trợ đa ngôn ngữ lập trình

Amazon Q Developer support hơn 25 ngôn ngữ lập trình phổ biến:

- Python
- Java
- JavaScript
- C#
- TypeScript
- Go
- Ruby

Q hiểu context & project structure, tạo code suggestion chuẩn xác, phù hợp từng ngôn ngữ và coding style của dự án [\[1\]](https://aws.amazon.com/vi/q/developer/) [\[2\]](https://aws.amazon.com/vi/q/developer/features/).

#### Tương tác với AWS SDK, CLI & dịch vụ AWS

Q Developer không chỉ hỗ trợ code mà còn tích hợp chặt với AWS ecosystem:

- **AWS SDK & CLI:** Q tự động generate, optimize code dùng AWS SDK, viết CLI command, hoặc convert thao tác trên AWS Console thành reusable code.
- **AWS Services:** Hỗ trợ design kiến trúc, phân tích cost, test, deploy các dịch vụ như Lambda, S3, DynamoDB, v.v.
- **Automation Agent:** Q có thể tự động hóa chuỗi task như generate docs, auto test, refactor, upgrade chỉ với 1 prompt [\[2\]](https://aws.amazon.com/vi/q/developer/features/) [\[4\]](https://aws.amazon.com/vi/q/developer/build/) [\[8\]](https://aws.amazon.com/vi/q/developer/operate/).

#### Pricing & Service tiers

Amazon Q Developer có nhiều tier phù hợp cá nhân & doanh nghiệp:

- **Free Tier:** Trải nghiệm tính năng cơ bản, giới hạn số suggestion & query.
- **Professional Tier:** Tùy chỉnh sâu, đa ngôn ngữ, tích hợp repo nội bộ, quét bảo mật, automation nâng cao [\[5\]](https://aws.amazon.com/vi/q/developer/pricing/).

![Amazon Q Developer Pricing Tiers](/images/2-architecture/image-1.png?width=70pc)

*Hình 2: Các tier dịch vụ Amazon Q Developer*

Chọn tier phù hợp để tối ưu chi phí và tận dụng tối đa sức mạnh Q Developer.