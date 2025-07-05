---
title: "Replatforming với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.5.2. </b> "
---

Giả sử bạn có một ASP.NET 8 Web API đang chạy trên container Windows. Bạn muốn chuyển sang chạy trên Linux để tăng tính di động và tiết kiệm chi phí.

#### Ví dụ: Chuyển đổi Dockerfile

**Bước 1:** Tạo file mới tên `Dockerfile` trong VSCode và dán Dockerfile hiện tại (Windows):

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:8.0-windowsservercore-ltsc2022 AS base
WORKDIR /app
EXPOSE 6268

ENV ASPNETCORE_URLS=http://+:6268

FROM mcr.microsoft.com/dotnet/sdk:8.0-windowsservercore-ltsc2022 AS build
ARG BUILD_CONFIGURATION=Release
WORKDIR /src
# ...phần còn lại của Dockerfile
```

**Bước 2:** Sử dụng Amazon Q Developer để đề xuất thay đổi giúp chạy trên Linux (ví dụ: cập nhật base image, biến môi trường, đường dẫn file).

```text
Convert this to use a lightweight Linux container
```

![alt text](image.png?width=40pc)

**Bước 3:** Xem xét và kiểm thử Dockerfile mới để đảm bảo ứng dụng chạy đúng trên Linux.

#### Best practices
- Luôn kiểm thử ứng dụng đã replatform ở môi trường staging
- Cập nhật tài liệu để phản ánh yêu cầu nền tảng mới
- Theo dõi các vấn đề đặc thù nền tảng sau khi chuyển đổi