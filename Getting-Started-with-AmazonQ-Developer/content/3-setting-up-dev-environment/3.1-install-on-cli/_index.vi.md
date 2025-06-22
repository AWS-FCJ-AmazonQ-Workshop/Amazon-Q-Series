---
title: "Cài đặt Amazon Q Developer trên CLI"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

#### Cài đặt Amazon Q Developer trên CLI

Amazon Q Developer CLI hỗ trợ các hệ điều hành macOS và Linux (bao gồm Ubuntu). Dưới đây là các bước cài đặt ngắn gọn theo tài liệu chính thức của AWS.[[1]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html)

#### 1. Cài đặt trên macOS

- Tải file cài đặt Amazon Q CLI dạng `.dmg` từ trang chính thức AWS.  
- Mở file `.dmg` và kéo ứng dụng vào thư mục Applications.  
- Khởi chạy ứng dụng Amazon Q, làm theo hướng dẫn để kích hoạt tích hợp shell (shell integrations) giúp sử dụng lệnh `q` trong terminal.  
- Đăng nhập bằng AWS Builder ID hoặc IAM Identity Center.

Hoặc bạn có thể cài đặt nhanh qua Homebrew:

```bash
brew install amazon-q
```

![alt text](/images/3-setting-up-dev-environment/3.1-install-on-cli/image.png?width=90pc)

*Hình 1: Cài đặt Amazon Q CLI trên MacOS*


#### 2. Cài đặt trên Linux (Ubuntu)

- Tải gói `.deb` chính thức:

```bash
wget https://desktop-release.q.us-east-1.amazonaws.com/latest/amazon-q.deb
```

- Cài đặt gói:

```bash
sudo apt-get install -f
sudo dpkg -i amazon-q.deb
```

- Khởi chạy Amazon Q CLI:

```bash
q
```

- Đăng nhập bằng AWS Builder ID hoặc IAM Identity Center.

> Lưu ý: Cách này yêu cầu môi trường có GUI để chạy ứng dụng desktop.

Ngoài ra, bạn có thể cài đặt bằng AppImage (cũng yêu cầu GUI):

```bash
chmod +x amazon-q.appimage
./amazon-q.appimage
```

#### 3. Sử dụng trên Windows

Amazon Q Developer CLI chưa có bản cài đặt native cho Windows. Để sử dụng trên Windows, bạn cần cài đặt **Windows Subsystem for Linux (WSL)** và chạy Amazon Q CLI trong môi trường Linux ảo này.

- Hướng dẫn cài đặt WSL của Microsoft:  
  https://learn.microsoft.com/windows/wsl/install

- Sau khi cài đặt WSL và Ubuntu, bạn có thể làm theo hướng dẫn cài đặt Linux ở trên trong terminal WSL.


#### 4. Kiểm tra và khắc phục sự cố

- Sử dụng lệnh sau để kiểm tra trạng thái cài đặt:

```bash
q doctor
```

- Nếu gặp lỗi đăng nhập, chạy lại:

```bash
q login
```

- Để báo lỗi hoặc sự cố, dùng:

```bash
q issue
```

![alt text](/images/3-setting-up-dev-environment/3.1-install-on-cli/image-3.png?width=60pc)

*Hình 2: Kiểm tra và khắc phục sự cố*