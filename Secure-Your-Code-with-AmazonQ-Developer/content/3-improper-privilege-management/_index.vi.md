+++
title = "Improper Privilege Management"
date = 2024-05-14T00:38:32+07:00
weight = 3
chapter = false
pre = "<b>3. </b>"
+++

Privilege escalation occurs when a malicious user exploits a bug, design flaw, or configuration error in an application or operating system to gain elevated access to the system. Elevated privileges can be used to delete files, view private information, or install unwanted programs or backdoors.

1. Copy the following code within your IDE.

   ```
   def set_user_noncompliant():

       import os

       root = 0

       # Noncompliant: the process user is set to root.

       os.setuid(root)
   ```

2. Click on Amazon Q in the status bar and run Project Scan to see how the Improper Privilege Management Vulnerability is detected.
   ![Secure-code](/images/1/secure-code-1.png?width=90pc)

3. Select **Review workspace** or **Review active file**
   ![Privilege-1](/images/3/Privilege-1.png?width=90pc)

4. The following finding will be visible in the status bar
   ![Privilege-2](/images/3/Privilege-2.png?width=90pc)

5. To views details of the findings, hold your cursor over the insecure code and click on "View Details" to learn more:
   ![Privilege-3](/images/3/Privilege-3.png?width=90pc)
   ![Privilege-4](/images/3/Privilege-4.png?width=90pc)

6. Running processes as root should be avoided whenever possible because it can lead to severe security vulnerabilities, including unauthorized access, privilege escalation, and potential system compromise.

   Always follow the principle of least privilege, meaning that processes should run with the minimum permissions necessary to perform their required tasks. This reduces the risk and potential impact of a security breach.

   Below is an example of how this code can be fixed. Make sure to save the file prior to re-running the scan.

   ```
   def set_user_compliant():

       import os

       root = 4

       # Compliant: the process user is set to userid 4.

       os.setuid(root)
   ```

7. Try fixing the issue and running the scan again.
