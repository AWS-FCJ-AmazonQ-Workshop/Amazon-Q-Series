---
title: "Introduction to Amazon Q Developer Security"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Introduction to Amazon Q Developer Security

Amazon Q Developer is a next-generation AI assistant that integrates security directly into the software development process[[1]](https://aws.amazon.com/blogs/devops/code-security-scanning-with-amazon-q-developer/)[[2]](https://cloudelligent.com/insights/blog/code-security-amazon-q-developer/). This tool helps you detect, alert, and automatically suggest security fixes as you code, leveraging thousands of continuously updated security detectors from AWS[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html).

#### Overview of Security Capabilities

- **Static Application Security Testing (SAST):** Detects common security issues such as SQL injection, XSS, OS command injection, path traversal, and more[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[4]](https://blog.getsetbuild.cloud/post/secure-coding-with-amazon-q/).

- **Secrets Detection:** Automatically scans for and alerts on hardcoded passwords, API keys, and AWS credentials in your code[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[5]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/code-reviews.html).

- **Infrastructure as Code (IaC) Scanning:** Checks infrastructure configurations (CloudFormation, Terraform, etc.) for misconfigurations and security violations[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[5]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/code-reviews.html).

#### Understanding Security Scanning Modes

Amazon Q Developer provides two main security scanning modes to fit different workflows[[3]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security-scans.html)[[6]](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/start-scan.html):

- **Auto Scans (Real-time):** Automatically scans and alerts as you write code (Pro version only).
- **Project Scans:** Scans the entire project on demand, suitable for periodic checks or pre-release reviews.

Note: It is recommended to keep Auto Scan enabled for early vulnerability detection and combine it with regular Project Scans to ensure the entire codebase is secure.

#### Practical Applications

- **Early Vulnerability Detection:** Proactively identify and address security issues before code reaches production.
- **Automated Remediation:** Receive automatic security fix suggestions, saving time and reducing risk.
- **Compliance Assurance:** Ensure your code always meets the latest AWS and industry security standards.

#### Workshop Objectives

- ✅ Understand the role and benefits of Amazon Q Developer Security
- ✅ Gain hands-on experience with security scanning and automated remediation features
- ✅ Learn best practices for securing code throughout the development lifecycle
- ✅ Develop skills to leverage AI for improving software quality and safety
