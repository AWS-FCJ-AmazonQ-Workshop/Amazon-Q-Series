---
title: "Introduction to Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

Regular Expressions - Email
Use Amazon Q Developer to create your regular expressions quickly for validating email addresses.

Example #1:
General Prompt:
create a function to use regular expressions to validate emails

Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In your VSCode create a file email_regEx.py and type the following code:

Prompt:
1
2
3
4
5
"""

create a function to use regular expressions to validate emails

"""

Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
Email RegEx
1
2
3
4
5
6
7
   #create a merge_sort function
def validate_email(email):
    import re
    regex = r'\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Z|a-z]{2,}\b'
    if re.fullmatch(regex, email):
        return True
    return False

Regular Expressions - Phone Number
Use Amazon Q Developer to create your regular expressions quickly for validating Phone Numbers.

Example #1:
General Prompt:
create a function to use regular expressions to validate phone numbers

Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In your VSCode create a file phone_regEx.py and type the following code:

Prompt:
1
2
3
4
5
"""

 create a function to use regular expressions to validate phone numbers

"""

Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
Phone RegEx
1
2
3
4
5
6
def validate_phone_number(phone_number):
    import re
    regex = r'\d{3}-\d{3}-\d{4}'
    if re.fullmatch(regex, phone_number):
        return True
    return False


Example #2:
Prompt with International Phone Number
General Prompt:
create a function to validate international phone numbers
include +1

Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In the same file type the following comment:

Prompt:
1
2
3
4
5
"""
create a function to validate international phone numbers
include +1

"""

Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
Phone RegEx
1
2
3
4
5
6
7

def validate_international_phone_number(phone_number):
    import re
    regex = r'\+\d{1}\d{3}-\d{3}-\d{4}'
    if re.fullmatch(regex, phone_number):
        return True
    return False



Regular Expressions - SSN
Use Amazon Q Developer to create your regular expressions quickly for validating Social Security Numbers.

Example #1:
General Prompt
create a function to use regular expressions to validate SSN

Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In your VSCode create a file ssn_regEx.py and type the following code:

Prompt:
1
2
3
4
"""
create a function to use regular expressions to validate SSN

"""

Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
SSN RegEx
1
2
3
4
5
6
def validate_social_security_number(ssn):
    import re
    regex = r'\d{3}-\d{2}-\d{4}'
    if re.fullmatch(regex, ssn):
        return True
    return False


Example #2:
Prompt multi line prompt with pattern match
General Prompt
Create a function to validate Social Security Numbers
    return it as a dictionary object
    SSN should be in the format of ###-##-####
    SSN should be in the format of ####-##-####
    SSN should not contain any ssn starting with 000
    SSN should not contain any ssn starting with 666
    SSN should not contain any ssn starting with 999

Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In the same file type the following comment:

Prompt:
1
2
3
4
5
6
7
8
9
10
"""
Create a function to validate Social Security Numbers
    return it as a dictionary object
    SSN should be in the format of ###-##-####
    SSN should be in the format of ####-##-####
    SSN should not contain any ssn starting with 000
    SSN should not contain any ssn starting with 666
    SSN should not contain any ssn starting with 999

"""

Keep hitting the enter key to accept the suggestions. Amazon Q Developer will create the following code for you:

Amazon Q Developer Suggestion:
SSN RegEx
1
2
3
4
5
6
7
8
9

def validate_social_security_number(ssn):
    import re
    regex = r'\d{3}-\d{2}-\d{4}'
    if re.fullmatch(regex, ssn):
        if ssn.startswith("000") or ssn.startswith("666") or ssn.startswith("999"):
            return False
        return True
    return False

Regular Expressions - Custom Expression 01
Use Amazon Q Developer to create your custom regular expressions.

Example #1:
General Prompt:
Create a function called validate_string using regular expressions to validate a string with the following conditions:
    - There is one letter that is capitalized
    - next a hyphen
    - and rest numbers
    example: A-123456


Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In your VSCode create a file custom01_regEx.py and type the following code:

Prompt:
1
2
3
4
5
6
7
"""
Create a function called validate_string using regular expressions to validate a string with the following conditions:
    - There is one letter that is capitalized
    - next a hyphen
    - and rest numbers
    example: A-123456
"""

Amazon Q Developer Suggestion:
Custom 01 RegEx
1
2
3
def validate_string(string):
    return re.match(r"[A-Z][-][0-9]+", string)