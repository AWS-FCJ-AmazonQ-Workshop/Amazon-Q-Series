+++
title = "Bảo Mật Code Của Bạn Với Amazon Q Developer"
date = 2024
weight = 1
chapter = false
+++

# Bảo Mật Code Của Bạn Với Amazon Q Developer

Amazon Q có thể quét codebase của bạn để tìm các lỗ hổng bảo mật và các vấn đề về chất lượng mã nhằm cải thiện trạng thái bảo mật của các ứng dụng của bạn trong suốt chu kỳ phát triển. Bạn có thể bắt đầu quét toàn bộ codebase, phân tích tất cả các tệp trong dự án hoặc không gian làm việc cục bộ của bạn, hoặc bật tính năng tự động quét để đánh giá mã của bạn khi bạn viết.

Điều này giúp các ứng dụng của bạn an toàn và có khả năng phục hồi tốt hơn bằng cách làm nổi bật các vấn đề bảo mật như các lỗ hổng cross-site scripting, log injection, quyền truy cập tệp lỏng lẻo, thông tin đăng nhập được mã hóa cứng và hơn thế nữa. Các vấn đề bảo mật được phát hiện càng sớm thì càng ít công việc và nỗ lực cần thiết để khắc phục chúng.

Quá trình quét được hỗ trợ bởi [Bộ phát hiện Bảo mật](https://docs.aws.amazon.com/codeguru/detector-library/) từ Thư viện Bộ phát hiện Amazon CodeGuru. Khi các chính sách bảo mật được cập nhật và các bộ phát hiện được thêm vào, quá trình quét sẽ tự động tích hợp các bộ phát hiện mới để đảm bảo mã của bạn tuân thủ các chính sách cập nhật nhất.

Amazon Q Developer phát hiện các vi phạm chính sách bảo mật và các lỗ hổng trong mã của bạn bằng cách kiểm thử bảo mật ứng dụng tĩnh (SAST), phát hiện bí mật và quét cơ sở hạ tầng dưới dạng mã (IaC). Các vấn đề bảo mật được tìm thấy trong quá trình quét sẽ được làm nổi bật trong bảng Problems (Vấn đề) trong VS Code.

Trong phần này, chúng ta sẽ sử dụng các tính năng Quét Bảo mật của Q Developer để phát hiện mã không an toàn.

{{% notice note %}}
Module này cố ý bao gồm các đoạn mã sẽ kích hoạt các phát hiện quét bảo mật. Các đoạn mã trong module này chỉ nên được sử dụng cho mục đích trình diễn.
{{% /notice %}}

Amazon Q có thể quét toàn bộ codebase của bạn hoặc tự động quét mã của bạn khi bạn viết. Cho mục đích của workshop này, chúng ta sẽ sử dụng quét dựa trên dự án. Có thể quét tối đa 100 MB mã cùng một lúc.

#### Scan dự án của bạn

1. Chọn chữ Amazon Q từ vùng hình chữ nhật ở dưới cùng cửa sổ IDE.
2. Một cửa sổ thả xuống sẽ xuất hiện ở trên cùng, từ đó người dùng có thể chọn **Run Project Scan**.

![autoscans](/images/1/autoscans.png?width=90pc)
