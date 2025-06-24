---
title: "Xây dựng DevOps Project và Architecture với Amazon Q CLI"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

Phần này hướng dẫn bạn sử dụng **Amazon Q CLI** kết hợp **Model Context Protocol (MCP)** để tự động hóa quá trình xây dựng DevOps Project và Architecture Diagram, giúp tối ưu hóa tốc độ phát triển và vận hành hạ tầng.

#### Điều kiện tiên quyết

1. Cài đặt `uv` từ [Astral](https://docs.astral.sh/uv/getting-started/installation/) hoặc [GitHub README](https://github.com/astral-sh/uv#installation)
2. Cài đặt Python: `uv python install 3.10`
3. Cài đặt [GraphViz](https://www.graphviz.org/)

#### Bước 1: Khởi động Amazon Q CLI và tạo thư mục dự án

- Tạo thư mục mới cho DevOps Project:

```bash
mkdir devops-project
cd devops-project
```

- Khởi động Amazon Q CLI:

```bash
q chat
```

- Workshop này sử dụng model `claude-4-sonnet` mới nhất của Anthropic nhằm nâng cao hiệu quả cho toàn bộ project.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image.png?width=90pc)
*Hình 1: Giao diện Q Chat CLI*

#### Bước 2: Cấu hình MCP Servers cho DevOps và Architecture

- Tạo file cấu hình MCP tại `~/.aws/amazonq/mcp.json` (hoặc `.amazonq/mcp.json` trong thư mục dự án) với nội dung ví dụ:

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

- Lưu lại và khởi động lại Q CLI để tải các MCP server.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image-1.png?width=90pc)
*Hình 2: Q CLI sau khi tải xong MCP Tools*

#### Bước 3: Tạo Architecture Diagram

- Trong Q CLI, nhập prompt:

```
Create an architecture diagram for a scalable web application using AWS services including VPC, ALB, ECS, RDS, and CloudWatch.
```

![alt text](/images/4-hands-on-demo/4.1-q-cli/gif-1.gif?width=90pc)
*Hình 3: Tạo Architecture Diagram tự động*

- Q CLI sẽ gọi MCP server `aws-diagram-mcp-server` để sinh Architecture Diagram và trả về bản vẽ hoặc mô tả chi tiết.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image-2.png?width=90pc)
*Hình 4: Architecture được tạo thành công*

#### Bước 4: Sinh mã Terraform/CDK để triển khai hạ tầng

- Tiếp tục trong Q CLI, nhập:

```
Generate Terraform code for the above architecture with autoscaling ECS cluster and multi-AZ RDS.
```

- Q CLI sẽ sử dụng MCP server `cdk-mcp-server` để sinh mã Terraform/CDK hoàn chỉnh.

![alt text](/images/4-hands-on-demo/4.1-q-cli/gif-2.gif?width=90pc)
*Hình 5: Sinh thành công Terraform Code*

#### Bước 5: Sinh tài liệu và tự động hóa workflow DevOps

- Yêu cầu tạo tài liệu mô tả project:

```
Generate a README.md explaining the architecture and deployment steps.
```

![alt text](/images/4-hands-on-demo/4.1-q-cli/image-3.png?width=90pc)
*Hình 6: Sinh thành công file README*

#### Tổng kết

- Amazon Q CLI kết hợp MCP server giúp bạn xây dựng nhanh chóng các DevOps Project phức tạp, từ thiết kế Architecture, sinh mã hạ tầng đến tự động hóa triển khai.
- Tất cả thao tác đều thực hiện bằng ngôn ngữ tự nhiên trong CLI, giúp giảm thời gian và hạn chế lỗi thủ công.
- MCP server dễ dàng mở rộng, tích hợp nhiều công cụ và dịch vụ khác nhau.
