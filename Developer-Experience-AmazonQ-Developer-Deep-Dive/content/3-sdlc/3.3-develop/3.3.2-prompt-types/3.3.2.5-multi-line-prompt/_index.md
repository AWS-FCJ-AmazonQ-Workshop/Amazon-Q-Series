---
title: "Multi Line Prompt"
date: 2023-08-17T00:00:00-00:00
weight: 5
chapter: false
pre: "<b>3.3.2.5 </b>"
---

Multi Line Prompt
Amazon Q Developer understands your intent and provides suggestions based on directives in multi-line prompts. Using explicit directives (e.g., CREATE, FORMAT, RETURN) in your prompt helps guide the AI to produce the desired outcome, especially for complex requirements.

## Why Use Multi Line Prompts?
- **Explicitness:** Directives clarify your intent for the AI
- **Complexity:** Handle multi-step logic and requirements
- **Customization:** Tailor the generated code to your needs

**Best Practice:** Use clear, imperative language and break down the problem into logical steps within your prompt.

---

### Example #1: Strings and Numbers Formatting
**Prompt:**

```python
# Given a list that contains some numbers and strings,
# **CREATE** a function called `format_list` and
# format the numbers in the list into a string in which the numbers are prepended with a "#"
# and check for strings and wrap in a double quote.
```

Amazon Q Developer Suggestion:

```python
def format_list(lst):
    formatted = []
    for item in lst:
        if isinstance(item, int) or isinstance(item, float):
            formatted.append(f"#{item}")
        elif isinstance(item, str):
            formatted.append(f'"{item}"')
    return ', '.join(formatted)
```

---

### Example #2: Find Maximum Value
**Prompt:**

```python
# **CREATE** a function to find the maximum value in a list
# **RETURN** the maximum value
```

Amazon Q Developer Suggestion:

```python
def find_max(numbers):
    return max(numbers)
```

---

## Key Takeaways
- Use multi-line prompts with explicit directives for complex or multi-step logic
- Break down requirements into clear, actionable steps
- The more detail you provide, the more tailored the code suggestions will be