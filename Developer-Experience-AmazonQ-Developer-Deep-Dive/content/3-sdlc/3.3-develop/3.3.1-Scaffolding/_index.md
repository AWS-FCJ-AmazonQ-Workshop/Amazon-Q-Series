---
title: "Project Scaffolding with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.3.1. </b> "
---

Scaffolding is the process of setting up the foundational structure for your application or service. Amazon Q Developer can help you quickly generate project frameworks, boilerplate code, and essential resources, allowing your team to focus on building features rather than repetitive setup tasks.

#### Scenario: Setting Up a Team Project
Suppose you need to create a framework for a team of developers to collaboratively build multiple Web APIs. Amazon Q Developer can guide you through this process step-by-step.

##### Example 1: Manual Prompting for Scaffolding

**Prompt:**
Open Q Chat in your IDE and enter the following prompt:

```text
I need to create a project framework where a team of C# developers will be able to develop multiple Web APIs cohesively. Let’s start with just 1 simple API called QDevWorkshop.API.ReferenceData that references a common class library called QDevWorkshop.API.Common. The Web API needs to be deployed as a serverless container on AWS using CDK. I am using VSCode. Guide me on how to do this please.
```

**Sample Response:**
Amazon Q Developer will provide a step-by-step plan, including project structure, code snippets, and deployment instructions. You can follow these steps to scaffold your project or use them as a reference for your own setup.

![alt text](/images/3-sdlc/3.3-develop/3.3.1-Scaffolding/image.png?width=40pc)

> **Tip:** If you are short on time or following the L200 track, you may skip the hands-on steps. The key takeaway is that Amazon Q Developer can accelerate your project setup.

---

##### Example 2: Using the Agent for Software Development

Amazon Q Developer also offers an Agent for Software Development, which can automate even more of the scaffolding process.

**Prompt:**
Open Q Chat in your IDE, type `/dev`, and press Enter twice to launch the Agent for Software Development.

Then enter:

```text
Create a project framework where a team of C# developers will be able to develop multiple Web APIs cohesively. Scaffold 1 boilerplate API called QDevWorkshop.API.ReferenceData that references a common class library called QDevWorkshop.API.Common. The ReferenceData web API should have a currencies resource supporting a GET method, returning a list of hardcoded currency symbols. Common has some helper methods such as conversion of object to json string. The Web API needs to be deployed as a serverless container on AWS using CDK.
```

**Sample Response:**
The agent will generate a detailed development plan and code suggestions. Review the proposed code, accept or provide feedback, and iterate as needed. Once satisfied, you can insert the generated code directly into your workspace.

![alt text](/images/3-sdlc/3.3-develop/3.3.1-Scaffolding/image-1.png?width=40pc)
---

#### Best Practices for Scaffolding
- **Be Specific:** Clearly define your requirements in the prompt for more accurate scaffolding.
- **Iterate:** Use feedback and code review features to refine the generated structure.
- **Leverage Automation:** Use the Agent for Software Development for complex or multi-service projects.
- **Document:** Ensure your scaffolded project includes documentation for future contributors.

{{% notice tip %}}
**Pro Tip:** Amazon Q Developer can scaffold projects in multiple languages and frameworks. Adjust your prompt to match your technology stack and deployment targets.
{{% /notice %}}