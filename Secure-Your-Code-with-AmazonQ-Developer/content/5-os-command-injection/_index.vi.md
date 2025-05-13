+++
title = "OS Command Injection"
date = 2024-05-14T00:38:32+07:00
weight = 5
chapter = false
pre = "<b>5. </b>"
+++

Việc xây dựng các lệnh hệ điều hành hoặc shell với đầu vào không được làm sạch của người dùng có thể dẫn đến vô tình chạy mã độc hại. Loại lỗ hổng này cho phép kẻ tấn công thực thi các lệnh tùy ý trên hệ điều hành máy chủ với các đặc quyền của ứng dụng dễ bị tấn công. Các cuộc tấn công command injection có thể dẫn đến nhiều kết quả độc hại, bao gồm truy cập dữ liệu trái phép, hỏng dữ liệu, từ chối dịch vụ và xâm nhập hệ thống hoàn toàn.

1. Sao chép đoạn mã sau vào IDE của bạn.

   ```
   def exec_command_noncompliant():

       from paramiko import client

       from flask import request

       address = request.args.get("address")

       cmd = "ping -c 1 %s" % address

       client = client.SSHClient()

       client.connect("ssh.samplehost.com")

       # Noncompliant: address argument is not sanitized.

       client.exec_command(cmd)
   ```

2. Chạy **Amazon Q Project Sca**n để xem cách phát hiện lỗ hổng OS command injection.
   ![OS-1](/images/5/OS-1.png?width=90pc)

3. Để xem chi tiết các phát hiện, giữ con trỏ chuột trên đoạn mã không an toàn và nhấp vào "View Details" để tìm hiểu thêm:
   ![OS-2](/images/5/OS-2.png?width=90pc)
4. Bất cứ khi nào có thể, hãy tránh xây dựng các lệnh shell với đầu vào của người dùng. Sử dụng các API hoặc thư viện dành riêng cho ngôn ngữ được thiết kế để thực hiện các hành động cần thiết mà không cần gọi shell.

   **Xác thực và Làm sạch Đầu vào**: Nếu bạn phải bao gồm đầu vào của người dùng trong một lệnh shell, hãy xác thực nghiêm ngặt đầu vào để đảm bảo nó tuân thủ các định dạng dự kiến (ví dụ: chỉ chữ và số). Làm sạch đầu vào bằng cách thoát hoặc loại bỏ các ký tự có khả năng gây nguy hiểm.

   Dưới đây là một ví dụ về cách khắc phục đoạn mã này. Đảm bảo lưu tệp trước khi chạy lại quá trình quét.

   ```
   from paramiko import SSHClient, AutoAddPolicy
   import os
   import shlex

   def exec_command_compliant():
       # Retrieve SSH credentials and server details from environment variables
       ssh_host = os.getenv('SSH_HOST', 'default_host')
       ssh_username = os.getenv('SSH_USERNAME', 'default_username')
       ssh_password = os.getenv('SSH_PASSWORD', 'default_password')

       # Get the address from the request's query parameters
       from flask import request
       address = request.args.get("address")

       # Sanitize the address argument to prevent command injection
       safe_address = shlex.quote(address)

       # Prepare the ping command with the sanitized address
       cmd = f"ping -c 1 {safe_address}"

       # Initialize the SSH client and connect to the remote host
       client = SSHClient()
       client.load_system_host_keys()

       # Use environment variables for credentials
       client.connect(ssh_host, username=ssh_username, password=ssh_password)

       # Execute the command on the remote server
       stdin, stdout, stderr = client.exec_command(cmd)
       output = stdout.read().decode()

       # Close the SSH connection
       client.close()

       # Return or process the command's output
       return output
   ```
