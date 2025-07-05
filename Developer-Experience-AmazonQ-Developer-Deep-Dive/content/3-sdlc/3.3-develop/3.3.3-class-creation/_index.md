---
title: "Class Creation with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3.3. </b> "
---

Creating classes with Amazon Q Developer is intuitive and efficient. By providing clear prompts, you can generate well-structured classes with appropriate methods and attributes. This section demonstrates various approaches to class creation using AI assistance.

#### Example 1: Creating a Folder Class

Let's start with a practical example of creating a folder management system.

##### Prompt Strategy
Use descriptive prompts that clearly define the class requirements:

```text
create a class called "Folders"
folders has name, children, and optional parent
a child cannot be added twice
```

##### Implementation Steps

**Step 1:** Create a new file `folder_class.py` in VSCode

**Step 2:** Enter the following multi-line comment prompt:

```python
"""
create a class called "Folders"
folders has name, children, and optional parent
a child cannot be added twice
"""
```

**Step 3:** Press Enter repeatedly to accept Amazon Q Developer's suggestions

##### Generated Code

Amazon Q Developer will generate a comprehensive Folder class:

```python
from typing import List

class Folder:
    def __init__(self, name: str, parent=None):
        self.name = name
        self.parent = parent
        self.children = []

    def add_child(self, child: "Folder") -> None:
        if child in self.children:
            raise ValueError("Child already exists")
        child.parent = self
        self.children.append(child)

    def remove_child(self, child: "Folder") -> None:
        if child not in self.children:
            raise ValueError("Child does not exist")
        child.parent = None
        self.children.remove(child)

    def __repr__(self) -> str:
        return self.name
```

##### Extending the Class

Continue pressing Enter to let Amazon Q Developer add more functionality:

```python
    def __eq__(self, other) -> bool:
        return self.name == other.name

    def __hash__(self) -> int:
        return hash(self.name)

    def get_path(self) -> List[str]:
        if self.parent is None:
            return [self.name]
        return [self.name] + self.parent.get_path()
```

{{% notice info %}}
**Key Insight**: Amazon Q Developer continues to enhance the class as long as you keep accepting suggestions. This iterative approach helps build comprehensive, well-designed classes.
{{% /notice %}}

#### Example 2: Creating a User Class

Let's create a more complex class with multiple attributes and methods.

##### Prompt Strategy

```text
Create a class call User
add first_name, last_name, age, email, phone, login_attempts, and password attributes
```

##### Implementation Steps

**Step 1:** Create a new file `user_class.py`

**Step 2:** Enter the prompt:

```python
"""
Create a class call User
add first_name, last_name, age, email, phone, login_attempts, and password attributes
"""
```

{{% notice warning %}}
**Important**: Ensure proper indentation and alignment when writing prompts in Python files.
{{% /notice %}}

**Step 3:** Accept the suggestions by pressing Enter

##### Generated User Class

Amazon Q Developer will create a comprehensive User class:

```python
class User:
    def __init__(self, first_name, last_name, age, email, phone, login_attempts, password): 
        self.first_name = first_name 
        self.last_name = last_name 
        self.age = age
        self.email = email 
        self.phone = phone 
        self.login_attempts = login_attempts
        self.password = password

    def describe_user(self):
        print(f"User's name is {self.first_name} {self.last_name}.")
        print(f"User's age is {self.age}.")
        print(f"User's email is {self.email}.")
        print(f"User's phone number is {self.phone}.")
        print(f"User's login attempts is {self.login_attempts}.")

    def greet_user(self):
        print(f"Hello {self.first_name} {self.last_name}!")

    def increment_login_attempts(self):
        self.login_attempts += 1
        print(f"Login attempts: {self.login_attempts}")

    def reset_login_attempts(self):
        self.login_attempts = 0
        print(f"Login attempts: {self.login_attempts}")

    def change_password(self, new_password):
        self.password = new_password
        print(f"Password updated successfully")
```

##### Continuous Enhancement

As you continue pressing Enter at the end of methods, Amazon Q Developer will:

- Add validation methods
- Implement security features
- Create utility functions
- Add error handling

##### Best practices for Class Creation

##### 1. Clear and Specific Prompts
- Define all required attributes upfront
- Specify relationships between objects
- Include business rules and constraints

##### 2. Iterative Development
- Start with basic structure
- Allow Amazon Q Developer to suggest enhancements
- Review and accept relevant additions

##### 3. Multi-Language Support
Amazon Q Developer can create similar classes in various languages:

{{< tabs >}}
{{% tab name="Python" %}}
```python
"""
Create a class called User with attributes and methods
"""
```
{{% /tab %}}

{{% tab name="JavaScript" %}}
```javascript
// Create a User class with constructor and methods
```
{{% /tab %}}

{{% tab name="TypeScript" %}}
```typescript
// Create a User interface and class with type safety
```
{{% /tab %}}

{{% tab name="Java" %}}
```java
// Create a User class with getters, setters, and methods
```
{{% /tab %}}
{{< /tabs >}}

#### Next Steps

With classes created, you can now:
- Generate unit tests for your classes
- Add integration methods
- Implement design patterns
- Create inheritance hierarchies

Continue to the next section to learn about generating comprehensive unit tests for your classes.