---
title: "Cài đặt môi trường cho Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

![alt text](/images/2-setup/image.png?width=90pc)

#### Kiểm tra Prerequisites

Trước khi tiến hành deep dive workshop này, hãy đảm bảo bạn đã hoàn thành basic Amazon Q Developer setup:

- **IDE Integration**: VS Code hoặc JetBrains với Amazon Q extension đã cài đặt
- **CLI Access**: Amazon Q CLI đã được configured và authenticated
- **Account Setup**: Authentication qua AWS Builder ID hoặc IAM Identity Center
- **Network Access**: Kết nối phù hợp tới AWS services

#### Quick Setup Reference

Để có hướng dẫn setup đầy đủ, tham khảo [Setting Up the Development Environment](https://aws-fcj-amazonq-workshop.github.io/Amazon-Q-Series/Getting-Started-with-AmazonQ-Developer/3-setting-up-dev-environment/).

Nội dung bao gồm:
- CLI installation và configuration
- IDE plugin setup và authentication
- Account creation và access management
- Troubleshooting các vấn đề setup thường gặp

#### Verification Steps

Xác nhận setup của bạn bằng cách test:
1. **CLI**: Chạy `q login` để verify authentication
2. **IDE**: Mở Amazon Q chat panel và gửi test message
3. **Code Completion**: Tạo file mới và test inline suggestions

{{% notice tip %}}
Nếu gặp authentication issues, hãy clear cache và re-authenticate bằng credentials mới nhất.
{{% /notice %}}

