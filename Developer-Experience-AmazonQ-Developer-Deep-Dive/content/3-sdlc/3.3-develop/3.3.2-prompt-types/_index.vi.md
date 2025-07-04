---
title: "Kỹ thuật Prompt cho việc tạo mã"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.3.2. </b> "
---

Kỹ thuật prompt hiệu quả là rất quan trọng để có được kết quả tốt nhất từ Amazon Q Developer. Phần này khám phá các kỹ thuật và chiến lược prompting khác nhau nhằm tối đa hóa chất lượng, độ chính xác và sự phù hợp của việc tạo mã.

#### Tổng quan

Hiểu cách tạo prompt hiệu quả sẽ giúp bạn:
- **Tạo mã chính xác hơn** phù hợp với yêu cầu của bạn
- **Giảm thời gian lặp lại** bằng cách có kết quả tốt hơn ngay lần đầu
- **Tận dụng ngữ cảnh hiệu quả** để có gợi ý thông minh hơn
- **Tối ưu workflow phát triển** thông qua prompting chiến lược

#### Những gì bạn sẽ học được

Phần này bao gồm các chiến lược prompting toàn diện:

- [Prompt based on function name](3.3.2.1-function-name-prompt/)
- [Prompt based on single line comment](3.3.2.2-single-line-comment/)
- [Prompt based on single line directional prompt](3.3.2.3-single-line-prompt/)
- [Prompt based on multi line comment](3.3.2.4-multi-line-comment/)
- [Prompt based on multi line directional prompt](3.3.2.5-multi-line-prompt/)
- [Variable Names & Standards](3.3.2.6-variable-names-standards/)
- [Considerations](3.3.2.7-considerations/)

#### Nguyên tắc cơ bản của Prompt Engineering

##### Context là vua
Amazon Q Developer hoạt động tốt nhất khi được cung cấp:
- Mục tiêu và ràng buộc rõ ràng
- Ngữ cảnh mã liên quan
- Yêu cầu và pattern cụ thể
- Mô tả hành vi mong đợi

##### Progressive Enhancement
Bắt đầu với prompt đơn giản và dần thêm độ phức tạp:
1. **Basic Function**: Chức năng đơn giản, rõ ràng
2. **Add Constraint**: Bao gồm xử lý lỗi, validation
3. **Specify Pattern**: Yêu cầu design pattern hoặc kiến trúc cụ thể
4. **Include Example**: Cung cấp mẫu input/output khi hữu ích

##### Nhận thức về Ngôn ngữ và Framework
Amazon Q Developer thích ứng với:
- Quy ước ngôn ngữ lập trình
- Pattern cụ thể của framework
- Cấu trúc dự án và dependencies
- Style và tiêu chuẩn mã hiện có

{{% notice tip %}}
**Mẹo chuyên nghiệp**: Kết hợp nhiều kỹ thuật prompting để có kết quả tối ưu. Ví dụ, sử dụng tên hàm mô tả với comment hỗ trợ để cung cấp cả intent và chi tiết implementation.
{{% /notice %}}

#### Bắt đầu

Mỗi phần con cung cấp ví dụ chi tiết và thực hành trực tiếp với các cách tiếp cận prompting khác nhau. Làm việc qua chúng một cách tuần tự để xây dựng kỹ năng prompt engineering của bạn một cách có hệ thống.

Sẵn sàng thành thạo prompt engineering? Hãy bắt đầu với function name prompt!