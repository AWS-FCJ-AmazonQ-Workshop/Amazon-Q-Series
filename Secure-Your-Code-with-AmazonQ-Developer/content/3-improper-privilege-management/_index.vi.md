+++
title = "Improper Privilege Management"
date = 2024-05-14T00:38:32+07:00
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

Leo thang đặc quyền xảy ra khi một người dùng độc hại khai thác một lỗi (bug), lỗ hổng thiết kế hoặc lỗi cấu hình trong một ứng dụng hoặc hệ điều hành để giành được quyền truy cập cao hơn vào hệ thống. Các đặc quyền nâng cao có thể được sử dụng để xóa tệp, xem thông tin riêng tư hoặc cài đặt các chương trình hoặc backdoor không mong muốn.

1. Sao chép đoạn mã sau vào IDE của bạn.

   ```
   def set_user_noncompliant():

       import os

       root = 0

       # Noncompliant: the process user is set to root.

       os.setuid(root)
   ```

2. Nhấp vào **Amazon Q** trên thanh trạng thái và chạy **Project Scan** để xem cách phát hiện Lỗ hổng Quản lý Đặc quyền Không Đúng cách.
   ![autoscans](/images/1/autoscans.png?width=90pc)

3. Chọn **Review workspace** or **Review active file**
   ![Privilege-1](/images/3/Privilege-1.png?width=90pc)

4. Phát hiện sau sẽ hiển thị trên thanh trạng thái
   ![Privilege-2](/images/3/Privilege-2.png?width=90pc)

5. Để xem chi tiết các phát hiện, giữ con trỏ chuột trên đoạn mã không an toàn và nhấp vào "View Details" để tìm hiểu thêm:
   ![Privilege-3](/images/3/Privilege-3.png?width=90pc)
   ![Privilege-4](/images/3/Privilege-4.png?width=90pc)

6. Nên tránh chạy các tiến trình với quyền root bất cứ khi nào có thể vì nó có thể dẫn đến các lỗ hổng bảo mật nghiêm trọng, bao gồm truy cập trái phép, leo thang đặc quyền và khả năng hệ thống bị xâm nhập.

   Luôn tuân theo nguyên tắc đặc quyền tối thiểu, nghĩa là các tiến trình chỉ nên chạy với các quyền tối thiểu cần thiết để thực hiện các tác vụ được yêu cầu của chúng. Điều này làm giảm rủi ro và tác động tiềm ẩn của một cuộc tấn công bảo mật.

   Dưới đây là một ví dụ về cách khắc phục đoạn mã này. Đảm bảo lưu tệp trước khi chạy lại quá trình quét.

   ```
   def set_user_compliant():

       import os

       root = 4

       # Compliant: the process user is set to userid 4.

       os.setuid(root)
   ```

7. Thử khắc phục vấn đề và chạy lại quá trình quét.
