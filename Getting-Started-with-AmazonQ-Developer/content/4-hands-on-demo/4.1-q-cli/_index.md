---
title: "Building DevOps Project and Architecture with Amazon Q CLI"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1. </b> "
---

This section provides instructions on using **Amazon Q CLI** together with the **Model Context Protocol (MCP)** to automate the process of building DevOps Projects and Architecture Diagrams, helping to optimize development speed and infrastructure operations.

#### Prerequisites

1. Install `uv` from [Astral](https://docs.astral.sh/uv/getting-started/installation/) or the [GitHub README](https://github.com/astral-sh/uv#installation)
2. Install Python: `uv python install 3.10`
3. Install [GraphViz](https://www.graphviz.org/)

#### Step 1: Launch Amazon Q CLI and create a project directory

- Create a new directory for your DevOps Project:

```bash
mkdir devops-project
cd devops-project
```

- Launch Amazon Q CLI:

```bash
q chat
```

- This workshop uses the latest `claude-4-sonnet` model from Anthropic to improve overall project efficiency.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image.png?width=90pc)
*Figure 1: Q Chat CLI interface*

#### Step 2: Configure MCP Servers for DevOps and Architecture

- Create an MCP config file at `~/.aws/amazonq/mcp.json` (or `.amazonq/mcp.json` in your project directory) with the following example content:

```json
{
  "mcpServers": {
    "cdk-mcp-server": {
      "command": "uvx",
      "args": ["cdk-mcp-server@latest"],
      "env": {},
      "disabled": false,
      "autoApprove": []
    },
    "aws-diagram-mcp-server": {
      "command": "uvx",
      "args": ["aws-diagram-mcp-server@latest"],
      "env": {},
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

- Save and restart Q CLI to load the MCP servers.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image-1.png?width=90pc)
*Figure 2: Q CLI after loading MCP Tools*

#### Step 3: Create an Architecture Diagram

- In Q CLI, enter the following prompt:

```
Create an architecture diagram for a scalable web application using AWS services including VPC, ALB, ECS, RDS, and CloudWatch.
```

![alt text](/images/4-hands-on-demo/4.1-q-cli/gif-1.gif?width=90pc)
*Figure 3: Automatically generating an Architecture Diagram*

- Q CLI will call the `aws-diagram-mcp-server` MCP server to generate the Architecture Diagram and return either a drawing or a detailed description.

![alt text](/images/4-hands-on-demo/4.1-q-cli/image-2.png?width=90pc)
*Figure 4: Architecture successfully generated*

#### Step 4: Generate Terraform/CDK code for infrastructure deployment

- Continue in Q CLI and enter:

```
Generate Terraform code for the above architecture with autoscaling ECS cluster and multi-AZ RDS.
```

- Q CLI will use the `cdk-mcp-server` MCP server to generate complete Terraform/CDK code.

![alt text](/images/4-hands-on-demo/4.1-q-cli/gif-2.gif?width=90pc)
*Figure 5: Successfully generated Terraform Code*

#### Step 5: Generate documentation and automate the DevOps workflow

- Request project documentation:

```
Generate a README.md explaining the architecture and deployment steps.
```

![alt text](/images/4-hands-on-demo/4.1-q-cli/image-3.png?width=90pc)
*Figure 6: Successfully generated README file*

#### Summary

- Amazon Q CLI combined with MCP server helps you quickly build complex DevOps Projects, from Architecture design, infrastructure code generation to deployment automation.
- All operations are performed using natural language in the CLI, reducing time and minimizing manual errors.
- MCP server is easily extensible and can integrate with various tools and services.
