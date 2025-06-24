---
title: "Xây dựng DevOps Project và Architecture với Amazon Q CLI"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

Phần này sẽ hướng dẫn bạn cách sử dụng **Amazon Q CLI** kết hợp với **Model Context Protocol (MCP)** để nhanh chóng tạo các dự án DevOps và sơ đồ kiến trúc, giúp tự động hóa nhiều tác vụ phát triển và vận hành hạ tầng.

#### Bước 1: Khởi động Amazon Q CLI và tạo thư mục dự án

- Mở terminal, tạo thư mục mới cho dự án DevOps:

```bash
mkdir devops-project
cd devops-project
```

- Khởi động Amazon Q CLI bằng lệnh:

```bash
q chat
```

- Hiện tại tháng 06/2025, Amazon Q Developer đã hỗ trợ 3 models mới nhât của nhà Anthropic, tại workshop này, chúng ta sẽ tận dụng `claude-4-sonnet` model mới và mạnh mẽ nhất cho xuyên suốt project luôn.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image.png?width=90pc)*Hình 1: Giao diện Q Chat CLI*

#### Bước 2: Cấu hình MCP Servers cho DevOps và Architecture

- Tạo file cấu hình MCP tại `~/.aws/amazonq/mcp.json` (hoặc `.amazonq/mcp.json` trong dự án) với các MCP server hỗ trợ DevOps, ví dụ:

```json
{
  "mcpServers": {
    "cdk-mcp-server": {
      "command": "uvx",
      "args": ["cdk-mcp-server@latest"],
      "env": {},
      "disabled": false,
      "autoApprove": []
    },
    "aws-diagram-mcp-server": {
      "command": "uvx",
      "args": ["aws-diagram-mcp-server@latest"],
      "env": {},
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

- Lưu và khởi động lại Amazon Q CLI để tải MCP server.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image-1.png?width=90pc)*Hình 2: Giao diện CLI sau khi tải hoàn thành 2 MCP Tools*

#### Bước 3: Tạo sơ đồ kiến trúc (Architecture Diagram)

- Trong phiên làm việc `q chat`, nhập prompt:

```
Create an architecture diagram for a scalable web application using AWS services including VPC, ALB, ECS, RDS, and CloudWatch.
```

- Amazon Q CLI gọi MCP server `aws-diagram-mcp-server` để tạo sơ đồ kiến trúc tự động, trả về bản vẽ hoặc mô tả chi tiết.

<!-- Hinh query thành công -->

#### Bước 4: Generate Terraform hoặc CDK để triển khai hạ tầng

- Tiếp tục trong `q chat`, nhập:

```
Generate Terraform code for the above architecture with autoscaling ECS cluster and multi-AZ RDS.
```

- Amazon Q CLI sử dụng MCP server `cdk-mcp-server` hoặc tương tự để sinh mã Terraform/CDK hoàn chỉnh, giúp bạn triển khai nhanh chóng.

<!-- Hinh query thành công -->

#### Bước 5: Tạo tài liệu và tự động hóa workflow DevOps

- Yêu cầu tạo tài liệu mô tả dự án:

```
Generate a README.md explaining the architecture and deployment steps.
```

<!-- Hinh anh tao thanh cong file README -->

- Hoặc tạo script tự động deploy:

```
Create a bash script to deploy the infrastructure and start the application.
```

Amazon Q CLI sẽ tạo script shell hoàn chỉnh, giúp bạn tự động hóa quy trình.

<!-- Hinh anh tao thanh cong deploy script -->

#### Tổng kết

- Amazon Q CLI kết hợp MCP server giúp bạn xây dựng nhanh các dự án DevOps phức tạp, từ thiết kế kiến trúc, sinh mã hạ tầng đến tự động hóa triển khai.  
- Quy trình hoàn toàn tương tác bằng ngôn ngữ tự nhiên trong CLI, giảm thiểu thời gian viết code thủ công và sai sót.  
- MCP server cho phép mở rộng dễ dàng, tích hợp nhiều công cụ và dịch vụ khác nhau.
