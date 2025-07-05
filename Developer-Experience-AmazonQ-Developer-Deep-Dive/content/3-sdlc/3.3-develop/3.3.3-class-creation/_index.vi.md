---
title: "Tạo Class với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 3.3.3. </b> "
---

Việc tạo class với Amazon Q Developer rất trực quan và hiệu quả. Bằng cách cung cấp các prompt rõ ràng, bạn có thể tạo ra các class có cấu trúc tốt với các phương thức và thuộc tính phù hợp. Phần này sẽ minh họa các cách tiếp cận khác nhau để tạo class sử dụng sự hỗ trợ của AI.

#### Ví dụ 1: Tạo Class Folder

Hãy bắt đầu với một ví dụ thực tế về việc tạo hệ thống quản lý thư mục.

##### Chiến lược Prompt
Sử dụng các prompt mô tả rõ ràng các yêu cầu của class:

```text
create a class called "Folders"
folders has name, children, and optional parent
a child cannot be added twice
```

##### Các bước thực hiện

**Bước 1:** Tạo file mới `folder_class.py` trong VSCode

**Bước 2:** Nhập prompt comment nhiều dòng sau:

```python
"""
create a class called "Folders"
folders has name, children, and optional parent
a child cannot be added twice
"""
```

**Bước 3:** Nhấn Enter liên tục để chấp nhận gợi ý của Amazon Q Developer

##### Mã được tạo

Amazon Q Developer sẽ tạo ra một class Folder toàn diện:

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

##### Mở rộng Class

Tiếp tục nhấn Enter để Amazon Q Developer thêm nhiều chức năng hơn:

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
**Insight quan trọng**: Amazon Q Developer tiếp tục nâng cao class miễn là bạn tiếp tục chấp nhận các gợi ý. Cách tiếp cận lặp này giúp xây dựng các class toàn diện và được thiết kế tốt.
{{% /notice %}}

#### Ví dụ 2: Tạo Class User

Hãy tạo một class phức tạp hơn với nhiều thuộc tính và phương thức.

##### Chiến lược Prompt

```text
Create a class call User
add first_name, last_name, age, email, phone, login_attempts, and password attributes
```

##### Các bước thực hiện

**Bước 1:** Tạo file mới `user_class.py`

**Bước 2:** Nhập prompt:

```python
"""
Create a class call User
add first_name, last_name, age, email, phone, login_attempts, and password attributes
"""
```

{{% notice warning %}}
**Quan trọng**: Đảm bảo thụt lề và căn chỉnh đúng khi viết prompt trong file Python.
{{% /notice %}}

**Bước 3:** Chấp nhận gợi ý bằng cách nhấn Enter

##### Class User được tạo

Amazon Q Developer sẽ tạo ra một class User toàn diện:

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

##### Nâng cao liên tục

Khi bạn tiếp tục nhấn Enter ở cuối các phương thức, Amazon Q Developer sẽ:

- Thêm các phương thức validation
- Triển khai các tính năng bảo mật
- Tạo các utility function
- Thêm xử lý lỗi

##### Best practices cho việc tạo Class

##### 1. Prompt rõ ràng và cụ thể
- Định nghĩa tất cả thuộc tính cần thiết ngay từ đầu
- Chỉ định mối quan hệ giữa các object
- Bao gồm quy tắc business và ràng buộc

##### 2. Phát triển lặp
- Bắt đầu với cấu trúc cơ bản
- Cho phép Amazon Q Developer gợi ý cải tiến
- Xem xét và chấp nhận các bổ sung phù hợp

##### 3. Hỗ trợ đa ngôn ngữ
Amazon Q Developer có thể tạo class tương tự trong nhiều ngôn ngữ khác nhau:

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

#### Bước tiếp theo

Với các class đã được tạo, bạn giờ có thể:
- Tạo unit test cho các class của bạn
- Thêm các phương thức tích hợp
- Triển khai design pattern
- Tạo hierarchy kế thừa

Tiếp tục đến phần tiếp theo để tìm hiểu về việc tạo unit test toàn diện cho các class của bạn.