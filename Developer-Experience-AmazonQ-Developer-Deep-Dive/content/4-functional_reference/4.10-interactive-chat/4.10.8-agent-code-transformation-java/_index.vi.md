---
title: "Agent chuyển đổi mã nguồn: Java"
date: "`r Sys.Date()`"
weight: 8
chapter: false
pre: " <b> 4.10.8 </b> "
---

## Amazon Q: Agent chuyển đổi mã nguồn (Java)

Amazon Q Developer Agent giúp bạn chuyển đổi dự án Java (ví dụ: Java 8 sang Java 17). Mở dự án trong IDE, dùng Q Chat với lệnh `/transform` để bắt đầu chuyển đổi.

### Quy trình chuyển đổi Java 8 sang Java 17

1. **Bắt đầu Agent chuyển đổi mã nguồn**
   - Tab Agent for Code Transformation sẽ hiển thị form với các tùy chọn:
     - Location: Thư mục gốc của dự án Java cần chuyển đổi
     - Source: Phiên bản nguồn (Java 8 hoặc 11)
     - Target: Phiên bản đích (Java 17)
   - Chọn Confirm sau khi đã chọn các tùy chọn

2. **Xây dựng dự án**
   - Agent sẽ cố gắng build dự án trước khi bắt đầu quá trình chuyển đổi
   - Mặc định sẽ dùng lệnh `mvn test`, hoặc có thể chọn `mvn test-compile` để bỏ qua unit tests
   - Chọn Confirm để tiếp tục

3. **Cung cấp đường dẫn JDK**
   - Agent cần đường dẫn thư mục JDK được cài đặt trong môi trường phát triển
   - Sử dụng lệnh `/usr/libexec/java_home -v 1.8` (Linux/MacOS) để tìm đường dẫn
   - Sao chép đường dẫn vào chat và nhấn Enter để bắt đầu build

4. **Quá trình xây dựng và phân tích**
   - Quá trình build có thể mất đến 10 phút tùy thuộc vào kích thước dự án
   - Sau khi build thành công, Agent sẽ quét các file dự án và chuẩn bị bắt đầu công việc
   - Agent cần tải các artifacts dự án lên tài khoản của bạn
   - Có thể hủy quá trình chuyển đổi bằng nút "Cancel Transformation"
   - Theo dõi tiến trình bằng nút "Open Transformation Hub"

5. **Tạo kế hoạch chuyển đổi**
   - Agent sẽ build mã nguồn bằng Java 8 trong môi trường build an toàn
   - Phân tích mã nguồn để tạo kế hoạch chuyển đổi
   - Mở kế hoạch chuyển đổi trong tab mới trong IDE để bạn xem qua các thay đổi cần thiết
   - Tự động bắt đầu thực hiện kế hoạch để chuyển đổi dự án Java 8 (hoặc 11) sang Java 17

6. **Kế hoạch chuyển đổi bao gồm**
   - Cập nhật phiên bản JDK và thay đổi dependencies và mã liên quan
   - Thay thế các đoạn mã đã lỗi thời
   - Áp dụng thay đổi mã cho dependencies bổ sung và giải quyết lỗi biên dịch
   - Tạo thay đổi mã để bạn xem xét trước khi chấp nhận

7. **Chấp nhận chuyển đổi**
   - Sau khi Agent hoàn thành kế hoạch chuyển đổi, bạn sẽ có tùy chọn tải xuống các thay đổi đề xuất
   - Chọn "Download Proposed Changes" để tải mã và nhật ký thay đổi dưới dạng pull request git cục bộ
   - Xem xét từng thay đổi mã đề xuất trong mỗi file dưới dạng git diff
   - Chấp nhận hoặc từ chối bằng cách chọn tùy chọn tương ứng
   - Khi chọn Accept, các thay đổi file sẽ được áp dụng vào thư mục cục bộ

8. **Tóm tắt chuyển đổi mã nguồn**
   - Xem tóm tắt chuyển đổi mã nguồn để biết thông tin và thống kê về các thay đổi mã
   - Xem xét các dependencies đã lỗi thời

> **Lưu ý:** Đảm bảo dự án đáp ứng các điều kiện tiên quyết (Maven, JDK, build thành công...) trước khi chuyển đổi.