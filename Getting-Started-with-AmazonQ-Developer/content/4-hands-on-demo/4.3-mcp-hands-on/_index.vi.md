---
title: "Sử dụng MCP với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: "4.3. "
---

Hướng dẫn sử dụng **Model Context Protocol (MCP)** để mở rộng khả năng của Amazon Q Developer, cho phép AI tra cứu tài liệu AWS trực tiếp trong IDE.

#### 1. Tổng quan MCP

**Model Context Protocol (MCP)** là giao thức mở cho phép AI assistant kết nối với các dịch vụ bên ngoài. Lợi ích chính:

- Tra cứu tài liệu AWS trực tiếp trong IDE
- Tự động hóa tác vụ dựa trên ngữ cảnh dự án
- Giảm thiểu chuyển đổi giữa các công cụ

![MCP Architecture](/images/4-hands-on-demo/4.3-mcp-hands-on/image.png?width=90pc)

*Hình 1: Kiến trúc MCP - Kết nối Amazon Q Developer với AWS Documentation Server*

#### 2. Cấu hình AWS Documentation MCP Server trên Amazon Q Developer

Để sử dụng AWS Documentation MCP Server — một MCP server chính thức của AWS giúp tra cứu tài liệu AWS trong IDE — bạn làm theo các bước sau:

**Bước 1: Truy cập cấu hình MCP**
- Mở Amazon Q Developer → Tab Chat → Biểu tượng **tools**

**Bước 2: Cấu hình AWS Documentation MCP Server**

| Thông số                  | Giá trị                                                                      |
| ------------------------- | ---------------------------------------------------------------------------- |
| **Scope**                 | Global (`~/.aws/amazonq/mcp.json`) hoặc This Workspace (`.amazonq/mcp.json`) |
| **Tên**                   | `AWSDocMCPServer`                                                            |
| **Transport**             | `stdio`                                                                      |
| **Command**               | `uvx`                                                                        |
| **Arguments**             | `awslabs.aws-documentation-mcp-server@latest`                                |
| **Environment Variables** | `FASTMCP_LOG_LEVEL=ERROR` & `AWS_DOCUMENTATION_PARTITION=aws`                |

![MCP Server Configuration](/images/4-hands-on-demo/4.3-mcp-hands-on/image-1.png?width=40pc)

*Hình 2: Giao diện cấu hình AWS Documentation MCP Server với các thông số cần thiết*

**Bước 3: Phân quyền**
- Chọn **Always allow** cho môi trường development (Production nên hạn chế)  

![MCP Permissions](/images/4-hands-on-demo/4.3-mcp-hands-on/image-2.png?width=40pc)

*Hình 3: Cấu hình quyền truy cập cho MCP Server - Always allow cho development*

#### 3. Sử dụng AWS Documentation MCP Server

Các lệnh cơ bản:

**Tra cứu tài liệu:**
```
look up documentation on S3 bucket naming rule. cite your sources
```

**Tìm kiếm theo từ khóa:**
```
search documentation for "Lambda function timeout" limit 3
```

**Gợi ý tài liệu liên quan:**
```
recommend content for page https://docs.aws.amazon.com/...
```

![AWS Documentation Query](/images/4-hands-on-demo/4.3-mcp-hands-on/PixPin_2025-06-22_22-13-45.gif?width=40pc)

*Hình 4: Demo tra cứu quy tắc đặt tên S3 bucket - MCP Server trả về nội dung markdown với nguồn tham khảo*

#### Lợi ích

- **Tăng hiệu suất:** Tra cứu tài liệu AWS trực tiếp trong IDE
- **Tiết kiệm thời gian:** Không cần chuyển đổi giữa các tab trình duyệt
- **Thông tin chính xác:** Nội dung được lấy từ tài liệu chính thức AWS
- **Cấu hình một lần:** Sử dụng cho tất cả dự án

**Tham khảo:**  
- [AWS Blog: Use Model Context Protocol with Amazon Q Developer](https://aws.amazon.com/blogs/devops/use-model-context-protocol-with-amazon-q-developer-for-context-aware-ide-workflows/)  
- [AWS Documentation MCP Server trên GitHub](https://github.com/awslabs/mcp/tree/main/src/aws-documentation-mcp-server)  
