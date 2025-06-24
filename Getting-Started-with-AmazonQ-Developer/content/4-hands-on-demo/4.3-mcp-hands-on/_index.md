---
title: "Using MCP with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: "4.3. "
---

Guide to using **Model Context Protocol (MCP)** to extend Amazon Q Developer, allowing the AI to look up AWS documentation directly in your IDE.

#### 1. MCP Overview

**Model Context Protocol (MCP)** is an open protocol that allows AI assistants to connect to external services. Main benefits:

- Look up AWS documentation directly in the IDE
- Automate tasks based on project context
- Minimize switching between tools

![MCP Architecture](/images/4-hands-on-demo/4.2-mcp-hands-on/image.png?width=90pc)

*Figure 1: MCP architecture - Connecting Amazon Q Developer with AWS Documentation Server*

#### 2. Configure AWS Documentation MCP Server in Amazon Q Developer

To use the AWS Documentation MCP Server — an official AWS MCP server for looking up AWS docs in your IDE — follow these steps:

**Step 1: Access MCP configuration**
- Open Amazon Q Developer → Chat Tab → **tools** icon

**Step 2: Configure AWS Documentation MCP Server**

| Parameter                | Value                                                                         |
|--------------------------|-------------------------------------------------------------------------------|
| **Scope**                | Global (`~/.aws/amazonq/mcp.json`) or This Workspace (`.amazonq/mcp.json`)    |
| **Name**                 | `AWSDocMCPServer`                                                             |
| **Transport**            | `stdio`                                                                       |
| **Command**              | `uvx`                                                                         |
| **Arguments**            | `awslabs.aws-documentation-mcp-server@latest`                                 |
| **Environment Variables**| `FASTMCP_LOG_LEVEL=ERROR` & `AWS_DOCUMENTATION_PARTITION=aws`                 |

![MCP Server Configuration](/images/4-hands-on-demo/4.2-mcp-hands-on/image-1.png?width=40pc)

*Figure 2: AWS Documentation MCP Server configuration UI with required parameters*

**Step 3: Set permissions**
- Choose **Always allow** for development environments (restrict in production)

![MCP Permissions](/images/4-hands-on-demo/4.2-mcp-hands-on/image-2.png?width=40pc)

*Figure 3: Set MCP Server access permissions - Always allow for development*

#### 3. Using AWS Documentation MCP Server

Basic commands:

**Look up documentation:**
```
look up documentation on S3 bucket naming rule. cite your sources
```

**Keyword search:**
```
search documentation for "Lambda function timeout" limit 3
```

**Suggest related documentation:**
```
recommend content for page https://docs.aws.amazon.com/...
```

![AWS Documentation Query](/images/4-hands-on-demo/4.2-mcp-hands-on/PixPin_2025-06-22_22-13-45.gif?width=40pc)

*Figure 4: Demo looking up S3 bucket naming rules - MCP Server returns markdown content with references*

#### Benefits

- **Increased productivity:** Look up AWS docs directly in the IDE
- **Time saving:** No need to switch browser tabs
- **Accurate information:** Content sourced from official AWS documentation
- **One-time configuration:** Use for all projects

**References:**  
- [AWS Blog: Use Model Context Protocol with Amazon Q Developer](https://aws.amazon.com/blogs/devops/use-model-context-protocol-with-amazon-q-developer-for-context-aware-ide-workflows/)  
- [AWS Documentation MCP Server on GitHub](https://github.com/awslabs/mcp/tree/main/src/aws-documentation-mcp-server)