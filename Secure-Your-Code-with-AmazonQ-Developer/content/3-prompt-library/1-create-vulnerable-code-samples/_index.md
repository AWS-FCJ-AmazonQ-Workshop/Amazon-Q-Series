---
title: "Create Vulnerable Code Samples"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.1 </b> "
---

To practice with Amazon Q Developer security scanning, we'll create code files containing common security vulnerabilities. These files will be used to test various security prompts in our library.

#### Setup Test Environment

1. Create a new directory for security testing:

```
mkdir security-test
cd security-test
```

2. Create the vulnerable code files as instructed below.

#### Create Vulnerable App

File name: `vulnerable_app.py`

This file contains 3 main vulnerability types in a Flask web application:

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

Vulnerabilities in this file:

- SQL Injection - String concatenation in query
- Open Redirect - No URL validation before redirect
- Command Injection - Unsafe shell execution

#### Create File Handler

File name: `file_handler.py`

This file demonstrates vulnerabilities related to file operations and credential management:

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

Vulnerabilities in this file:

- Path Traversal - No filename input sanitization
- Credential Exposure - Hardcoded password and credential logging

#### Create Auth Service

File name: `auth_service.py`

This file contains privilege escalation and credential management vulnerabilities:

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

Vulnerabilities in this file:

- Privilege Escalation - Weak access control logic
- Credential Exposure - Hardcoded API key

These files will be used in subsequent labs to test different security prompts.
