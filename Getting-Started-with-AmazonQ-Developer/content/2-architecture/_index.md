---
title: "Architecture and How It Works"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

#### Overview Architecture & IDE Integration

Amazon Q Developer is a deeply integrated AI assistant in popular IDEs such as Visual Studio Code and JetBrains. Developers can interact directly with Q right inside the IDE via multi-line code suggestions, inline chat, and task automation. In addition, Q supports the CLI, translates natural language to bash commands, and accelerates terminal operations.

![Amazon Q in VSCode](/images/2-architecture/image.png?width=90pc)

*Figure 1: Illustration of Amazon Q Developer integration in Visual Studio Code*

#### Multi-language Programming Support

Amazon Q Developer supports more than 25 popular programming languages:

- Python
- Java
- JavaScript
- C#
- TypeScript
- Go
- Ruby

Q understands context & project structure, generating accurate code suggestions tailored to each language and the project's coding style [\[1\]](https://aws.amazon.com/q/developer/) [\[2\]](https://aws.amazon.com/q/developer/features/).

#### Interaction with AWS SDK, CLI & AWS Services

Q Developer not only supports code but is also tightly integrated with the AWS ecosystem:

- **AWS SDK & CLI:** Q automatically generates and optimizes code using AWS SDK, writes CLI commands, or converts actions on the AWS Console into reusable code.
- **AWS Services:** Supports architecture design, cost analysis, testing, and deployment for services like Lambda, S3, DynamoDB, etc.
- **Automation Agent:** Q can automate task chains such as generating docs, auto testing, refactoring, and upgrading with just one prompt [\[2\]](https://aws.amazon.com/q/developer/features/) [\[4\]](https://aws.amazon.com/q/developer/build/) [\[8\]](https://aws.amazon.com/q/developer/operate/).

#### Pricing & Service Tiers

Amazon Q Developer offers multiple tiers suitable for individuals and enterprises:

- **Free Tier:** Experience basic features, limited number of suggestions & queries.
- **Professional Tier:** Advanced customization, multi-language support, internal repo integration, security scanning, advanced automation [\[5\]](https://aws.amazon.com/q/developer/pricing/).

![Amazon Q Developer Pricing Tiers](/images/2-architecture/image-1.png?width=70pc)

*Figure 2: Amazon Q Developer service tiers*

Choose the right tier to optimize costs and maximize the power of Q Developer.
