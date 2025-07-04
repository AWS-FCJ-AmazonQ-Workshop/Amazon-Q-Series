---
title: "Single Line Prompt"
date: 2023-08-17T00:00:00-00:00
weight: 3
chapter: false
pre: "<b>3.3.2.3 </b>"
---

# Single Line Prompt

## Overview
Single line prompts are concise, one-line instructions that guide Amazon Q Developer to generate specific code snippets. These prompts are ideal for quick code generation tasks and simple implementations.

## Characteristics
- **Brevity**: One line of descriptive text
- **Clarity**: Clear and unambiguous instructions
- **Specificity**: Focused on a single task or function
- **Context-Aware**: Leverages existing code context

## Common Patterns

### 1. Function Creation Prompts
```python
# Create a function to validate password strength
# Generate a method to calculate compound interest
# Write a function to merge two sorted arrays
```

### 2. Data Processing Prompts
```javascript
// Convert JSON string to object
// Filter array for positive numbers only
// Remove duplicates from list
```

### 3. Algorithm Implementation
```java
// Implement binary search algorithm
// Create quicksort function
// Generate Fibonacci sequence
```

## Best Practices

### 1. Use Action Verbs
```python
# Calculate monthly payment for loan
# Validate user input format
# Convert temperature from Celsius to Fahrenheit
```

### 2. Include Expected Input/Output
```javascript
// Parse CSV string into array of objects
// Format date to MM/DD/YYYY string
// Generate random password with 8 characters
```

### 3. Specify Implementation Details
```python
# Sort dictionary by values in descending order
# Connect to MySQL database using connection pool
# Encrypt text using AES-256 encryption
```

## Example Implementations

### Python Example
```python
# Create a function to find the longest word in a sentence
def find_longest_word(sentence):
    words = sentence.split()
    return max(words, key=len)
```

### JavaScript Example
```javascript
// Generate array of random numbers between 1 and 100
function generateRandomArray(size) {
    return Array.from({length: size}, () => Math.floor(Math.random() * 100) + 1);
}
```

### Java Example
```java
// Check if string is a palindrome
public boolean isPalindrome(String str) {
    String cleaned = str.replaceAll("[^a-zA-Z0-9]", "").toLowerCase();
    return cleaned.equals(new StringBuilder(cleaned).reverse().toString());
}
```

## Effectiveness Tips
1. **Be Specific**: Avoid vague terms like "do something"
2. **Include Context**: Mention data types, constraints, or requirements
3. **Use Standard Terminology**: Employ well-known programming concepts
4. **Position Correctly**: Place prompt where code should be generated

## Common Use Cases
- Quick utility function creation
- Data transformation tasks
- Simple algorithm implementations
- Basic validation logic
- Configuration and setup code
