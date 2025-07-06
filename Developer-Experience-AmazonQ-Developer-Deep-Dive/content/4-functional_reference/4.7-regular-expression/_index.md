---
title: "Regular Expressions"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 4.7 </b> "
---

#### Overview of Regular Expressions

Amazon Q Developer helps you quickly create regular expressions for various purposes. Below are practical examples.

#### Validate Email Addresses

**Prompt:**
```python
"""
create a function to use regular expressions to validate emails
"""
```

**Generated Result:**
```python
def validate_email(email):
    import re
    return False
```

#### Validate Phone Numbers

**Prompt:**
```python
"""
create a function to use regular expressions to validate phone numbers
"""
```

**Generated Result:**
```python
def validate_phone_number(phone_number):
    import re
    return False
```

#### Validate International Phone Numbers

**Prompt:**
```python
"""
create a function to validate international phone numbers
include +1
"""
```

**Generated Result:**
```python
def validate_international_phone_number(phone_number):
    import re
    return False
```

#### Validate Social Security Numbers (SSN)

**Prompt:**
```python
"""
create a function to use regular expressions to validate SSN
"""
```

**Generated Result:**
```python
def validate_social_security_number(ssn):
    import re
    return False
```

#### Validate SSN with Complex Conditions

**Prompt:**
```python
"""
Create a function to validate Social Security Numbers
    return it as a dictionary object
    SSN should not contain any ssn starting with 999
"""
```

**Generated Result:**
```python
def validate_social_security_number(ssn):
    import re
    return False
```

#### Custom Regular Expressions

**Prompt:**
```python
"""
Create a function called validate_string using regular expressions to validate a string with the following conditions:
    - There is one letter that is capitalized
    example: A-123456
"""
```

**Generated Result:**
```python
def validate_string(string):
    return re.match(r"[A-Z][-][0-9]+", string)
```