---
title: "Lưu ý & Best practices khi tạo Prompt"
date: 2023-08-17T00:00:00-00:00
weight: 7
chapter: false
pre: "<b>3.3.2.7 </b>"
---

#### Best practices
Hãy chủ động và có chủ đích khi đặt tên biến, hàm và cấu trúc prompt. Điều này giúp cả bạn, đồng nghiệp và AI hiểu rõ mã nguồn và yêu cầu. Luôn cụ thể, mô tả rõ ràng trong mọi khía cạnh của mã và prompt.

#### Tránh
- Tên biến một ký tự (trừ biến lặp tạm thời)
- Tên chung chung như `data` hoặc `value`
- Viết tắt như `val` hoặc `num`
- Tên hàm không rõ nghĩa hoặc mơ hồ

#### Nên dùng
- Tên mô tả rõ như `numberOfStudents` hoặc `totalPrice`
- Tên phù hợp với ngữ cảnh và kiểu dữ liệu của biến
- Tên thể hiện giá trị, mục đích, phạm vi (toàn cục, cục bộ, class, ...)
- Tên thể hiện vòng đời (hằng số, tạm thời, ...), mức độ truy cập (public, private, ...)
- Sử dụng chỉ thị trong prompt để nhấn mạnh từ khóa quan trọng, hướng AI sinh ra kết quả đúng ý

**Mẹo:** Đây là các Best practices chung cho cả lập trình và kỹ thuật prompt. Đặt tên rõ ràng, có chủ đích và cấu trúc prompt hợp lý sẽ giúp mã chất lượng hơn và AI gợi ý sát nhu cầu hơn.
