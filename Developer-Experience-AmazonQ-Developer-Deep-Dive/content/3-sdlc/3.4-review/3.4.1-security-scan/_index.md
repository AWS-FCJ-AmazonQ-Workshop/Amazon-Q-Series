---
title: "Security Scan with Amazon Q Developer"
date: "July 6, 2025"
weight: 2
chapter: false
pre: " <b> 3.4.1. </b> "
---

Security Scan
Amazon Q Developer can be used to identify and remediate security vulnerabilities. Let’s explore how to do this.

Create a new file named `insecure.cs` in VSCode, then paste the following code into the file. Remember to save the file.

For learning purposes only
The example code below contains security vulnerabilities and must not be deployed in any production environment. This code is written this way so you can learn about the security scan feature of Amazon Q Developer. Do not use this code for any purpose other than learning within the scope of this workshop.

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

There are two ways to use the security scan feature.

**Method 1: Auto-scan**
To use this method, you just need to ensure that the auto-scan security feature is enabled. To check in the settings if you are using VSCode:

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image.png?width=40pc)

With this method, you just need to wait a few seconds, and Amazon Q Developer will automatically scan the source code as you write. If vulnerabilities are detected, you will see warnings directly in the code line as shown below:

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image-1.png?width=90pc)

Here, you can click on Explain to see details. Click View Details, then from the details panel, click Explain again. At this point, Amazon Q Developer will automatically provide context and a suitable prompt in Chat, and you will receive an explanation of the vulnerability and guidance on how to fix it.

**Method 2: Project-wide scan**
To use this method:

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image-2.png?width=90pc)

After the scan is complete, you will see all detected vulnerabilities in the Problems tab.

![alt text](/images/3-sdlc/3.4-review/3.4.1-security-scan/image-3.png?width=40pc)