+++
title = "Bắt đầu với Amazon Q Developer"
date = 2024
weight = 1
chapter = false
authors = ["Tran Doan Cong Ly", "Van Hoang Kha", "Minh Nghia"]
+++

# Bắt đầu với Amazon Q Developer

#### Amazon Q Developer là gì?

**ℹ️ Thông tin**: Amazon Q Developer là trợ lý hội thoại thông minh được hỗ trợ bởi công nghệ trí tuệ nhân tạo sinh (Generative AI), giúp người dùng hiểu rõ, xây dựng, mở rộng và vận hành các ứng dụng trên nền tảng AWS. Công cụ này cung cấp những câu trả lời chính xác, phù hợp với ngữ cảnh và có tính khả thi cao về kiến trúc AWS, quản lý tài nguyên, các phương pháp thực hành tốt nhất, tài liệu hướng dẫn và dịch vụ hỗ trợ.

Khi được tích hợp vào môi trường phát triển (IDE), Amazon Q Developer mang đến sự hỗ trợ toàn diện cho việc phát triển phần mềm thông qua các tính năng:
- Tương tác và giải thích mã nguồn một cách trực quan
- Tự động hoàn thiện mã nguồn trong quá trình viết
- Sinh tạo mã nguồn mới theo yêu cầu
- Phát hiện và quét các lỗ hổng bảo mật
- Tối ưu hóa và cải tiến mã nguồn hiện có

**ℹ️ Thông tin**: Amazon Q Developer được xây dựng trên nền tảng Amazon Bedrock - dịch vụ được quản lý toàn diện, cung cấp các mô hình nền tảng (Foundation Models) thông qua giao diện lập trình ứng dụng (API). Hệ thống đã được tăng cường với kho nội dung AWS chất lượng cao nhằm đưa ra những câu trả lời hoàn chỉnh, khả thi và có nguồn tham chiếu rõ ràng.

{{% notice note %}}
**🔒 Lưu ý về bảo mật**: Amazon Q Developer được phát triển dựa trên nền tảng Amazon Bedrock và tích hợp tính năng phát hiện lạm dụng tự động nhằm đảm bảo tính an toàn, bảo mật và việc sử dụng AI một cách có trách nhiệm.
{{% /notice %}}

#### Hướng dẫn bắt đầu sử dụng Amazon Q Developer

Để khởi động quá trình sử dụng Amazon Q Developer, bạn có thể truy cập thông qua các phương thức sau đây:

#### Ứng dụng và trang web của AWS

1. Cấp [các quyền cần thiết](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security_iam_id-based-policy-examples.html) cho định danh IAM của bạn
2. Nhấp vào biểu tượng Amazon Q để bắt đầu tương tác trong các môi trường:
   - Bảng điều khiển quản lý AWS (AWS Management Console)
   - Trang web tài liệu hướng dẫn AWS
   - Trang web chính thức của AWS
   - Ứng dụng di động AWS Console

**ℹ️ Thông tin**: Để tham khảo hướng dẫn chi tiết, vui lòng xem [Sử dụng Amazon Q Developer trên các ứng dụng và trang web AWS](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-on-aws.html).

#### Môi trường phát triển tích hợp (IDE)

Tải xuống tiện ích mở rộng Amazon Q và đăng nhập bằng AWS Builder ID (không yêu cầu tài khoản AWS) để sử dụng miễn phí.

- {{% button href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.amazon-q-vscode" %}} **Tải xuống Amazon Q cho Visual Studio Code**{{% /button %}}<br>

  _Hướng dẫn cài đặt và cấu hình:_
  {{< youtube i0zQpJPfSdU >}}

- {{% button href="https://plugins.jetbrains.com/plugin/24267-amazon-q/" %}} **Tải xuống Amazon Q cho JetBrains IDEs**{{% /button %}}<br>

  _Hướng dẫn cài đặt và cấu hình:_
  {{< youtube -iQfIhTA4J0 >}}

- {{% button href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.AWSToolkitforVisualStudio2022" %}} Tải xuống Amazon Q trong AWS Toolkit cho Visual Studio{{% /button %}}<br>

- {{% button href="https://marketplace.eclipse.org/content/amazon-q" %}} Tải xuống Amazon Q cho Eclipse IDEs (Phiên bản xem trước){{% /button %}}

**ℹ️ Thông tin**: Nhấp vào biểu tượng Amazon Q trong IDE để bắt đầu tương tác hoặc khởi tạo quy trình phát triển. Để biết thêm thông tin chi tiết, vui lòng tham khảo [Cài đặt tiện ích mở rộng hoặc plugin Amazon Q Developer trong IDE](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-in-IDE-setup.html).

#### Giao diện dòng lệnh (Command Line Interface)

Tải xuống Amazon Q Developer để sử dụng qua dòng lệnh:

- [macOS](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-macos)
- [Linux AppImage](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-appimage)
- [Ubuntu](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-ubuntu)

**ℹ️ Thông tin**: Để tham khảo hướng dẫn chi tiết, vui lòng xem [Sử dụng Amazon Q Developer qua giao diện dòng lệnh](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line.html).

#### Ứng dụng nhắn tin

Để sử dụng Amazon Q Developer trong các ứng dụng nhắn tin:

1. Gán chính sách được quản lý [AmazonQDeveloperAccess](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/managed-policy.html#amazonq-policy-fullaccess) cho định danh IAM của bạn
2. Thiết lập các biện pháp bảo vệ kênh cho ứng dụng Microsoft Teams hoặc Slack

**ℹ️ Thông tin**: Để tham khảo hướng dẫn chi tiết, vui lòng xem [Tương tác với Amazon Q Developer trong các ứng dụng nhắn tin](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-in-chat-applications.html).

#### Bảng giá Amazon Q Developer

Amazon Q Developer cung cấp các gói dịch vụ:
- Gói miễn phí với giới hạn sử dụng hàng tháng
- Gói đăng ký Amazon Q Developer Pro

**ℹ️ Thông tin**: Để biết thông tin chi tiết về bảng giá, vui lòng tham khảo [Bảng giá Amazon Q Developer](https://aws.amazon.com/q/developer/pricing).