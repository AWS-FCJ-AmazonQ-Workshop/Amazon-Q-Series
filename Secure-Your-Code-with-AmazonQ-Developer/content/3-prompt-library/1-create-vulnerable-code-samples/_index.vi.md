---
title: "Tạo Vulnerable Code Samples"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

Để thực hành với tính năng quét bảo mật của Amazon Q Developer, chúng ta sẽ tạo các file mã nguồn chứa các lỗ hổng bảo mật phổ biến. Những file này sẽ được sử dụng để kiểm tra các prompt bảo mật khác nhau trong thư viện của bạn.

#### Setup Test Environment

**1. Tạo một thư mục mới cho security testing:**

```
mkdir security-test
cd security-test
```

**2. Tạo các file code có lỗ hổng như hướng dẫn bên dưới.**

#### Create Vulnerable App

Tên file: `vulnerable_app.py`

File này chứa 3 loại vulnerability chính trong một Flask web application:

```
import sqlite3
import os
import subprocess
from flask import Flask, request, redirect

app = Flask(**name**)

# SQL Injection vulnerability
def get_user(username):
    conn = sqlite3.connect('users.db')
    query = f"SELECT * FROM users WHERE username = '{username}'"
    cursor = conn.execute(query)
    return cursor.fetchone()

# Open Redirect vulnerability
@app.route('/redirect')
def redirect_user():
    url = request.args.get('url')
    return redirect(url)

# Command Injection vulnerability
@app.route('/ping')
def ping_host():
    host = request.args.get('host')
    result = subprocess.run(f'ping -c 1 {host}', shell=True, capture_output=True)
    return result.stdout
```

Các vulnerabilities trong file này:

- **SQL Injection** - Nối chuỗi trực tiếp trong query
- **Open Redirect** - Không kiểm tra hợp lệ URL trước khi redirect
- **Command Injection** - Thực thi shell không an toàn

#### Create File Handler

Tên file: `file_handler.py`

File này minh họa các vulnerabilities liên quan đến file operations và credential management:

```
import os

# Path Traversal vulnerability
def read_file(filename):
    file_path = f"/app/uploads/{filename}"
    with open(file_path, 'r') as f:
        return f.read()

# Credential Exposure vulnerability
def connect_database():
    DB_PASSWORD = "admin123"
    connection_string = f"postgresql://user:{DB_PASSWORD}@localhost/mydb"
    print(f"Connecting to: {connection_string}")
    return connection_string
```

Các vulnerabilities trong file này:

- **Path Traversal** - Không kiểm tra/sanitize input filename
- **Credential Exposure** - Hardcoded password và credential logging

#### Create Auth Service

Tên file: `auth_service.py`

File này chứa privilege escalation và credential management vulnerabilities:

```
# Privilege Escalation vulnerability
def check_admin_access(user_id):
    if user_id:
        return True  # Missing proper role check
    return False

def delete_user(current_user, target_user_id):
    if check_admin_access(current_user.id):
        return f"User {target_user_id} deleted"
    return "Access denied"

# Hardcoded API key
API_KEY = "sk-1234567890abcdef"
```

Các vulnerabilities trong file này:

- **Privilege Escalation** - Logic kiểm soát truy cập yếu
- **Credential Exposure** - Hardcoded API key

Những file này sẽ được sử dụng trong các lab tiếp theo để test các security prompts khác nhau.
