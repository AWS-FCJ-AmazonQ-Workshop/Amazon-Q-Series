---
title: "Quét bảo mật với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.4.1. </b> "
---

Quét bảo mật
Amazon Q Developer có thể được sử dụng để nhận diện và khắc phục các lỗ hổng bảo mật (security vulnerabilities). Hãy cùng tìm hiểu cách thực hiện.

Tạo một file mới tên là `insecure.cs` trong VSCode, sau đó dán đoạn mã sau vào file đó. Nhớ lưu file lại.

Chỉ dùng cho mục đích học tập
Đoạn mã ví dụ dưới đây có chứa lỗ hổng bảo mật và tuyệt đối không được triển khai vào bất kỳ môi trường production nào. Mã này được viết như vậy để bạn có thể học về tính năng quét bảo mật của Amazon Q Developer. Không sử dụng mã này cho bất kỳ mục đích nào khác ngoài việc học trong khuôn khổ workshop này.

```csharp
using Microsoft.Data.SqlClient;
public class CurrencyServiceInsecure
{
    public bool Delete(string code)
    {
        string connectionString = "Server=myServerAddress;Database=myDataBase;User Id=myUsername;Password=myPassword;";
        using (SqlConnection connection = new SqlConnection(connectionString))
        {
            connection.Open();
            string query = $"DELETE FROM Currencies WHERE Code = {code}";
            using (SqlCommand command = new SqlCommand(query, connection))
            {
                int rowsAffected = command.ExecuteNonQuery();
                return rowsAffected > 0;
            }
        }
    }
}
```

Có hai cách để sử dụng tính năng quét bảo mật (security scan).

**Cách 1: Auto-scan**
Để sử dụng cách này, bạn chỉ cần đảm bảo rằng tính năng auto-scan bảo mật đang được bật. Để kiểm tra trong phần cài đặt nếu bạn dùng VSCode:

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image.png?width=40pc)

Với cách này, bạn chỉ cần chờ vài giây, Amazon Q Developer sẽ tự động quét mã nguồn khi bạn viết. Nếu phát hiện lỗ hổng, bạn sẽ thấy cảnh báo ngay trong dòng mã như hình dưới:

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image-1.png?width=90pc)

Tại đây, bạn có thể nhấn vào Explain để xem chi tiết. Nhấn View Details, sau đó từ panel chi tiết, nhấn tiếp vào Explain. Lúc này Amazon Q Developer sẽ tự động đưa ngữ cảnh và prompt phù hợp vào Chat, bạn sẽ nhận được giải thích về lỗ hổng và hướng dẫn cách khắc phục.

**Cách 2: Quét toàn bộ project (Project-wide scan)**
Để sử dụng cách này:

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image-2.png?width=90pc)

Sau khi quét xong, bạn sẽ thấy tất cả các lỗ hổng được phát hiện trong tab Problems.

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image-3.png?width=40pc)