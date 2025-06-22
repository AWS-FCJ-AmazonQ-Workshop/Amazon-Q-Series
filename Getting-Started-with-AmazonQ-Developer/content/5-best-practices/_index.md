---
title: "Best Practices for Working with Amazon Q"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

#### How to provide proper context for accurate results

To get precise suggestions from Amazon Q Developer, always provide full context:  
- Programming language, framework  
- Coding goal or feature  
- Technical constraints, performance requirements  
- Related code snippet or encountered error (if any)  

This helps the AI understand your problem and avoids inaccurate results [[1]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/introduction.html) [[7]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/onboarding.html).

#### Effective prompt engineering techniques

A good prompt should have:  
- **Clear goal:** e.g. "Optimize DB query under 100ms."
- **Technical constraints:** e.g. "Use Java 17, Hibernate."
- **Output requirements:** e.g. "Return complete Java code with comments."
- **Illustrative example:** The more specific, the better.

Applying these elements reduces editing and increases the effectiveness of your interaction with Amazon Q Developer [[3]](https://aws.amazon.com/blogs/devops/mastering-amazon-q-developer-part-1-crafting-effective-prompts/).

![alt text](/images/5-best-practices/image.png)

*Figure 1: Example of effective prompt engineering*

#### Review and edit AI-suggested code

Even though Amazon Q Developer is powerful, always review carefully:  
- Assess code correctness and efficiency  
- Test for technical and security issues  
- Edit to match your project's coding conventions  

This process ensures software quality and reduces risk [[1]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/introduction.html) [[4]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/code-recommendations.html).

#### Customize Amazon Q Developer for internal codebases

You can tailor Q Developer for your environment:  
- Embed internal libraries, APIs, coding rules into the AI context  
- Customize suggestions to your organization's architecture and security standards  
- Manage extended context so AI understands your codebase deeply  

This increases the accuracy and practical value of suggestions [[2]](https://aws.amazon.com/blogs/devops/april-2025-amazon-q-developer/) [[7]](https://docs.aws.amazon.com/prescriptive-guidance/latest/best-practices-code-generation/onboarding.html).

Applying these best practices helps you maximize the power of Amazon Q Developer, boost productivity, and ensure software quality.
