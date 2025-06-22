---
title: "Best Practices khi làm việc với Amazon Q"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

#### Cách cung cấp ngữ cảnh phù hợp để nhận kết quả chính xác

Để Amazon Q Developer đưa ra đề xuất chuẩn, hãy cung cấp đầy đủ context:  
- Ngôn ngữ lập trình, framework  
- Mục tiêu code hoặc feature  
- Ràng buộc kỹ thuật, yêu cầu hiệu năng  
- Đoạn code liên quan hoặc lỗi gặp phải (nếu có)  

Việc này giúp AI hiểu đúng vấn đề và tránh kết quả thiếu chính xác [[1]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/introduction.html) [[7]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/onboarding.html).

#### Kỹ thuật viết prompt hiệu quả

Prompt tốt nên có:  
- **Mục tiêu rõ ràng:** VD "Tối ưu hóa truy vấn DB dưới 100ms."  
- **Ràng buộc kỹ thuật:** VD "Dùng Java 17, Hibernate."  
- **Yêu cầu output:** VD "Trả về code Java hoàn chỉnh, có chú thích."  
- **Ví dụ minh họa:** Càng cụ thể càng tốt.  

Áp dụng các yếu tố này giúp giảm chỉnh sửa và tăng hiệu quả tương tác với Amazon Q Developer [\[3\]](https://aws.amazon.com/blogs/devops/mastering-amazon-q-developer-part-1-crafting-effective-prompts/).

![alt text](/images/5-best-practices/image.png)

*Hình 1: Ví dụ về kỹ thuật viết Prompt hiệu quả*

#### Kiểm tra và chỉnh sửa code do AI gợi ý

Dù Amazon Q Developer mạnh mẽ, bạn vẫn cần review kỹ:  
- Đánh giá tính đúng đắn, hiệu quả code  
- Kiểm thử kỹ thuật, bảo mật  
- Chỉnh sửa theo coding convention của dự án  

Quy trình này giúp đảm bảo chất lượng phần mềm và tránh rủi ro [[1]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/introduction.html) [[4]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/code-recommendations.html).

#### Tùy chỉnh Amazon Q Developer cho codebase nội bộ

Bạn có thể custom Q Developer cho môi trường riêng:  
- Nhúng thư viện nội bộ, API, coding rule vào context AI  
- Tùy chỉnh suggestion theo kiến trúc, security standard của tổ chức  
- Quản lý context mở rộng để AI hiểu sâu codebase  

Điều này tăng độ chính xác và ứng dụng thực tế của đề xuất [[2]](https://aws.amazon.com/blogs/devops/april-2025-amazon-q-developer/) [[7]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/onboarding.html).

Áp dụng các best practices này giúp bạn tận dụng tối đa sức mạnh Amazon Q Developer, nâng hiệu suất và đảm bảo chất lượng phần mềm.