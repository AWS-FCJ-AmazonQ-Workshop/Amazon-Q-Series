---
title: "Create Security Prompt Library"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.2 </b> "
---

Now we'll create a specialized prompt library for security analysis. These prompts will help standardize our security assessments and ensure comprehensive vulnerability detection.

#### Create Multi-Vulnerability-Scan Prompt

1. In your IDE, open an Amazon Q chat window.

2. Type **@**, and select **Prompts**.

![Prompt-Library](/images/7/prompt-lib-1.png?width=90pc)
_Figure 1: Select Prompts in the Amazon Q chat window_

3. Choose **Create a new prompt**.

![Prompt-Library](/images/7/prompt-lib-2.png?width=90pc)
_Figure 2: Click to create a new prompt_

4. In **Prompt name**, enter a prompt name such as `Multi-Vulnerability-Scan` and press **Enter**.
   _Figure 3: Enter the prompt name and confirm_

![Prompt-Library](/images/7/prompt-lib-3.png?width=90pc)

Amazon Q creates a prompt file called **Multi-Vulnerability-Scan.md** in the _~/.aws/amazonq/prompts_ folder, and opens the file in your IDE.

5. In the prompt file, add a detailed prompt. For example:

```
Scan Python Flask application for these vulnerabilities:
- SQL injection in database queries
- Open redirect in route handlers
- Command injection in subprocess calls
- Path traversal in file operations
- Privilege escalation in access controls
- Hardcoded credentials and API keys

Report: vulnerability type, line number, risk level, exploit scenario, secure code fix.
```

6. Save the prompt file.

#### Create Database-Security-Check Prompt

Repeat the creation process with prompt name `Database-Security-Check` and this content:

```
Focus on database security issues:
- SQL injection via string concatenation
- Unsafe query construction
- Missing parameterized queries
- Database credential exposure

Provide secure SQLite/PostgreSQL examples.

```

#### Create Web-App-Security-Audit Prompt

Create another prompt named `Web-App-Security-Audit` with this content:

```
Audit Flask web application for:
- Unvalidated redirects
- Command injection via user input
- File path manipulation
- Missing input sanitization
- Unsafe subprocess execution

Include Flask security best practices.
```

#### Using Your Security Prompts

1. In your IDE, open an Amazon Q chat window.

2. Type **@**, and select **Prompts**.

3. Choose your saved prompt, for example, **Multi-Vulnerability-Scan**.

4. (Optional) In the chat input window, add details, as required. You can type more text and add more context types. An example prompt might look like this...

```
@Multi-Vulnerability-Scan analyze the @vulnerable_app.py using the files in the @security-test folder
```

5. Submit the prompt and wait for Amazon Q to generate an answer.

![Prompt-Library](/images/7/prompt-lib-4.png?width=90pc)
_Figure 4: Use the prompt and view the security scan results in Amazon Q_

Your security prompt library is now ready for comprehensive vulnerability testing in the next section.
