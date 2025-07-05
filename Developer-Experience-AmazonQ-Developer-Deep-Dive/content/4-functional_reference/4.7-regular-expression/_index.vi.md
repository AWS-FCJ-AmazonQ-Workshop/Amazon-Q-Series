---
title: "Biểu thức chính quy (Regular Expression)"
date: "`r Sys.Date()`"
weight: 7
chapter: false
pre: " <b> 4.7 </b> "
---

#### Tổng quan về biểu thức chính quy

Amazon Q Developer giúp bạn tạo biểu thức chính quy (regular expressions) nhanh chóng cho nhiều mục đích khác nhau. Dưới đây là các ví dụ thực tế.

#### Xác thực địa chỉ email

**Prompt:**
```python
"""
create a function to use regular expressions to validate emails
"""
```

**Kết quả:**
```python
def validate_email(email):
    import re
    regex = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
    if re.fullmatch(regex, email):
        return True
    return False
```

#### Xác thực số điện thoại

**Prompt:**
```python
"""
create a function to use regular expressions to validate phone numbers
"""
```

**Kết quả:**
```python
def validate_phone_number(phone_number):
    import re
    regex = r'\d{3}-\d{3}-\d{4}'
    if re.fullmatch(regex, phone_number):
        return True
    return False
```

#### Xác thực số điện thoại quốc tế

**Prompt:**
```python
"""
create a function to validate international phone numbers
include +1
"""
```

**Kết quả:**
```python
def validate_international_phone_number(phone_number):
    import re
    regex = r'\+\d{1}\d{3}-\d{3}-\d{4}'
    if re.fullmatch(regex, phone_number):
        return True
    return False
```

#### Xác thực số an sinh xã hội (SSN)

**Prompt:**
```python
"""
create a function to use regular expressions to validate SSN
"""
```

**Kết quả:**
```python
def validate_social_security_number(ssn):
    import re
    regex = r'\d{3}-\d{2}-\d{4}'
    if re.fullmatch(regex, ssn):
        return True
    return False
```

#### Xác thực SSN với điều kiện phức tạp

**Prompt:**
```python
"""
Create a function to validate Social Security Numbers
    return it as a dictionary object
    SSN should be in the format of ###-##-####
    SSN should be in the format of ####-##-####
    SSN should not contain any ssn starting with 000
    SSN should not contain any ssn starting with 666
    SSN should not contain any ssn starting with 999
"""
```

**Kết quả:**
```python
def validate_social_security_number(ssn):
    import re
    regex = r'\d{3}-\d{2}-\d{4}'
    if re.fullmatch(regex, ssn):
        if ssn.startswith("000") or ssn.startswith("666") or ssn.startswith("999"):
            return False
        return True
    return False
```

#### Biểu thức chính quy tùy chỉnh

**Prompt:**
```python
"""
Create a function called validate_string using regular expressions to validate a string with the following conditions:
    - There is one letter that is capitalized
    - next a hyphen
    - and rest numbers
    example: A-123456
"""
```

**Kết quả:**
```python
def validate_string(string):
    return re.match(r"[A-Z][-][0-9]+", string)
```