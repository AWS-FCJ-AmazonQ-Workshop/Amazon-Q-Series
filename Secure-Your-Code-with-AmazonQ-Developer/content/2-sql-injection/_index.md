+++
title = "SQL Injection"
date = 2020-05-14T00:38:32+07:00
weight = 2
chapter = false
pre = "<b>2. </b>"
+++

SQL injection vulnerability is present within code when user-provided inputs are not sanitized before being used to generate a SQL database query. An attacker can misuse un-trusted input to run query statements that read, modify, or delete database content.

Copy the following code within your IDE. This code is vulnerable to SQL injection attack as it constructs the SQL query by directly concatenating user input (name) into the query string. An attacker could manipulate the name parameter to alter the SQL command, potentially gaining unauthorized access to other data in the database, corrupting the data, or even dropping tables.

```
def execute_query_noncompliant(request):

    import sqlite3

    name = request.GET.get("name")

    query = "SELECT * FROM Users WHERE name = " + name + ";"

    with sqlite3.connect("example.db") as connection:

        cursor = connection.cursor()

        # Noncompliant: user input is used without sanitization.

        cursor.execute(query)

        connection.commit()

        connection.close()
```

Click on Amazon Q in the status bar and run Project Scan to see how the SQL Injection Vulnerability is detected.
![Secure-code](/images/1/secure-code-1.png?width=90pc)
