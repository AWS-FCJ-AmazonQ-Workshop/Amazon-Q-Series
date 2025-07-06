---
title: "Single Line Comment"
date: 2023-08-17T00:00:00-00:00
weight: 2
chapter: false
pre: "<b>3.3.2.2 </b>"
---

Single Line Comment
Amazon Q Developer can understand your intent and provide intelligent code suggestions based on concise single line comments. This approach is ideal for simple functions or when you want to quickly prototype logic without writing detailed documentation.

## Why Use Single Line Comments?
- **Speed:** Instantly generate code for common tasks
- **Clarity:** A well-written comment can express intent clearly
- **Simplicity:** Great for small, focused functions

**Best Practice:** Write comments that are action-oriented and specific about the function's purpose.

---

### Example #1: Print a Message
**Prompt:**

```python
# function to print a message
```

Amazon Q Developer Suggestion:

```python
def print_message(message):
    print(message)
    return
```

---

### Example #2: Add Two Numbers
**Prompt:**

```python
# function to add two numbers
```

Amazon Q Developer Suggestion:

```python
def add_numbers(a, b):
    return a + b
```

---

## Key Takeaways
- Use single line comments for quick, simple code generation
- Be specific in your comment to get the most relevant suggestion
- For more complex logic, consider using multi-line comments or prompts