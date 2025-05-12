+++
title = "Path Traversal"
date = 2024-05-14T00:38:32+07:00
weight = 4
chapter = false
pre = "<b>4. </b>"
+++

Constructing path names with unsanitized user input can lead to path traversal attacks (for example, ../../..). This type of attack exploits insufficient security validation/sanitization of user-supplied input file names, allowing attackers to access files or directories that are not intended to be accessible. This can lead to unauthorized access, information disclosure, and even system compromise.

1. Copy the following code within your IDE.

   ```
   def verify_file_path_noncompliant():

       from flask import request

       file_path = request.args["file"]

       # Noncompliant: user input file path is not sanitized.

       file = open(file_path)

       file.close()
   ```

2. Click on Amazon Q in the status bar and run Project Scan to see how the Path Traversal Vulnerability is detected.
   ![autoscans](/images/1/autoscans.png?width=90pc)

3. The following finding will be visible in the status bar
   ![Path-Traversal-1](/images/4/Path-Traversal-1.png?width=90pc)
4. To views details of the findings, hold your cursor over the insecure code and click on "View Details" to learn more:
   ![Path-Traversal-2](/images/4/Path-Traversal-2.png?width=90pc)
5. Path traversal vulnerabilities can be mitigated by sanitizing user input before using it to construct a file path. This approach involves checking if the user-supplied file path is within a predefined list of allowed paths

   Below is an example of how this code can be fixed. Make sure to save the file prior to re-running the scan.

   ```
   def verify_file_path_compliant():

       from flask import request

       base_path = "/var/data/images/"

       file_path = request.args["file"]

       allowed_path = ["example_path1", "example_path2"]

       # Compliant: user input file path is sanitized.

       if file_path in allowed_path:

           file = open(base_path + file_path)

           file.close()
   ```

6. Try fixing the issue and running the scan again.
