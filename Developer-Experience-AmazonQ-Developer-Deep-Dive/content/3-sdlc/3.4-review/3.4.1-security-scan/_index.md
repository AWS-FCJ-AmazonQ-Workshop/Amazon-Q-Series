---
title: "Security Scan with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.4.1. </b> "
---

#### Security Scan

Amazon Q Developer can help you identify and remediate security vulnerabilities in your code. This feature is essential for building secure applications and preventing common threats.

#### How to Use Security Scan
1. **Create a new file** (e.g., `insecure.cs`) in VSCode and paste in the following code block:

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

> **Note:** This sample code contains a security vulnerability (SQL injection) and should never be used in production. It is for learning purposes only.

2. **Save the file.**
3. **Highlight the code block, right-click, and choose** `Amazon Q Developer > Security Scan`.
4. **Review the results.** Amazon Q Developer will identify vulnerabilities and suggest remediations, such as using parameterized queries.

#### Best Practices
- Always scan new and updated code for security issues
- Address vulnerabilities before deploying to production
- Use secure coding patterns and validate all user input