---
title: "Create AWS Cloud Development Kit (CDK) via CLI"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.1 </b> "
---

#### Prerequisites

{{% notice note %}}
If you haven't finished [UI Enhancement with Advanced Prompting Techniques](3_basic_web_application/4_ui_enhancement/)
{{% /notice %}}

Run the following prompt to create Sudoku game which will deploy in this lab.

```
I want to create simple html Sudoku game UI with the following features:
1. A modern, clean design with a color scheme that reduces eye strain
2. A responsive layout that works well on both desktop and mobile devices
3. Visual feedback for selected cells, valid/invalid entries, and completed rows/columns/boxes
4. A game info panel showing:
   - Current difficulty level
   - Timer
   - Number of mistakes
   - Completion percentage
5. Animations for cell selection and number placement
6. Support for both mouse and keyboard input
```

**1.** Create Infrastructure as Code (IaC) -> AWS Cloud Development Kit (CDK)

```
Use AWS Cloud Development Kit (CDK) to implement infrastructure as code in Python.
By using AWS solutions as follows:
- Host web application in Amazon S3 private bucket
- Deliver web through Amazon CloudFront.
```

**3.** Verify output

Amazon Q Developer will create CDK and provide instructions to deploy to AWS

![CDK-Creation](/images/4_deployment_with_cdk/1_cdk_creation/cdk-creation-1.png?width=90pc)
