+++
title = "Getting started with Amazon Q Developer"
date = 2024
weight = 1
chapter = false
+++

# Bắt đầu với Amazon Q Developer

### Amazon Q Developer là gì?

Amazon Q Developer là một trợ lý đàm thoại được hỗ trợ bởi trí tuệ nhân tạo (AI) tạo sinh, có thể giúp bạn hiểu, xây dựng, mở rộng và vận hành các ứng dụng AWS. Bạn có thể đặt câu hỏi về kiến trúc AWS, tài nguyên AWS của bạn, các phương pháp hay nhất, tài liệu, hỗ trợ và hơn thế nữa. Amazon Q liên tục cập nhật các khả năng của mình để câu hỏi của bạn nhận được câu trả lời phù hợp và hữu ích nhất theo ngữ cảnh.

Khi được sử dụng trong một môi trường phát triển tích hợp (IDE), Amazon Q cung cấp hỗ trợ phát triển phần mềm. Amazon Q có thể trò chuyện về mã, cung cấp các gợi ý hoàn thành mã trực tiếp, tạo mã hoàn toàn mới, quét mã của bạn để tìm các lỗ hổng bảo mật, đồng thời thực hiện các nâng cấp và cải tiến mã, chẳng hạn như cập nhật ngôn ngữ, gỡ lỗi và tối ưu hóa.

Amazon Q được hỗ trợ bởi Amazon Bedrock, một dịch vụ được quản lý hoàn toàn cung cấp các mô hình nền tảng (FMs) thông qua API. Mô hình cung cấp sức mạnh cho Amazon Q đã được tăng cường bằng nội dung AWS chất lượng cao để cung cấp cho bạn các câu trả lời đầy đủ, hữu ích và có nguồn tham khảo hơn nhằm đẩy nhanh quá trình xây dựng trên AWS.

{{% notice note %}}
Được hỗ trợ bởi Amazon Bedrock: Amazon Q Developer được xây dựng trên Amazon Bedrock và bao gồm tính năng tự động phát hiện lạm dụng được triển khai trong Amazon Bedrock để đảm bảo an toàn, bảo mật và sử dụng AI có trách nhiệm.
{{% /notice %}}

### Bắt đầu với Amazon Q Developer

Để nhanh chóng bắt đầu sử dụng Amazon Q, bạn có thể truy cập theo các cách sau:

#### AWS apps and websites

Thêm [các quyền cần thiết](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security_iam_id-based-policy-examples.html) vào định danh IAM của bạn, sau đó chọn biểu tượng Amazon Q để bắt đầu trò chuyện trong AWS Management Console, trang web Tài liệu AWS, trang web AWS hoặc Ứng dụng di động AWS Console. Để biết thêm thông tin, hãy xem [Sử dụng Amazon Q Developer trên các ứng dụng và trang web AWS](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-on-aws.html).

#### IDEs

Tải xuống tiện ích mở rộng Amazon Q và sử dụng AWS Builder ID của bạn (không yêu cầu tài khoản AWS) để đăng nhập miễn phí.

- {{% button href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.amazon-q-vscode" %}} **Tải xuống Amazon Q trong Visual Studio Code**{{% /button %}}<br>

  _Hướng dẫn Cài đặt và Cấu hình:_
  {{< youtube i0zQpJPfSdU >}}

- {{% button href="https://plugins.jetbrains.com/plugin/24267-amazon-q/" %}} **Tải xuống Amazon Q trong JetBrains IDE**{{% /button %}}<br>

  _Hướng dẫn Cài đặt và Cấu hình:_
  {{< youtube -iQfIhTA4J0 >}}

- {{% button href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.AWSToolkitforVisualStudio2022" %}} Tải xuống Amazon Q trong AWS Toolkit for Visual Studio{{% /button %}}<br>

- {{% button href="https://marketplace.eclipse.org/content/amazon-q" %}} Tải xuống Amazon Q trong Eclipse IDE (Bản xem trước){{% /button %}}

Từ IDE của bạn, chọn biểu tượng Amazon Q để bắt đầu trò chuyện hoặc khởi tạo quy trình phát triển. Để biết thêm thông tin, hãy xem [Cài đặt tiện ích mở rộng hoặc plugin Amazon Q Developer trong IDE của bạn](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-in-IDE-setup.html).

#### Command line

Tải xuống Amazon Q cho command line cho [macOS](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-macos)

DTải xuống Amazon Q cho command line cho [Linux AppImage](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-appimage)

Tải xuống Amazon Q cho command line cho [Ubuntu](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-ubuntu)

Để biết thêm thông tin, hãy xem [Sử dụng Amazon Q Developer trên dòng lệnh](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line.html).

#### Amazon Q Developer trong các ứng dụng trò chuyện

Thêm chính sách được quản lý [AmazonQDeveloperAccess](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/managed-policy.html#amazonq-policy-fullaccess) vào định danh IAM của bạn và các biện pháp bảo vệ kênh cho các ứng dụng Microsoft Teams hoặc Slack. Để biết thêm thông tin, hãy xem [Trò chuyện với Amazon Q Developer trong các ứng dụng trò chuyện](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-in-chat-applications.html).

### Giá Amazon Q Developer

Amazon Q Developer có sẵn thông qua gói Miễn phí và gói đăng ký Amazon Q Developer Pro. Để biết thêm thông tin, hãy xem [Amazon Q Developer pricing](https://aws.amazon.com/q/developer/pricing).
