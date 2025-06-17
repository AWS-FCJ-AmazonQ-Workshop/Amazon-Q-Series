+++
title = "SQL Injection"
date = 2020-05-14T00:38:32+07:00
weight = 2
chapter = false
pre = "<b>2. </b>"
+++

SQL injection vulnerability is present within code when user-provided inputs are not sanitized before being used to generate a SQL database query. An attacker can misuse un-trusted input to run query statements that read, modify, or delete database content.

1. Copy the following code within your IDE. This code is vulnerable to SQL injection attack as it constructs the SQL query by directly concatenating user input (name) into the query string. An attacker could manipulate the name parameter to alter the SQL command, potentially gaining unauthorized access to other data in the database, corrupting the data, or even dropping tables.

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

2. Click on Amazon Q in the status bar and run Project Scan to see how the SQL Injection Vulnerability is detected.
   ![autoscans](/images/1/autoscans.png?width=90pc)

3. Select **Review workspace** or **Review active file**
   ![SQL-Injection](/images/2/sql-injection-1.png?width=90pc)

4. The following finding will be visible in the status bar
   ![SQL-Injection-2](/images/2/sql-injection-2.png?width=90pc)

5. To views details of the findings, hold your cursor over the insecure code and click on “View Details” to learn more:
   ![SQL-Injection-3](/images/2/sql-injection-3.png?width=90pc)
   ![SQL-Injection-3](/images/2/sql-injection-4.png?width=90pc)

6. To fix the SQL Injection vulnerability in the provided code, you should use parameterized queries, also known as prepared statements. This method ensures that user inputs are handled safely, preventing attackers from injecting malicious SQL code.

   Below is an example of how this code can be fixed. Make sure to save the file prior to re-running the scan.

   ```
   def execute_query_compliant(request):
   import sqlite3

   name = request.GET.get("name")

   query = "SELECT * FROM Users WHERE name = ?"

   with sqlite3.connect("example.db") as connection:
       cursor = connection.cursor()
       cursor.execute(query, (name,))  # Use a parameterized query
       connection.commit()
       connection.close()
   ```

7. Try fixing the issue and running the scan again.
