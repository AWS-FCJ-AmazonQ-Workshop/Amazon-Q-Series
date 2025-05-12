+++
title = "Securing Your Code With Amazon Q Developer"
date = 2024
weight = 1
chapter = false
+++

# Securing Your Code With Amazon Q Developer

Amazon Q can scan your codebase for security vulnerabilities and code quality issues to improve the posture of your applications throughout the development cycle. You can initiate a scan of an entire codebase, analyzing all files in your local project or workspace, or enable auto scans that assess your code as you write it.

This helps your applications to be more secure and resilient by highlighting security issues such as cross-site scripting vulnerabilities, log injections, loose file permissions, hardcoded credentials and more. The earlier security issues are detected, the less work and effort is required to fix the same.

Scan are powered by [Security Detectors](https://docs.aws.amazon.com/codeguru/detector-library/) from the Amazon CodeGuru Detector Library. As security policies are updated and detectors are added, scans automatically incorporate new detectors to ensure your code is compliant with the most up-to-date policies.

Amazon Q Developer detects security policy violations and vulnerabilities in your code with static application security testing (SAST), secrets detection, and infrastructure as code (IaC) scanning. Security issues found during the scan are highlighted in the Problems panel in VS Code.

In this section, we will use the Security Scanning features of Q Developer to detect insecure code.

{{% notice note %}}
This module deliberately includes code fragments that will trigger security scan findings. Code fragments in this module should only be used for demonstration purposes.
{{% /notice %}}

Amazon Q can scan your entire codebase, or auto-scan your code as you write it. For the purposes of this workshop we will be using project based scanning. Upto 100 MB of code can be scanned at a time.

#### Scan your project

1. Choose the text, Amazon Q, from the rectangular area at the bottom of the IDE window.
2. A drop-down window will appear at the top from which the user may choose Run Project Scan.

![Secure-code](/images/1/secure-code-1.png?width=90pc)
