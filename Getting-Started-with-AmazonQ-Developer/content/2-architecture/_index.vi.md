---
title: "Kiến trúc và cách hoạt động"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Kiến trúc tổng quan và tích hợp với IDE

Amazon Q Developer được thiết kế như một trợ lý AI tích hợp sâu vào môi trường phát triển phần mềm (IDE) phổ biến như Visual Studio Code và JetBrains. Người dùng có thể tương tác trực tiếp với Amazon Q ngay trong IDE thông qua các đề xuất mã đa dòng, chat nội tuyến, và các tác vụ tự động hóa phát triển phần mềm. Ngoài ra, Amazon Q còn hỗ trợ dòng lệnh (CLI), cho phép dịch ngôn ngữ tự nhiên sang lệnh bash, giúp tăng tốc các thao tác trên terminal.

_Hình minh họa tích hợp Amazon Q Developer trong Visual Studio Code_ (Placeholder)

#### Các ngôn ngữ lập trình được hỗ trợ

Amazon Q Developer hỗ trợ hơn 25 ngôn ngữ lập trình phổ biến, trong đó có:

- Python
- Java
- JavaScript
- C#
- TypeScript
- Go
- Ruby

Khả năng hiểu ngữ cảnh và cấu trúc dự án giúp Amazon Q tạo ra các đề xuất mã chính xác và phù hợp với từng ngôn ngữ cũng như phong cách lập trình của dự án[1][2].

#### Cách Amazon Q Developer tương tác với AWS SDK, CLI và các dịch vụ AWS khác

Amazon Q Developer không chỉ hỗ trợ viết và cải tiến mã mà còn tích hợp chặt chẽ với hệ sinh thái AWS:

- **AWS SDK & CLI:** Amazon Q có thể tạo và tối ưu hóa mã sử dụng AWS SDK, tự động viết các lệnh CLI hoặc chuyển đổi các thao tác trên AWS Management Console thành mã có thể tái sử dụng.
- **Tương tác với dịch vụ AWS:** Q Developer giúp thiết kế kiến trúc, phân tích chi phí, kiểm thử và triển khai các dịch vụ AWS như Lambda, S3, DynamoDB, v.v.
- **Tác tử tự động hóa:** Amazon Q có thể thực hiện chuỗi tác vụ phức tạp như tạo tài liệu, kiểm thử tự động, tái cấu trúc mã và nâng cấp phần mềm chỉ với một lệnh duy nhất[2][4][8].

#### Chi phí và các tier dịch vụ

Amazon Q Developer cung cấp các gói dịch vụ linh hoạt phù hợp với nhu cầu của cá nhân và doanh nghiệp:

- **Free Tier:** Cho phép trải nghiệm các tính năng cơ bản với giới hạn về số lượng đề xuất và truy vấn.
- **Professional Tier:** Cung cấp khả năng tùy chỉnh sâu hơn, hỗ trợ đa ngôn ngữ, tích hợp kho mã nội bộ, và các tính năng nâng cao như quét bảo mật, tác tử tự động hóa phức tạp[5].

Việc lựa chọn tier phù hợp giúp tối ưu chi phí đồng thời tận dụng tối đa các lợi ích từ Amazon Q Developer.

---

_Hình ảnh minh họa kiến trúc tổng quan và tích hợp hệ sinh thái AWS_ (Placeholder)

---

Phần này giúp bạn hiểu rõ cách Amazon Q Developer vận hành và tích hợp trong môi trường phát triển hiện đại, từ đó khai thác tối đa sức mạnh AI trong dự án của mình.

[1] https://aws.amazon.com/vi/q/developer/
[2] https://aws.amazon.com/vi/q/developer/features/
[3] https://ictvietnam.vn/amazon-q-developer-mo-rong-ho-tro-lap-trinh-bang-tieng-viet-69510.html
[4] https://aws.amazon.com/vi/q/developer/build/
[5] https://aws.amazon.com/vi/q/developer/pricing/
[6] https://www.sggp.org.vn/amazon-q-developer-mo-rong-ho-tro-lap-trinh-bang-tieng-viet-va-nhieu-ngon-ngu-khac-post791863.html
[7] https://dev.to/aws-builders/amazon-q-cli-de-su-dung-nhu-the-ma-toi-gio-minh-moi-dung-229b
[8] https://aws.amazon.com/vi/q/developer/operate/
