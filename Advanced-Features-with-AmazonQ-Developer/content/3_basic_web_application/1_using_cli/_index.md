---
title: "Using Amazon Q Developer CLI"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

#### Prerequisites

{{% notice note %}}
Ensure you have completed [Environment Setup](2_invironment_setup/).
{{% /notice %}}

**1.** Input prompt to create Sudoku web application in Terminal

```
create simple html sudoku web application and save into file
```

![CLI-Development](/images/3_basic_web_application/1_using_cli/cli-development-1.png?width=90pc)

**2.** Press **t** or **y** to allow Q execute the command to create file

![CLI-Development](/images/3_basic_web_application/1_using_cli/cli-development-2.png?width=90pc)

**3.** Amazon Q Developer CLI will be able to:

- Create an HTML file which you can see in Project Explorer.
- Describe the application details and usage.

![CLI-Development](/images/3_basic_web_application/1_using_cli/cli-development-3.png?width=90pc)

**4.** Open the HTML file and click on **Go Live**

![CLI-Development](/images/3_basic_web_application/1_using_cli/cli-development-4.png?width=90pc)

**5.** You will be able to see the web page and play Sudoku

![CLI-Development](/images/3_basic_web_application/1_using_cli/cli-development-5.png?width=90pc)

**6.** Delete all files

```
!rm -rf *
```

**7.** Exit Q chat

```
# Exit Q chat
/quit

# Re-enter Q Chat
q
```
