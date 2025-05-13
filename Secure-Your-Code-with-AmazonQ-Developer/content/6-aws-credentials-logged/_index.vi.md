+++
title = "AWS credentials logged"
date = 2024-05-14T00:38:32+07:00
weight = 6
chapter = false
pre = "<b>6. </b>"
+++

Trong lỗ hổng này, các thông tin đăng nhập AWS chưa được mã hóa có thể bị ghi nhật ký, điều này có thể làm lộ các thông tin đăng nhập đó cho kẻ tấn công. Mã hóa dữ liệu nhạy cảm, chẳng hạn như thông tin đăng nhập, trước khi chúng được ghi nhật ký để làm cho mã an toàn hơn.

1. Sao chép đoạn mã sau vào IDE của bạn.

   ```
   def log_credentials_noncompliant():

       import boto3

       import logging

       session = boto3.Session()

       credentials = session.get_credentials()

       credentials = credentials.get_frozen_credentials()

       access_key = credentials.access_key

       secret_key = credentials.secret_key

       # Noncompliant: credentials are written to the logger.

       logging.info('Access key: ', access_key)

       logging.info('secret access key: ', secret_key)
   ```

2. Chạy **Amazon Q Project Scan** để xem cách phát hiện lỗ hổng này.
   ![credentials-logged-1](/images/6/credentials-logged-1.png?width=90pc)
3. Để xem chi tiết các phát hiện, giữ con trỏ chuột trên đoạn mã không an toàn và nhấp vào "View Details" để tìm hiểu thêm:
   ![credentials-logged-2](/images/6/credentials-logged-2.png?width=90pc)
4. Tránh ghi nhật ký thông tin nhạy cảm như khóa truy cập hoặc khóa bí mật. Để quản lý quyền truy cập tài nguyên AWS, hãy ưu tiên sử dụng vai trò IAM hơn là khóa truy cập và khóa bí mật tĩnh, đặc biệt đối với các ứng dụng chạy trên các dịch vụ AWS như EC2, Lambda, v.v. Vai trò IAM cung cấp thông tin đăng nhập tạm thời được AWS tự động quản lý.

   Dưới đây là một ví dụ về cách khắc phục đoạn mã này. Đảm bảo lưu tệp trước khi chạy lại quá trình quét.

   ```
   def log_credentials_compliant():

       import boto3

       session = boto3.Session()

       credentials = session.get_credentials()

       credentials = credentials.get_frozen_credentials()

       access_key = credentials.access_key

       secret_key = credentials.secret_key

       # Compliant: avoids writing credentials to the logger.

       session = boto3.Session(

           aws_access_key_id=access_key,

           aws_secret_access_key=secret_key

       )
   ```
