---
title: "Feature Development with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 3.5.1. </b> "
---

Suppose you have an existing codebase implementing a simple calculator. Now, business requirements have changed and you need to enhance it to support scientific calculator functionalities.

In this section, you'll experience using Amazon Q Developer Agent for Software Development to implement additional features. In your IDE, open the Amazon Q Developer Chat panel, type `/dev`, and press Enter twice to bring up the Agent for Software Development in a new tab.

#### Example: Enhancing a Calculator

**Step 1:** Create a new file called `calculator.py` in VSCode and paste in your existing simple calculator code.

```python
class Calculator:
    def add(self, a, b):
        return a + b
    def subtract(self, a, b):
        return a - b
    def multiply(self, a, b):
        return a * b
    def divide(self, a, b):
        return a / b
```

**Step 2:** Use the Agent to add scientific functions (e.g., sin, cos, tan, sqrt, power).

**Step 3:** Review and accept the code suggestions, or iterate as needed.

#### Best Practices
- Use clear prompts describing the new features you want
- Review generated code for correctness and style
- Test new features thoroughly before deploying