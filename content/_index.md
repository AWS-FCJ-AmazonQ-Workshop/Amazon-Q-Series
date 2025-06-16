+++
title = "Getting started with Amazon Q Developer"
date = 2024
weight = 1
chapter = false
authors = ["Tran Doan Cong Ly", "Van Hoang Kha", "Minh Nghia"]
+++

# Getting Started with Amazon Q Developer

#### What is Amazon Q Developer?

**ℹ️ Information**: Amazon Q Developer is a generative AI-powered conversational assistant that helps you understand, build, extend, and operate AWS applications. It provides contextually relevant and actionable answers about AWS architecture, resources, best practices, documentation, and support.

When integrated into your development environment (IDE), Amazon Q Developer provides comprehensive software development assistance through:

- **Code chat and explanations** - Interactive code discussions and detailed explanations
- **Inline code completions** - Real-time code suggestions as you type
- **New code generation** - Generate entire functions and code blocks from natural language
- **Security vulnerability scanning** - Automated detection of security issues in your code
- **Code upgrades and improvements** - Modernize and optimize existing codebases
- **Multi-file feature implementation** - Plan and implement features across your entire project

**ℹ️ Information**: Amazon Q Developer is powered by Amazon Bedrock, a fully managed service that provides foundation models (FMs) through an API. The model has been enhanced with high-quality AWS content to deliver complete, actionable, and well-referenced answers.

{{% notice note %}}
**🔒 Security Note**: Amazon Q Developer is built on Amazon Bedrock and includes automated abuse detection to enforce safety, security, and responsible AI use.
{{% /notice %}}

#### Getting Started with Amazon Q Developer

You can access Amazon Q Developer through multiple interfaces to fit your workflow:

#### AWS Apps and Websites

**Prerequisites:**
1. Add the [necessary permissions](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/security_iam_id-based-policy-examples.html) to your IAM identity
2. Select the Amazon Q icon to start chatting in:
   - AWS Management Console
   - AWS Documentation website
   - AWS website
   - AWS Console Mobile Application

**ℹ️ Information**: For detailed instructions, see [Using Amazon Q Developer on AWS apps and websites](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-on-aws.html).

#### Integrated Development Environments (IDEs)

Download the Amazon Q extension and sign in using your AWS Builder ID (no AWS account required) for free access.

**Supported IDEs:**

- {{% button href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.amazon-q-vscode" %}} **Visual Studio Code**{{% /button %}}
  
  *Installation and Configuration Guide:*
  {{< youtube i0zQpJPfSdU >}}

- {{% button href="https://plugins.jetbrains.com/plugin/24267-amazon-q/" %}} **JetBrains IDEs** (IntelliJ IDEA, PyCharm, WebStorm, etc.){{% /button %}}
  
  *Installation and Configuration Guide:*
  {{< youtube -iQfIhTA4J0 >}}

- {{% button href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.AWSToolkitforVisualStudio2022" %}} **Visual Studio (AWS Toolkit)**{{% /button %}}

- {{% button href="https://marketplace.eclipse.org/content/amazon-q" %}} **Eclipse IDEs** (Preview){{% /button %}}

**ℹ️ Information**: Click the Amazon Q icon in your IDE to start chatting or initiate development workflows. For more information, see [Installing the Amazon Q Developer extension or plugin in your IDE](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-in-IDE-setup.html).

#### Command Line Interface

Amazon Q Developer is available for command line use across multiple platforms:

**Supported Platforms:**
- [macOS](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-macos)
- [Linux AppImage](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-appimage)
- [Ubuntu](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html#command-line-installing-ubuntu)

**Key CLI Features:**
- Natural language to shell command translation
- Contextual command completion
- Multi-language support
- Complex query handling

**ℹ️ Information**: For detailed instructions, see [Using Amazon Q Developer on the command line](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line.html).

#### Chat Applications

Integrate Amazon Q Developer into your team's communication workflow:

**Prerequisites:**
1. Add the [AmazonQDeveloperAccess](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/managed-policy.html#amazonq-policy-fullaccess) managed policy to your IAM identity
2. Configure channel guardrails for your chat applications

**Supported Platforms:**
- Microsoft Teams
- Slack
- AWS-specific chat interfaces

**ℹ️ Information**: For detailed instructions, see [Chatting with Amazon Q Developer in chat applications](https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/q-in-chat-applications.html).

#### Amazon Q Developer Pricing

Amazon Q Developer offers flexible pricing options:

#### Free Tier
- Monthly usage limits with generous allowances
- Basic features and capabilities
- AWS Builder ID authentication
- Individual developer use

#### Amazon Q Developer Pro
- Advanced features and customization
- Higher usage limits
- Team collaboration features
- Enterprise-grade security and compliance

**ℹ️ Information**: For detailed pricing information, see [Amazon Q Developer pricing](https://aws.amazon.com/q/developer/pricing).

#### What's New in Amazon Q Developer

#### Recent Enhancements
- **Software Development Agent (/dev)**: Automatically plan and implement features across multiple files
- **Code Transformation Agent (/transform)**: Upgrade Java applications from Java 8/11 to Java 17
- **Enhanced Security Scanning**: Support for 10+ programming languages
- **Improved Code Generation**: Better context awareness and accuracy
- **AWS Resource Integration**: Direct integration with AWS services and resources

#### Migration from Amazon CodeWhisperer
Amazon CodeWhisperer capabilities are now fully integrated into Amazon Q Developer, including:
- Inline code suggestions
- Security vulnerability scanning
- Code reference tracking
- Multi-language support

All existing CodeWhisperer users can seamlessly transition to Amazon Q Developer with enhanced capabilities.
