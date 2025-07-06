---
title: "Function Name Prompt"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.3.2.1. </b> "
---

Function Name Prompt
Amazon Q Developer can understand your intent and provides suggestions based on the function names. The more descriptive the function name is, the better the suggestions.

#### Why Use Function Name Prompts?
A well-chosen function name acts as a powerful prompt for Amazon Q Developer. By simply typing a clear, descriptive function name, you can:
- Instantly generate relevant code logic
- Reduce the need for lengthy comments or extra context
- Accelerate prototyping and implementation

**Best Practice:** Use function names that clearly express the purpose and expected behavior of the function. Avoid vague or generic names.

---

##### Example #1: Towers of Hanoi
**Prompt:**
In this case, the prompt is the function name and there is no other information needed.

```python
def towers_of_hanoi(
```

If you start typing `def towers_of_hanoi(` in your VSCode file (e.g., `basic.py`), Amazon Q Developer will suggest a complete implementation:

```python
def towers_of_hanoi(n, source, destination, auxiliary):
    if n == 1:
        print(source, destination)
        return
    towers_of_hanoi(n - 1, source, auxiliary, destination)
    print(source, destination)
    towers_of_hanoi(n - 1, auxiliary, destination, source)
```

---

##### Example #2: Average Calculation
**Prompt:**
Again, the function name alone is enough:

```python
def get_average(numbers):
```

Amazon Q Developer will suggest:

```python
def get_average(numbers):
    mean = sum(numbers) / len(numbers)
    return mean
```

---

##### Multiple Suggestions
Sometimes, Amazon Q Developer offers multiple code suggestions. Use the arrow keys to navigate and Tab to accept the one that best fits your needs.

![alt text](/images/3-sdlc/3.3-develop/3.3.2-prompt-types/3.3.2.1-function-name-prompt/image.png?width=40pc)

---

##### Example #3: Standard Deviation
**Prompt:**

```python
def standard_deviation(numbers):
```

Amazon Q Developer may suggest:

```python
def standard_deviation(numbers):
    mean = sum(numbers) / len(numbers)
    return (sum((x - mean) ** 2 for x in numbers) / len(numbers)) ** 0.5
```

Or a more modular approach:

```python
import math
def standard_deviation(numbers):
    return math.sqrt(variance(numbers))

def variance(numbers):
    mean = sum(numbers) / len(numbers)
    return sum([(x - mean) ** 2 for x in numbers]) / len(numbers)
```

---

#### Key Takeaways
- Descriptive function names are often enough for Amazon Q Developer to generate high-quality code.
- For more complex logic, start with a clear function name and refine with comments or additional context as needed.
- Experiment with naming and review multiple suggestions to find the best fit for your use case.
