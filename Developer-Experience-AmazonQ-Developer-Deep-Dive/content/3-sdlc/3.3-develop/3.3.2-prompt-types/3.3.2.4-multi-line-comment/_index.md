---
title: "Multi Line Comment"
date: 2023-08-17T00:00:00-00:00
weight: 4
chapter: false
pre: "<b>3.3.2.4 </b>"
---

Multi Line Comment
Amazon Q Developer understands your intent and provides suggestions based on multi-line comments. This approach is ideal for more complex logic, where you can describe requirements, constraints, and expected behavior in detail.

#### Why Use Multi Line Comments?
- **Expressiveness:** Describe complex requirements and logic
- **Clarity:** Provide context, edge cases, and constraints
- **Control:** Guide the AI to generate code that matches your intent

**Best Practice:** Use multi-line comments to break down the problem, specify input/output, and highlight special cases.

---

##### Example #1: Strings and Numbers Formatting
**Prompt:**

```python
# Given a list that contains some numbers and strings,
# format the list elements into a string in which the numbers are prepended with a "#"
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

##### Example #2: Filter Even Numbers
**Prompt:**

```python
# Given a list of numbers,
# return a new list containing only the even numbers.
```

Amazon Q Developer Suggestion:

```python
def filter_even(numbers):
    return [n for n in numbers if n % 2 == 0]
```

---

#### Key Takeaways
- Use multi-line comments for complex requirements and logic
- Clearly describe the problem, constraints, and expected output
- The more context you provide, the better the code suggestions

