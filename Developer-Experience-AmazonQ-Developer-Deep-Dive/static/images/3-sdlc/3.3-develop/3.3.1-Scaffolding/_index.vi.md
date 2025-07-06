---
title: "Khởi tạo dự án với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.3.1. </b> "
---

Scaffolding là quá trình thiết lập cấu trúc nền tảng cho ứng dụng hoặc dịch vụ của bạn. Amazon Q Developer giúp bạn nhanh chóng tạo framework dự án, mã boilerplate và các tài nguyên thiết yếu, giúp nhóm tập trung vào phát triển tính năng thay vì các bước lặp lại khi khởi tạo.

#### Kịch bản: Thiết lập dự án cho nhóm phát triển
Giả sử bạn cần tạo framework để một nhóm lập trình viên cùng xây dựng nhiều Web API. Amazon Q Developer có thể hướng dẫn bạn từng bước trong quá trình này.

##### Ví dụ 1: Prompt thủ công để khởi tạo dự án

**Prompt:**
Mở Q Chat trong IDE và nhập prompt sau:

```text
I need to create a project framework where a team of C# developers will be able to develop multiple Web APIs cohesively. Let’s start with just 1 simple API called QDevWorkshop.API.ReferenceData that references a common class library called QDevWorkshop.API.Common. The Web API needs to be deployed as Serverless container on AWS using CDK. I am using VSCode. Guide me on how to do this please.
```


**Phản hồi mẫu:**
Amazon Q Developer sẽ cung cấp kế hoạch từng bước, bao gồm cấu trúc dự án, đoạn mã mẫu và hướng dẫn triển khai. Bạn có thể làm theo các bước này hoặc dùng làm tài liệu tham khảo cho dự án của mình.

![alt text](image.png?width=40pc)

> **Mẹo:** Nếu bạn hạn chế thời gian hoặc theo track L200, có thể bỏ qua phần thực hành. Điều quan trọng là bạn biết Amazon Q Developer có thể tăng tốc quá trình khởi tạo dự án.

---

##### Ví dụ 2: Sử dụng Agent for Software Development

Amazon Q Developer còn cung cấp Agent for Software Development để tự động hóa nhiều hơn quá trình scaffolding.

**Prompt:**
Mở Q Chat trong IDE, gõ `/dev` và nhấn Enter hai lần để khởi động Agent for Software Development.

Sau đó nhập:

```text
Create a project framework where a team of C# developers will be able to develop multiple Web APIs cohesively. Scaffold 1 boilerplate API called QDevWorkshop.API.ReferenceData that references a common class library called QDevWorkshop.API.Common. The ReferenceData web API should have a currencies resource supporting a GET method, returning a list of hardcoded currency symbols. Common has some helper methods such as conversion of object to json string. The Web API needs to be deployed as Serverless container on AWS using CDK.
```

**Phản hồi mẫu:**
Agent sẽ tạo kế hoạch phát triển chi tiết và đề xuất mã. Xem xét mã đề xuất, chấp nhận hoặc phản hồi để lặp lại cho phù hợp. Khi hài lòng, bạn có thể chèn mã vào workspace của mình.

![alt text](image-1.png?width=40pc)

---

#### Best practices khi khởi tạo dự án
- **Cụ thể:** Định nghĩa rõ yêu cầu trong prompt để scaffolding chính xác hơn.
- **Lặp lại:** Sử dụng phản hồi và review mã để hoàn thiện cấu trúc dự án.
- **Tận dụng tự động hóa:** Dùng Agent for Software Development cho dự án phức tạp hoặc nhiều dịch vụ.
- **Tài liệu hóa:** Đảm bảo dự án scaffolded có tài liệu cho người phát triển sau.

{{% notice tip %}}
**Mẹo chuyên nghiệp:** Amazon Q Developer có thể scaffold dự án với nhiều ngôn ngữ và framework. Hãy điều chỉnh prompt phù hợp với stack công nghệ và mục tiêu triển khai của bạn.
{{% /notice %}}