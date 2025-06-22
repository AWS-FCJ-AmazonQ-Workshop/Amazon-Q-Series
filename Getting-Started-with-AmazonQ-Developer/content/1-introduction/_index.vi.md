---
title: "Giới thiệu về Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Tổng quan về Amazon Q Developer

Amazon Q Developer là AI assistant thế hệ mới cho dev, giúp tăng tốc và tối ưu toàn bộ software development lifecycle. Build trên Amazon Bedrock, Q Developer hỗ trợ lập trình viên từ code, refactor, test đến upgrade app trên AWS – tất cả đều tự động, smart[\[1\]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html).

Q Developer tích hợp sâu với các IDE hot như Visual Studio Code, JetBrains, và cả CLI, cho phép bạn code trực tiếp với code suggestion đa dòng, chat AI realtime, và hỗ trợ bash tự nhiên[\[2\]](https://www.maginative.com/article/amazon-unveils-q-developer-bringing-generative-ai-to-boost-software-development-productivity/).

#### Tinh năng chính

- **Chat:** Hỗ trợ hỏi đáp về code, giải thích code, refactor, sinh code mới từ đầu, và tư vấn về AWS, kiến trúc, best practices. Có thể sử dụng trực tiếp trên IDE, CLI hoặc web[\[1\]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html)[\[2\]](https://aws.amazon.com/q/developer/).
- **Explore:** Truy vấn và tìm hiểu tài nguyên AWS, filter và hỏi đáp bằng ngôn ngữ tự nhiên (chủ yếu trên web/AWS Console)[\[1\]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html).
- **Suggestions (Code Completion):** Đề xuất code thông minh, tự động gợi ý khi bạn gõ trong IDE hoặc CLI, giúp tiết kiệm thời gian và giảm lỗi[\[1\]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html)[\[2\]](https://aws.amazon.com/q/developer/).
- **Agent:** Thực hiện các tác vụ phức tạp như mô tả, refactor lớn trên nhiều file, tạo pull request, hoặc tự động hóa quy trình phát triển chỉ từ một prompt duy nhất[\[2\]](https://aws.amazon.com/q/developer/).
- **Code Scans:** Quét và phát hiện lỗ hổng bảo mật, lỗi tiềm ẩn trong code, giải thích nguyên nhân và đề xuất bản sửa lỗi tự động[\[1\]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html)[\[2\]](https://aws.amazon.com/q/developer/).
- **Transformation:** Tự động refactor hoặc nâng cấp toàn bộ dự án khi chuyển đổi phiên bản ngôn ngữ (ví dụ Java 8 → Java 17) hoặc porting nền tảng (.NET Windows → Linux)[\[2\]](https://aws.amazon.com/q/developer/).
- **Hỗ trợ đa nền tảng:** Sử dụng được trên Web, IDE (Visual Studio Code, JetBrains, Visual Studio, Eclipse Preview), và CLI (MacOS, Linux, Ubuntu)[\[1\]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html)[\[2\]](https://aws.amazon.com/q/developer/).
- **Model Context Protocol (MCP):** Hỗ trợ MCP trên CLI (update 4/2025), cho phép AI truy cập công cụ ngoài, dữ liệu và API theo chuẩn bảo mật, giúp workflow phát triển phong phú và tùy biến hơn[\[4\]](https://aws.amazon.com/about-aws/whats-new/2025/04/amazon-q-developer-cli-model-context-protocol/).

![Chat with Amazon Q Developer on VS Code](/images/1-introduction/image.png?width=40pc)

*Hình 1: Các tính năng nổi bật của Amazon Q Developer*

#### Ứng dụng thực tiễn

- **Boost productivity:** Các công ty như BT Group, National Australia Bank ghi nhận accept code suggestion 37%-50%, productivity tăng 20-40%[\[3\]](https://www.missioncloud.com/blog/what-is-amazon-q-and-how-does-it-unlock-productivity-for-businesses-and-developers).
- **Upgrade & migrate app:** Tự động nâng version Java, port .NET, tiết kiệm thời gian, giảm chi phí.
- **Optimize AWS:** Phân tích cost, kiến trúc, vận hành AWS hiệu quả qua chat và đề xuất chuyên sâu.
- **Generate docs & diagrams:** Tự động tạo flowchart, class diagram, sequence diagram để hiểu hệ thống[\[5\]](https://aws.amazon.com/blogs/dotnet/generate-code-documentation-using-amazon-q-developer/).

#### Mục tiêu workshop

- ✅ Hiểu rõ vai trò, lợi ích của Amazon Q Developer.
- ✅ Trải nghiệm thực tế các tính năng chính, tích hợp Q Developer vào workflow.
- ✅ Nắm best practices để tận dụng AI tối đa khi code, refactor, upgrade.
- ✅ Phát triển kỹ năng dùng Q Developer để tăng productivity, cải thiện chất lượng & bảo mật phần mềm.