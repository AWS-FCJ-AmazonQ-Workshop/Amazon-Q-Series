---
title: "Test Security Prompt"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3 </b> "
---

Now that we have created our vulnerable code samples and security prompt library, let's test how effectively Amazon Q Developer can identify security issues using different prompt strategies.

#### Testing Different Prompt Approaches

**1. General Security Review**

Use the comprehensive security prompt to scan a single file:

```
@Multi-Vulnerability-Scan @vulnerable_app.py
```

![Prompt-Library](/images/7/prompt-lib-5.png?width=90pc)
_Figure 1: Running a general security review on a single file_

- **Purpose**: Perform a broad security analysis covering all 6 vulnerability types in one scan.
- **Expected Output**: General overview of all vulnerabilities with basic remediation suggestions.

**2. Specialized Database Security Check**

Focus specifically on database-related vulnerabilities:

```
@Database-Security-Check @vulnerable_app.py @file_handler.py
```

![Prompt-Library](/images/7/prompt-lib-6.png?width=90pc)
_Figure 2: Running a specialized database security check_

- **Purpose**: Deep dive into SQL injection and credential exposure issues.
- **Expected Output**: Detailed analysis of database security with SQLite/PostgreSQL examples.

**3. Web Application Security Audit**

Concentrate on web application specific vulnerabilities:

```
@Web-App-Security-Audit @vulnerable_app.py
```

![Prompt-Library](/images/7/prompt-lib-7.png?width=90pc)
_Figure 3: Running a web application security audit_

- **Purpose**: Focus on Flask-specific security issues like redirects and command injection.
- **Expected Output**: Web security best practices with Flask-specific remediation.

**4. Comprehensive Multi-File Analysis**

Analyze all vulnerable files simultaneously:

```
@Multi-Vulnerability-Scan @vulnerable_app.py @file_handler.py @auth_service.py
```

![Prompt-Library](/images/7/prompt-lib-8.png?width=90pc)
_Figure 4: Running a comprehensive multi-file security analysis_

- **Purpose**: Complete security assessment across the entire codebase.

- **Expected Output**: Comprehensive report with cross-file vulnerability relationships.

#### Quality Assessment Criteria

For each security finding, verify that Amazon Q provides:

- ✅ **Exact line number** and problematic code snippet
- ✅ **Severity level** (Critical/High/Medium/Low)
- ✅ **Exploitation scenario** explaining the security risk
- ✅ **Secure remediation** with corrected code example
- ✅ **Prevention best practices** to avoid similar issues

#### Comparing Prompt Effectiveness

After testing all scenarios, compare the results:

- **General prompts** provide broad coverage but may lack depth
- **Specialized prompts** offer detailed analysis for specific vulnerability types
- **Multi-file scans** reveal cross-file security relationships and dependencies
