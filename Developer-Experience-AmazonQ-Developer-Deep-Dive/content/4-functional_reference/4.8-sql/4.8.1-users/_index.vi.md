---
title: "SQL - Bảng Users"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.8.1 </b> "
---

#### SQL - Bảng Users

Amazon Q Developer có thể sinh mã SQL chuẩn ANSI và các biến thể đặc thù cho từng hệ quản trị cơ sở dữ liệu. Nếu một nhà cung cấp cơ sở dữ liệu có cú pháp DDL hoặc DML riêng, Amazon Q Developer sẽ sinh mã phù hợp với cú pháp đó.

> **Lưu ý:** Luôn kiểm tra xem Amazon Q Developer có nhiều hơn một gợi ý hay không.

#### Tạo bảng Users

**Prompt:**
```sql
/*
For a relational database, create the following tables using ansi sql if they do not exist:
- users
*/
```

**Kết quả:**
```sql
CREATE TABLE IF NOT EXISTS users (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    password VARCHAR(255) NOT NULL,
    PRIMARY KEY (id)
);
```

#### Thay đổi bảng Users (ALTER)

**Prompt:**
```sql
-- 
-- for the users table, alter the table and add the following columns:
-- add unique email constraint
-- add phone number column
-- add is_student column
-- add is_admin column
-- add is_active column
-- add an index to phone number column
-- add an index to name column
--
```

**Kết quả:**
```sql
ALTER TABLE users
ADD COLUMN phone_number VARCHAR(255) NULL,
    ADD COLUMN is_student TINYINT(1) NULL,
    ADD COLUMN is_admin TINYINT(1) NULL,
    ADD COLUMN is_active TINYINT(1) NULL;
ALTER TABLE users
ADD UNIQUE INDEX (email);
ALTER TABLE users
ADD INDEX (phone_number);
ALTER TABLE users
ADD INDEX (name);
```

#### Tạo Trigger cho bảng Users

**Prompt:**
```sql
--
-- create a trigger to update the is_active column when a user is created
--
```

**Kết quả:**
```sql
CREATE TRIGGER update_is_active
AFTER
INSERT ON users 
FOR EACH ROW
    UPDATE users
    SET is_active = 1
WHERE id = NEW.id;
```

#### Câu lệnh CRUD cho bảng Users

**Prompt:**
```sql
/*
for the users table, create an ansi query that returns the name, and email address of all users.

for the users table, create an ansi query that returns the name, and email address of each user based on the user id.

for the users table, create an ansi query that returns the name, and email address of each user based on the email address.

for the users table, create an ansi query that returns the name, and email address of each user based on the name;

select user based on name starting with three letters and the email address ending with .com, and id greater than 100.

for the users table, select users where name starts with three letters and create_at is between two dates.

for the users table, select the top 10 most recent users.

for the users table, select the first 10 rows.
*/
```

**Kết quả:**
```sql
SELECT name, email FROM users;
SELECT name, email FROM users WHERE id = 1;
SELECT name, email FROM users WHERE email = 'XXXXXXXXXXXXXX';
SELECT name, email FROM users WHERE name LIKE 'XXX';
SELECT name, email FROM users WHERE name LIKE 'XXX%' AND email LIKE '%.com' AND id > 100;
SELECT name, email FROM users WHERE name LIKE 'XXX%' AND create_at BETWEEN '2020-01-01' AND '2020-01-31';
SELECT name, email FROM users ORDER BY create_at DESC LIMIT 10;
SELECT name, email FROM users LIMIT 10;
```