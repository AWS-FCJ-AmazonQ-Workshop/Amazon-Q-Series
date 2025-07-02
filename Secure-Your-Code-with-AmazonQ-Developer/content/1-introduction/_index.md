---
title: "Introduction to Secure Code With Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Introduction to Secure Code With Amazon Q Developer

Welcome to the "Secure Your Code With Amazon Q Developer" Workshop! This is a hands-on session on source code security using AI with Amazon Q Developer—a conversational AI assistant that helps you understand, build, and secure AWS applications effectively[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[2]](https://aws.amazon.com/q/developer/features/).

Amazon Q Developer not only supports code completion but can also scan your source code, detect and suggest fixes for security vulnerabilities, update, debug, and optimize your code[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[3]](https://dev.to/__spyros/revolutionizing-code-security-how-amazon-q-developer-safeguards-modern-applications-19f7).

#### Workshop Objectives

This workshop focuses on the **Security Scanning (/review)** feature of Amazon Q Developer to detect security policy violations and vulnerabilities in your source code, thereby improving overall security quality[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[4]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/). Amazon Q Developer uses **Static Application Security Testing (SAST)**, **secrets detection**, **software composition analysis** and **Infrastructure as Code (IaC) scanning** to identify security issues[[5]](https://www.blackduck.com/glossary/what-is-sast.html)[[6]](https://orca.security/glossary/secrets-detection/)[[7]](https://www.wiz.io/academy/iac-scanning).

This tool is powered by the **Amazon CodeGuru Detector Library** with thousands of security detectors across various programming languages[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[8]](https://aws.amazon.com/blogs/aws/new-for-amazon-codeguru-reviewer-detector-library-and-security-detectors-for-log-injection-flaws/). As security policies are updated and new detectors are added, Amazon Q automatically integrates them to ensure your source code complies with the latest policies[[4]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/).

#### Security Scanning Features

Amazon Q Developer can scan your entire codebase or automatically scan code as you write. This workshop will focus on **project-based scanning** with the ability to scan up to **100 MB code** at a time.

The tool helps detect security issues such as:

- **Cross-site scripting vulnerabilities (XSS)**: Injecting malicious code into web pages.
- **Log injections**: Inserting harmful data into logs.
- **Loose file permissions**: Files with overly broad access rights.
- **Hardcoded credentials**: Storing passwords or API keys directly in source code.
- **SQL Injection**: Injecting malicious SQL code into queries.
- **Secrets exposure**: Sensitive information leaked in code or logs.

![scanning-models](/images/1/AmazonQ-Scanning-models.png?width=90pc)

#### Prompt Library

mazon Q Developer currently allows you to build a library of common prompts, stored as Markdown files in the **~/.aws/amazonq/prompts** directory. This enables prompt reuse across multiple conversations and projects, which is especially useful for generating diagrams such as **Entity-Relationship (ER) diagram** or **sequence diagram**.

#### Why is this Workshop Important?

Early detection of vulnerabilities helps reduce the cost and effort of remediation. Amazon Q Developer supports "**shift-left security**" integrating security early in the software development lifecycle (SDLC) instead of treating it as a final step[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[4]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/).

With advanced static analysis and machine learning, Amazon Q Developer not only detects vulnerabilities but also provides **auto-generated code fixes** for identified issues[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[3]](https://dev.to/__spyros/revolutionizing-code-security-how-amazon-q-developer-safeguards-modern-applications-19f7). This helps developers not only understand what the problem is but also how to fix it effectively.

This workshop will equip you with practical knowledge and skills to use Amazon Q Developer effectively in building safer and more secure applications.
