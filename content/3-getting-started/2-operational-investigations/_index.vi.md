+++
title = "Điều tra vận hành với Amazon Q Developer"
date = 2024
weight = 2
chapter = false
pre = "<b>3.2 </b>"
+++

#### Amazon Q Developer Điều tra vận hành là gì?

**ℹ️ Thông tin**: Tính năng điều tra vận hành của Amazon Q giúp bạn nhanh chóng điều tra và giải quyết các sự cố bằng cách hiển thị thông tin liên quan, tận dụng sức mạnh của công nghệ AI tạo sinh. Amazon Q sẽ quét các số liệu, nhật ký, dấu vết, sự kiện triển khai và dữ liệu khác để tạo ra các giả thuyết về nguyên nhân gốc rễ và thông tin chi tiết có thể thực hiện được.

#### Bắt đầu

**💡 Mẹo chuyên nghiệp**: Để bắt đầu sử dụng tính năng điều tra vận hành:

1. Mở [CloudWatch console](https://console.aws.amazon.com/cloudwatch/)
2. Trong ngăn điều hướng bên trái:
   - Chọn **AI Operations**
   - Chọn **Investigations**
   - Chọn **Configure for this account**

**⚠️ Cảnh báo**: Để tạo nhóm điều tra và thiết lập các điều tra vận hành Amazon Q Developer, bạn phải đăng nhập vào một principal IAM có chính sách **AIOpsConsoleAdminPolicy** hoặc **AdministratorAccess** được đính kèm, hoặc vào một tài khoản có quyền tương tự. Cài đặt trong nhóm điều tra giúp bạn quản lý tập trung các thuộc tính chung của các cuộc điều tra của bạn.

![Investigations-1](/images/4/investigations-1.png?width=90pc)

4. Chọn thời gian lưu giữ cho các cuộc điều tra. Mặc định là 90 ngày.
5. Bạn có thể tùy chọn tùy chỉnh cài đặt mã hóa. Ví dụ: nếu bạn muốn sử dụng khóa do khách hàng quản lý thay vì khóa mặc định do AWS cung cấp. Để biết thêm thông tin, xem [Mã hóa dữ liệu điều tra](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-Security.html#Investigations-KMS).

![Investigations-2](/images/4/investigations-2.png?width=90pc)

6. (Tùy chọn) Phần truy cập người dùng của trình hướng dẫn bắt đầu giúp bạn hiểu cách thiết lập quyền thích hợp cho các vai trò người dùng khác nhau tương tác với điều tra vận hành Amazon Q Developer. (Liên kết sẽ đưa bạn đến tài liệu với thêm thông tin) AWS cung cấp ba chính sách IAM được quản lý: **AIOpsConsoleAdminPolicy** cho quản trị viên, **AIOpsOperatorAccess** cho người dùng cần bắt đầu và quản lý các cuộc điều tra, và **AIOpsReadOnlyAccess** cho người dùng chỉ cần xem thông tin.

![Investigations-3](/images/4/investigations-3.png?width=90pc)

7. Bạn có thể tùy chọn kết nối điều tra vận hành Amazon Q Developer với IAM Identity Center. Bằng cách tích hợp với IAM Identity Center, bạn có thể quy các đề xuất được thêm vào nguồn cấp dữ liệu điều tra cho từng người dùng. Để biết thêm thông tin, vui lòng xem [liên kết này](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-Integrations.html#Investigations-Integrations-IDC).

![Investigations-4](/images/4/investigations-4.png?width=90pc)

8. Chọn **Next** để tiếp tục
9. Trong phần "Investigation configuration", bạn có thể thiết lập vai trò IAM mà Q Developer sẽ sử dụng để truy cập dữ liệu đo lường từ xa cho các cuộc điều tra của nó. Chọn "Auto-create". Điều này sẽ tạo và cấu hình vai trò mới với các quyền cần thiết.

![Investigations-5](/images/4/investigations-5.png?width=90pc)

10. Trong phần **Enhanced integration**, bạn có thể cấu hình các tùy chọn bổ sung sẽ hỗ trợ thêm cho Q developer trong việc thực hiện điều tra. Các bước tiếp theo sẽ giải thích ngắn gọn những gì các tùy chọn này làm.
11. **Tags for application boundary detection**: Phần này cho phép bạn chỉ định các khóa thẻ tùy chỉnh hiện có được sử dụng cho các ứng dụng của bạn. Các thẻ này giúp Amazon Q Developer tinh chỉnh tìm kiếm của nó khi khám phá mối quan hệ tài nguyên. Thông tin thêm có thể được tìm thấy [tại đây](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-GetStarted.html).

![Investigations-6](/images/4/investigations-6.png?width=90pc)

12. Phần **CloudTrail section for change event detection** cho phép Amazon Q Developer truy cập dữ liệu CloudTrail, cải thiện phân tích của nó về các thay đổi hệ thống và giả thuyết nguyên nhân gốc rễ.

![Investigations-7](/images/4/investigations-7.png?width=90pc)

13. Các phần **X-Ray for topology mapping** và **Application Signals for health assessment** nêu bật các dịch vụ AWS bổ sung có thể nâng cao khả năng của Amazon Q Developer.

![Investigations-8](/images/4/investigations-9.png?width=90pc)

14. Chọn "**Next**" để tiếp tục
15. Phần cuối cùng của trình hướng dẫn cho phép cấu hình tích hợp bên thứ ba. Những tích hợp đó bao gồm hệ thống quản lý sự cố, tích hợp trò chuyện và SNS. Chúng tôi sẽ không đi sâu vào chi tiết ở đây. Nhưng nếu bạn muốn biết thêm thông tin, vui lòng truy cập [liên kết này](https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Investigations-GetStarted.html).
16. Chọn "**Complete setup**" để bắt đầu cấu hình. Sau vài giây, bạn sẽ thấy một thông báo xác nhận "**Initial Setup success**"

![Investigations-9](/images/4/investigations-10.png?width=90pc)