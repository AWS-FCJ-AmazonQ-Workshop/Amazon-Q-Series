+++
title = "Path Traversal"
date = 2024-05-14T00:38:32+07:00
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

Việc xây dựng tên đường dẫn với đầu vào không được làm sạch của người dùng có thể dẫn đến các cuộc tấn công path traversal (duyệt đường dẫn) (ví dụ: ../../../). Loại tấn công này khai thác việc xác thực/làm sạch không đầy đủ các tên tệp do người dùng cung cấp, cho phép kẻ tấn công truy cập các tệp hoặc thư mục không được phép truy cập. Điều này có thể dẫn đến truy cập trái phép, tiết lộ thông tin và thậm chí xâm nhập hệ thống.

1. Sao chép đoạn mã sau vào IDE của bạn.

   ```
   def verify_file_path_noncompliant():

       from flask import request

       file_path = request.args["file"]

       # Noncompliant: user input file path is not sanitized.

       file = open(file_path)

       file.close()
   ```

2. Nhấp vào **Amazon Q** trên thanh trạng thái và chạy **Project Scan** để xem cách phát hiện Lỗ hổng Path Traversal.
   ![autoscans](/images/1/autoscans.png?width=90pc)

3. Phát hiện sau sẽ hiển thị trên thanh trạng thái
   ![Path-Traversal-1](/images/4/Path-Traversal-1.png?width=90pc)
4. Để xem chi tiết các phát hiện, giữ con trỏ chuột trên đoạn mã không an toàn và nhấp vào "View Details" để tìm hiểu thêm:
   ![Path-Traversal-2](/images/4/Path-Traversal-2.png?width=90pc)
5. Các lỗ hổng path traversal có thể được giảm thiểu bằng cách làm sạch đầu vào của người dùng trước khi sử dụng nó để xây dựng đường dẫn tệp. Cách tiếp cận này bao gồm việc kiểm tra xem đường dẫn tệp do người dùng cung cấp có nằm trong danh sách các đường dẫn được phép xác định trước hay không.

   Dưới đây là một ví dụ về cách khắc phục đoạn mã này. Đảm bảo lưu tệp trước khi chạy lại quá trình quét.

   ```
   def verify_file_path_compliant():

       from flask import request

       base_path = "/var/data/images/"

       file_path = request.args["file"]

       allowed_path = ["example_path1", "example_path2"]

       # Compliant: user input file path is sanitized.

       if file_path in allowed_path:

           file = open(base_path + file_path)

           file.close()
   ```

6. Thử khắc phục vấn đề và chạy lại quá trình quét.
