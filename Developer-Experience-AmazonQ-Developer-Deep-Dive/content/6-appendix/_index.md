---
title: "Troubleshooting and Performance Optimization"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

#### Common issues & solutions with Amazon Q Developer

- **IAM permissions:** Missing access to AWS services/resources. Q diagnoses and guides IAM adjustments [[1]](https://aws.amazon.com/blogs/aws/amazon-q-developer-now-helps-you-troubleshoot-aws-console-errors/).
- **AWS service config:** Missing parameters or misconfiguration when deploying CloudFormation. Q analyzes root cause and suggests fixes directly in the console [[2]](https://aws.amazon.com/about-aws/whats-new/2023/11/cloudformation-troubleshooting-q-developer-assistance/).
- **Code issues:** Q automatically scans, detects security vulnerabilities, credential leaks, malware, and suggests fixes for Java, Python, JS [[3]](https://aws.amazon.com/q/developer/faqs/) [[4]](https://aws.amazon.com/q/developer/features/).
- **AWS Console errors:** Q helps diagnose and fix errors in the console for EC2, ECS, S3, Lambda, CloudFormation [[1]](https://aws.amazon.com/blogs/aws/amazon-q-developer-now-helps-you-troubleshoot-aws-console-errors/).

#### Optimize workflow with Amazon Q Developer

- **Auto code review & security scan:** Q automatically detects bugs, anti-patterns, and security issues as you code [[4]](https://aws.amazon.com/q/developer/features/).
- **Auto test generation:** Q generates repeatable unit tests, increasing coverage and reliability [[4]](https://aws.amazon.com/q/developer/features/).
- **ChatOps:** Integrate Q into Slack, Teams to monitor and troubleshoot AWS resources in real time [[4]](https://aws.amazon.com/q/developer/features/).
- **Automation agent:** Use agents to auto-generate docs, tests, refactor, upgrade with a single prompt [[5]](https://aws.amazon.com/q/).

#### Debug & code security tools

- **Security scan:** Q automatically detects vulnerabilities, credential leaks, risky code and suggests fixes [[3]](https://aws.amazon.com/q/developer/faqs/) [[4]](https://aws.amazon.com/q/developer/features/).
- **CloudFormation troubleshooting:** Q analyzes IaC deployment errors and suggests detailed fixes [[2]](https://aws.amazon.com/about-aws/whats-new/2023/11/cloudformation-troubleshooting-q-developer-assistance/).
- **Chat debug:** Ask Q about code/AWS errors, get explanations & quick fix guidance [[4]](https://aws.amazon.com/q/developer/features/) [[6]](https://community.aws/content/2fVw1hN4VeTF3qtVSZHfQiQUS16/getting-started-with-amazon-q-developer-in-visual-studio-code).
- **IDE integration:** Get fix, improvement, and security suggestions right in your IDE [[7]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/setup-qdeveloper.html).

#### Diagnostic and troubleshooting workflow with Amazon Q Developer

1. **Identify the issue**
   - Use Amazon Q to analyze error messages in IDE or AWS Console
   - Describe the error in chat with Amazon Q for initial guidance

2. **Analyze the root cause**
   - Amazon Q will analyze code, configurations, and logs to identify the cause
   - Use the "Explain this error" feature in AWS Console when encountering errors [[1]](https://aws.amazon.com/blogs/aws/amazon-q-developer-now-helps-you-troubleshoot-aws-console-errors/)

3. **Apply the solution**
   - Follow Amazon Q's guidance to fix the issue
   - Use code suggestions and auto-fix when available
   - Check the reference documentation suggested by Amazon Q

4. **Verify and confirm**
   - Test again after applying the changes
   - Use Amazon Q to generate unit tests to verify the correctness of the solution

#### Troubleshooting reference documentation

- [Amazon Q Developer Troubleshooting Guide](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/troubleshooting.html)
- [Amazon Q Developer Security Best Practices](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/security-best-practices.html)
- [Amazon Q Developer IDE Setup Guide](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/setup-qdeveloper.html)
- [Amazon Q Developer Community Guide](https://community.aws/content/2fVw1hN4VeTF3qtVSZHfQiQUS16/getting-started-with-amazon-q-developer-in-visual-studio-code)

This section helps you quickly resolve issues, optimize performance, and enhance security when using Amazon Q Developer in your daily development workflow.