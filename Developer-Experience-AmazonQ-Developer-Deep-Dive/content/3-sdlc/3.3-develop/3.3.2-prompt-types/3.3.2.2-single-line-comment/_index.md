---
title: "Single Line Comment"
date: 2023-08-17T00:00:00-00:00
weight: 2
chapter: false
pre: "<b>3.3.2.2 </b>"
---

# Single Line Comment Prompts

## Overview
Single line comment prompts use inline comments to generate specific code suggestions. Amazon Q Developer analyzes the comment context and provides relevant code implementations directly following the comment.

## Use Cases
- Generate simple function implementations
- Create variable assignments
- Add conditional logic
- Implement basic algorithms

## Best Practices

### 1. Be Specific and Clear
```python
# Calculate the factorial of a number using recursion
```

### 2. Include Context
```javascript
// Validate email format using regex pattern
```

### 3. Specify Expected Behavior
```java
// Sort array in ascending order using bubble sort
```

## Example Implementation

### Python Example
```python
# Create a function to check if a number is prime
def is_prime(n):
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            return False
    return True
```

### JavaScript Example
```javascript
// Convert string to title case
function toTitleCase(str) {
    return str.replace(/\w\S*/g, (txt) => 
        txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase()
    );
}
```

## Key Benefits
- **Quick Implementation**: Fast code generation for simple tasks
- **Context Awareness**: Leverages surrounding code for better suggestions
- **Minimal Syntax**: Simple comment format requires no special syntax
- **Language Agnostic**: Works across multiple programming languages

## Tips for Effective Use
1. Position comments directly above where code should be generated
2. Use descriptive language that clearly indicates intent
3. Include parameter or return type hints when applicable
4. Keep comments concise but informative
