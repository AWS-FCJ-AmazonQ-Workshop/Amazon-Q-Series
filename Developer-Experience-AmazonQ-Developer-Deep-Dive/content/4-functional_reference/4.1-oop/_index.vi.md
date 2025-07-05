---
title: "Giới thiệu về Amazon Q Developer: Các khái niệm OOP"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

#### Lập trình hướng đối tượng: Đa hình & Kế thừa

Đa hình và kế thừa là hai khái niệm nền tảng trong lập trình hướng đối tượng (OOP), giúp tái sử dụng mã, tăng tính mô-đun và khả năng mở rộng.

![alt text](image.png?width=90pc)

#### Đa hình
Đa hình cho phép đối tượng hoặc phương thức có nhiều hình thức hoặc hành vi khác nhau. Điều này giúp các đối tượng thuộc các lớp khác nhau có thể được xử lý như các đối tượng của cùng một lớp cha, hỗ trợ nguyên tắc "một giao diện, nhiều cách triển khai". Nhờ đó, mã nguồn trở nên linh hoạt và dễ bảo trì hơn.

#### Kế thừa
Kế thừa cho phép một lớp mới (lớp con) kế thừa thuộc tính và hành vi từ một lớp đã có (lớp cha). Lớp con có thể mở rộng hoặc ghi đè các đặc điểm kế thừa, giúp tái sử dụng mã và mô hình hóa các mối quan hệ thực tế.

**Tóm tắt:**
- Đa hình giúp mã nguồn linh hoạt, cho phép xử lý các đối tượng khác nhau một cách nhất quán.
- Kế thừa hỗ trợ tái sử dụng và mở rộng mã bằng cách xây dựng lớp mới dựa trên lớp có sẵn.

#### Sử dụng Amazon Q Developer cho OOP
Trong phần này, bạn sẽ sử dụng Amazon Q Developer để tạo ví dụ minh họa các khái niệm OOP, tập trung vào đa hình và kế thừa. Amazon Q Developer có thể sinh mã dựa trên prompt như sau:

**Ví dụ Prompt:**
> Tạo một hàm sử dụng class và object để minh họa đa hình với kế thừa. Bao gồm thông tin quốc gia, ngôn ngữ và thủ đô cho Ấn Độ và Mỹ dưới dạng hai hàm sử dụng kế thừa.

Bạn có thể sử dụng prompt này với Python, C# hoặc các ngôn ngữ được hỗ trợ khác. Ví dụ, trong VS Code, hãy tạo file `polymorphism.py` và nhập mã được sinh ra.

Bằng cách tận dụng Amazon Q Developer, bạn có thể nhanh chóng xây dựng giải pháp OOP và khám phá các thực tiễn tốt nhất trong phát triển phần mềm hiện đại.