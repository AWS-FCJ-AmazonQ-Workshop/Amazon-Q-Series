---
title: "Kiến trúc và cách hoạt động"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Cách cung cấp ngữ cảnh phù hợp để nhận kết quả chính xác

Để Amazon Q Developer đưa ra các đề xuất và giải pháp chính xác, việc cung cấp ngữ cảnh đầy đủ và rõ ràng là rất quan trọng. Bạn nên bao gồm:

- Ngôn ngữ lập trình và framework đang sử dụng
- Mục tiêu cụ thể của đoạn code hoặc tính năng cần phát triển
- Các giới hạn kỹ thuật hoặc yêu cầu hiệu năng
- Đoạn code liên quan hoặc lỗi gặp phải (nếu có)

Việc này giúp AI hiểu đúng vấn đề và tránh các kết quả không phù hợp hoặc thiếu chính xác[1][7].

---

#### Kỹ thuật viết prompt hiệu quả

Một prompt hiệu quả thường bao gồm:

- **Mục tiêu kinh doanh rõ ràng:** Ví dụ, "Tối ưu hóa truy vấn database để giảm thời gian phản hồi dưới 100ms."
- **Ràng buộc kỹ thuật:** Ví dụ, "Sử dụng Java 17 và thư viện Hibernate."
- **Yêu cầu định dạng đầu ra:** Ví dụ, "Trả về đoạn code Java hoàn chỉnh với chú thích."
- **Ví dụ minh họa:** Khi có thể, cung cấp ví dụ cụ thể để AI hiểu rõ hơn về yêu cầu.

Việc áp dụng các yếu tố này giúp giảm thiểu việc phải chỉnh sửa lại nhiều lần và tăng hiệu quả tương tác với Amazon Q Developer[3].

---

#### Kiểm tra và chỉnh sửa code do AI gợi ý

Mặc dù Amazon Q Developer rất mạnh mẽ, các đề xuất vẫn cần được kiểm tra kỹ lưỡng trước khi áp dụng vào dự án:

- Đánh giá tính đúng đắn và hiệu quả của đoạn code được tạo ra.
- Kiểm thử kỹ thuật và bảo mật để tránh lỗi hoặc lỗ hổng tiềm ẩn.
- Chỉnh sửa hoặc tùy biến code theo chuẩn coding và quy chuẩn của dự án.

Quá trình này giúp đảm bảo chất lượng phần mềm và tránh các rủi ro không mong muốn[1][4].

---

#### Tùy chỉnh Amazon Q Developer cho phù hợp với thư viện nội bộ, API và quy chuẩn của dự án

Amazon Q Developer cho phép tùy chỉnh để phù hợp với môi trường phát triển riêng của doanh nghiệp:

- Nhúng thư viện nội bộ, API và các quy tắc coding đặc thù vào ngữ cảnh làm việc của AI.
- Tùy chỉnh đề xuất code để phù hợp với kiến trúc và tiêu chuẩn bảo mật của tổ chức.
- Sử dụng tính năng quản lý ngữ cảnh mở rộng để bao gồm các lớp, hàm, biến toàn cục trong dự án, giúp AI hiểu sâu hơn về codebase.

Điều này giúp tăng độ chính xác và tính ứng dụng thực tế của các đề xuất từ Amazon Q Developer[2][7].

---

**Hình ảnh minh họa:**  
_Quy trình tương tác hiệu quả với Amazon Q Developer qua prompt rõ ràng và kiểm tra kết quả_ (Placeholder)

---

**Tham khảo tài liệu chính thức:**

- [Best practices with Amazon Q Developer for in-line and assistant code generation (AWS Docs)](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/introduction.html)
- [Mastering Amazon Q Developer: Crafting Effective Prompts (AWS Blog)](https://aws.amazon.com/blogs/devops/mastering-amazon-q-developer-part-1-crafting-effective-prompts/)
- [Best practices for code recommendations with Amazon Q Developer (AWS Docs)](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/code-recommendations.html)

---

Áp dụng những best practices này sẽ giúp bạn tận dụng tối đa sức mạnh của Amazon Q Developer, nâng cao hiệu quả phát triển và đảm bảo chất lượng phần mềm trong dự án.

[1] https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/introduction.html
[2] https://aws.amazon.com/blogs/devops/april-2025-amazon-q-developer/
[3] https://aws.amazon.com/blogs/devops/mastering-amazon-q-developer-part-1-crafting-effective-prompts/
[4] https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/code-recommendations.html
[5] https://dev.to/mohamednizzad/a-definite-guide-to-develop-production-grade-applications-with-aws-q-developer-in-2025-video-3690
[6] https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html
[7] https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/onboarding.html
[8] https://www.techtarget.com/searchcloudcomputing/tip/Get-started-with-Amazon-Q-Developer
