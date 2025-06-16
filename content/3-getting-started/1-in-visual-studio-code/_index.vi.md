+++
title = "Amazon Q Developer trong Visual Studio Code"
date = 2024
weight = 1
chapter = false
pre = "<b>3.1 </b>"
+++

#### Cài đặt tiện ích mở rộng Amazon Q trong Visual Studio Code

**ℹ️ Thông tin**: Visual Studio Code là một trình soạn thảo mã nguồn nhẹ nhưng mạnh mẽ, chạy trên máy tính để bàn của bạn và có sẵn cho Windows, macOS và Linux. Đảm bảo bạn đã cài đặt [Visual Studio Code](https://code.visualstudio.com/download) cho hệ điều hành của mình. Bạn có thể tìm thấy các bước [thiết lập](https://code.visualstudio.com/docs/setup/setup-overview) trong tài liệu chính thức của họ.

#### Cài đặt tiện ích mở rộng Amazon Q

**💡 Mẹo chuyên nghiệp**: Thực hiện theo các bước sau để cài đặt tiện ích mở rộng Amazon Q:

1. Mở **Visual Studio Code**
2. Nhấp vào **Extensions** trên thanh hoạt động bên trái
3. Trong phần extensions, tìm kiếm "**Amazon Q**"
4. Chọn **Install** extension, khởi động lại/tải lại VSCode nếu cần

![AmazonQ-1](/images/3/AmazonQ-1.png?width=90pc)

#### Xác thực

**ℹ️ Thông tin**: Bạn có 2 tùy chọn để đăng nhập và workshop này khám phá cả hai phương thức xác thực:

1. Với [Builder ID](https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/builder-id.html) cho người dùng cá nhân với Gói Miễn phí
2. Với [AWS IAM Identity Center](https://docs.aws.amazon.com/toolkit-for-visual-studio/latest/user-guide/sso-credentials.html) cho người dùng chuyên nghiệp với Gói Pro

**💡 Mẹo chuyên nghiệp**: Bạn có thể sử dụng định danh nhân viên trong IAM Identity Center để đại diện cho công việc của mình và AWS Builder ID để đại diện cho thông tin cá nhân của bạn. Các định danh này hoạt động độc lập. Xem [Giá Amazon Q Developer](https://aws.amazon.com/q/developer/pricing/) để biết thêm chi tiết.

![AmazonQ-2](/images/3/AmazonQ-2.png?width=90pc)
_Nguồn: **Giá Amazon Q Developer**_

**ℹ️ Thông tin**: Trong Visual Studio Code, mở Amazon Q từ thanh hoạt động bên trái. Bạn sẽ thấy màn hình sau:

![AmazonQ-3](/images/3/AmazonQ-3.png?width=90pc)

#### Với AWS Builder ID (không yêu cầu tài khoản AWS)

**ℹ️ Thông tin**: Chọn tùy chọn này để sử dụng Amazon Q miễn phí. Bạn không cần Tài khoản AWS, tuy nhiên, bạn cần đăng ký AWS Builder ID. [AWS Builder ID](https://docs.aws.amazon.com/signin/latest/userguide/sign-in-aws_builder_id.html) là một hồ sơ cá nhân cung cấp quyền truy cập vào [các công cụ và dịch vụ được chọn](https://docs.aws.amazon.com/signin/latest/userguide/aws_builder_id-apps.html). AWS Builder ID miễn phí. Bạn chỉ trả tiền cho các tài nguyên AWS bạn sử dụng trong tài khoản AWS của mình, điều này tách biệt với Builder ID. Bạn có thể sử dụng cùng một email cho AWS Builder ID và cho email người dùng root của tài khoản AWS.

**💡 Mẹo chuyên nghiệp**: Thực hiện theo các bước sau để đăng ký và đăng nhập với AWS Builder ID:

1. Chọn tùy chọn đầu tiên "**Use for Free**" và nhấp vào "**Continue**"
   ![AmazonQ-4](/images/3/AmazonQ-4.png?width=90pc)

2. Nhập địa chỉ email của bạn, nhấp vào **Next**
   ![AmazonQ-5](/images/3/AmazonQ-8.png?width=90pc)

3. Nhập tên của bạn, nhấp vào **Next**
   ![AmazonQ-6](/images/3/AmazonQ-9.png?width=90pc)

4. Nhập mã xác minh được gửi đến email của bạn, nhấp vào **Verify**
   ![AmazonQ-8](/images/3/AmazonQ-10.png?width=90pc)

5. Nhập **mật khẩu** của bạn và nhập **CAPTCHA**
   ![AmazonQ-9](/images/3/AmazonQ-11.png?width=90pc)

6. Nhập **địa chỉ email** bạn đã sử dụng để đăng ký Builder ID của mình, nhấp vào **Next**
   ![AmazonQ-7](/images/3/AmazonQ-18.png?width=90pc)

7. Nhập **mật khẩu** bạn đã sử dụng để đăng ký Builder ID của mình, nhấp vào **Sign in**
   ![AmazonQ-10](/images/3/AmazonQ-12.png?width=90pc)

8. Nhập mã xác minh được gửi đến email của bạn, nhấp vào **Verify**
   ![AmazonQ-11](/images/3/AmazonQ-13.png?width=90pc)

9. Bạn đã tạo tài khoản Builder ID thành công
   ![AmazonQ-12](/images/3/AmazonQ-14.png?width=90pc)

10. Trong bảng Visual Studio Code, chọn **Cancel**
    ![AmazonQ-13](/images/3/AmazonQ-15.png?width=90pc)

11. Chọn tùy chọn "**Use for Free**" và nhấp vào "**Continue**"
    ![AmazonQ-14](/images/3/AmazonQ-16.png?width=90pc)

12. Nhấp vào **Open**
    ![AmazonQ-15](/images/3/AmazonQ-17.png?width=90pc)

13. Nhấp vào **Allow access**
    ![AmazonQ-16](/images/3/AmazonQ-5.png?width=90pc)

14. Bạn đã phê duyệt thành công yêu cầu cho AWS IDE Extensions for VS Code
    ![AmazonQ-17](/images/3/AmazonQ-6.png?width=90pc)

15. Sau khi hoàn tất, bạn có thể chuyển lại IDE của mình. Bạn đã đăng nhập thành công vào Amazon Q bằng Builder ID. Cửa sổ Q Chat sẽ tự động mở cho bạn
    ![AmazonQ-18](/images/3/AmazonQ-7.png?width=90pc)

**ℹ️ Thông tin**: Bây giờ bạn có thể chuyển đến phần [**_Đặt câu hỏi cho Amazon Q trong IDE_**](#đặt-câu-hỏi-cho-amazon-q-trong-ide).

#### Giấy phép Pro với AWS IAM Identity Center

**⚠️ Cảnh báo**: _Nếu bạn đang thực hiện bước này, bạn sẽ phải chịu phí AWS. Nếu bạn chỉ đang thử nghiệm, hãy đảm bảo xóa người dùng sau khi hoàn tất để giảm chi phí._

**ℹ️ Thông tin**: Để xác thực bằng phương pháp này, điều quan trọng là phải có Tài khoản AWS đã kích hoạt IAM Identity Center. Amazon Q yêu cầu IAM Identity Center. Nếu Tổ chức AWS của bạn chưa kích hoạt IAM Identity Center, Quản trị viên Tài khoản phải kích hoạt IAM Identity Center trong tài khoản này trước để thiết lập Amazon Q.

**💡 Mẹo chuyên nghiệp**: Yêu cầu quản trị viên tài khoản của bạn tạo một định danh cho bạn trong IAM Identity Center và [đăng ký định danh này vào Developer Pro](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-pro-tier-setting-up-access.html).

**ℹ️ Thông tin**: Đảm bảo Quản trị viên Tài khoản chia sẻ hai mục chính để bạn đăng nhập qua Visual Studio Code:

- URL bắt đầu (Start URL)
- Vùng AWS (AWS Region)

Chúng có sẵn trong AWS Console cho IAM Identity Center, trong phần "Settings" bạn sẽ thấy URL cổng truy cập AWS trong tab Identity Source.

**💡 Mẹo chuyên nghiệp**: Trong Visual Studio Code, thực hiện các bước sau để xác thực:

- Nhấp vào "**Amazon Q**" trong Thanh Trạng thái bên dưới để xem thêm các tùy chọn như Tạm dừng đề xuất tự động, mở cài đặt hoặc Đăng xuất
  ![AmazonQ-19](/images/3/AmazonQ-19.png?width=90pc)

1. Truy cập [Amazon Q](https://us-east-1.console.aws.amazon.com/amazonq?region=us-east-1#)

- Chọn **Amazon Q Developer**
  ![AmazonQ-1](/images/3/AmazonQpro-1.png?width=90pc)

2. Chọn **Get started**
   ![AmazonQ-1](/images/3/AmazonQpro-2.png?width=90pc)

- Nhập **Email address**, **First name** & **Last name**
- Chọn **Continue**
  ![AmazonQ-1](/images/3/AmazonQpro-3.png?width=90pc)
- Nhập **Profile name**
- Chọn **Create**
  ![AmazonQ-1](/images/3/AmazonQpro-4.png?width=90pc)

3. Bạn đã tạo thành công hồ sơ cho Amazon Q Developer

- Sao chép URL bắt đầu
  ![AmazonQ-1](/images/3/AmazonQpro-5.png?width=90pc)

4. Truy cập địa chỉ email của bạn

- Chọn **Accept invitation**
  ![AmazonQ-1](/images/3/AmazonQpro-6.png?width=90pc)

5. Tại phần Đăng ký người dùng mới

- Nhập **New password**
- Nhập **Confirm password**
- Nhấp vào **Set new password**
  ![AmazonQ-1](/images/3/AmazonQpro-7.png?width=90pc)

6. Nhập **User name** (email của bạn)

- Nhấp vào **Next**
  ![AmazonQ-1](/images/3/AmazonQpro-8.png?width=90pc)

7. Nhập **Password**

- Nhấp vào **Log in**
  ![AmazonQ-1](/images/3/AmazonQpro-9.png?width=90pc)

8. Tại phần Đăng ký thiết bị MFA

- Chọn **Authenticator Application**
- Nhấp vào **Next**
  ![AmazonQ-1](/images/3/AmazonQpro-10.png?width=90pc)

9. Tại phần **Set up authenticator app**
   **ℹ️ Thông tin**: Nếu bạn chưa cài đặt ứng dụng MFA ảo, vui lòng cài đặt bằng liên kết:
   [Authenticator Extension](https://chromewebstore.google.com/detail/authenticator/bhghoamapcdpbohphigoooaddinpkbai)

- Nhấp vào **Show QR code**
  ![AmazonQ-1](/images/3/AmazonQpro-11.png?width=90pc)
- Sử dụng ứng dụng MFA ảo hoặc camera trên thiết bị của bạn để quét mã QR
- Nhập **Code from authenticator**
- Nhấp vào **MFA Designation**
  ![AmazonQ-1](/images/3/AmazonQpro-12.png?width=90pc)

10. Nhấp vào **Complete**
    ![AmazonQ-1](/images/3/AmazonQpro-13.png?width=90pc)

11. Kiểm tra email **Active Your Amazon Q Developer Pro Subscription**
    ![AmazonQ-1](/images/3/AmazonQpro-14.png?width=90pc)

12. Trên cửa sổ Đăng nhập trong Amazon Q, chọn tùy chọn đầu tiên "**Use with Pro license**" và nhấp vào "**Continue**"
    ![AmazonQ-1](/images/3/AmazonQpro-15.png?width=90pc)
13. Bạn sẽ được yêu cầu nhập **Start URL** và **AWS Region** mà chúng ta đã ghi lại trước đó

- Nhấp vào **Continue**
  ![AmazonQ-1](/images/3/AmazonQpro-16.png?width=90pc)

- Bạn sẽ nhận được một cửa sổ bật lên với mã xác nhận, nhấp vào "Proceed to browser"

14. Bạn sẽ được chuyển hướng đến một trình duyệt web. Xác nhận mã giống nhau và nhấp vào "**Confirm and continue**"

- Thao tác này sẽ chuyển hướng bạn đến trang đăng nhập vào hồ sơ Identity Center của bạn. Sau khi hoàn tất, chỉ cần nhấp vào "**Allow access**"
  ![AmazonQ-1](/images/3/AmazonQpro-17.png?width=90pc)

15. Bạn đã phê duyệt thành công yêu cầu cho AWS IDE Extensions for VS Code
    ![AmazonQ-1](/images/3/AmazonQpro-18.png?width=90pc)
16. Bây giờ bạn có thể chuyển lại IDE Visual Studio Code của mình. Bạn đã đăng nhập thành công vào Amazon Q với giấy phép Pro

- Cửa sổ Amazon Q Chat sẽ tự động mở cho bạn
  ![AmazonQ-1](/images/3/AmazonQpro-19.png?width=90pc)

#### Đặt câu hỏi cho Amazon Q trong IDE

**ℹ️ Thông tin**: Amazon Q có thể được tìm thấy trong thanh hoạt động trong Visual Studio Code
![AmazonQAsk-1](/images/3/AmazonQask-01.png?width=90pc)

**💡 Mẹo chuyên nghiệp**: Để sử dụng Amazon Q hiệu quả:
- Mở mã nguồn hoặc kho lưu trữ GitHub của bạn
- Chọn mã, nhấp chuột phải gửi đến Amazon Q để giải thích mã HOẶC mở tệp và yêu cầu Q giải thích mã
  ![AmazonQAsk-2](/images/3/AmazonQask-02.png?width=90pc)