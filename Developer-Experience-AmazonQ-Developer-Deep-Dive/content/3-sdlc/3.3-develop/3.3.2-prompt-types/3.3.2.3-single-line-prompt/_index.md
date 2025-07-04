---
title: "Single Line Prompt"
date: 2023-08-17T00:00:00-00:00
weight: 3
chapter: false
pre: "<b>3.3.2.3 </b>"
---

Single Line Prompt
Amazon Q Developer will understand your intent and provide suggestions based on concise, directive single line prompts or comments. This is especially useful for giving clear instructions such as CREATE, RETURN, or other actions.

## Why Use Single Line Prompts?
- **Directives:** Guide the AI with explicit actions (e.g., CREATE, RETURN)
- **Efficiency:** Quickly generate code for common tasks
- **Clarity:** Clear, actionable instructions yield better results

**Best Practice:** Use imperative verbs and be specific about the function's purpose and expected output.

---

### Example #1: User Age Function
**Prompt:**

```python
# create a function called get user age
# ask the user to input their age
# return the user's age
```

Amazon Q Developer Suggestion:

```python
def get_user_age():
    age = input("Please enter your age: ")
    return age
```

---

### Example #2: Calculate Area
**Prompt:**

```python
# create a function to calculate the area of a rectangle
# return the area
```

Amazon Q Developer Suggestion:

```python
def calculate_area(length, width):
    return length * width
```

---

## Key Takeaways
- Use single line prompts with clear directives for fast, accurate code generation
- Combine multiple single line prompts for more complex logic
- Review and refine suggestions to best fit your needs