---
title: "SQL - Users"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 4.8.1. </b> "
---

SQL - Users
Amazon Q Developer can generate ANSI & database-specific SQL DDL and DML statements. If a database vendor has specific DDL or DML implementation, Amazon Q Developer generates the specific implementation.

> **Note:** Always check if Amazon Q Developer has more than one suggestion.

#### Create Users Table

**General Prompt:**
For a relational database, create the following tables using ANSI SQL if they do not exist:
- users

**Supported Databases:** ANSI, MySQL, Postgres, Oracle, SQL Server

Create a file in your VSCode and name it `create_table_users_ansi.sql`.

**Prompt:**
```sql
/*
For a relational database, create the following tables using ANSI SQL if they do not exist:
- users
*/
```

In the file, copy and paste the prompt, and press Enter. Amazon Q Developer will provide:

**Amazon Q Developer Suggestion #1:**
```sql
CREATE TABLE IF NOT EXISTS users (
    id INT NOT NULL AUTO_INCREMENT,
    PRIMARY KEY (id)
);
```

#### Alter Users Table

You can use Amazon Q Developer to ALTER the table for adding columns, modifying columns, adding indexes, etc.

**General Prompt:**
For the users table, ALTER the table and add the following columns:
- Add unique email constraint
- Add phone number column
- Add is_student column
- Add is_admin column
- Add is_active column
- Add an index to the phone number column
- Add an index to the name column

**Supported Databases:** ANSI, MySQL, Postgres, Oracle, SQL Server

In the file `create_table_users_ansi.sql`, copy and paste the prompt and press Enter. Amazon Q Developer will provide:

**Prompt:**
```sql
--
-- For the users table, alter the table and add the following columns:
-- Add unique email constraint
-- Add phone number column
-- Add is_student column
-- Add is_admin column
-- Add is_active column
-- Add an index to the phone number column
-- Add an index to the name column
--
```

**Amazon Q Developer Suggestion #1:**
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

#### Triggers Users Table

You can use Amazon Q Developer to ADD Triggers for the table

**General Prompt:**

Create a trigger to update the is_active column when a user is created


**Supported Databases:** ANSI, MySQL, Postgres, Oracle, SQL Server
In the file create_table_users_ansi.sql, copy and paste the prompt and press enter, Amazon Q Developer will provide::

**Prompt:**
```sql
--
-- create a trigger to update the is_active column when a user is created
--
```

**Amazon Q Developer Suggestion #1:**
```sql
CREATE TRIGGER update_is_active
AFTER
INSERT ON users 
FOR EACH ROW
    UPDATE users
    SET is_active = 1
WHERE id = NEW.id;
```

#### CRUD Statements for Users Table
You can use Amazon Q Developer to generate your CRUD Statements (Create, Update, Read, Delete) for the table.

**General Prompt:**

```sql
/*
for the users table, create an ansi query that returns the name,  and email address of all users.

for the users table, create an ansi query that returns the name,  and email address of each user based on the user id.

for the users table, create an ansi query that returns the name,  and email address of each user based on the email address.

for the users table, create an ansi query that returns the name,  and email address of each user based on the name;

select user based on name starting with three letters and the email address ending with .com, and id greater than 100.

for the users table, select users where name starts with three letters and create_at is between two dates.

for the users table, select the top 10 most recent users.

*/
```

**Supported Databases:** ANSI, MySQL, Postgres, Oracle, SQL Server

In the file create_table_users_ansi.sql, copy and paste the prompt and press enter, Amazon Q Developer will provide::

**Prompt:**
```sql
/*
for the users table, create an ansi query that returns the name,  and email address of all users.

for the users table, create an ansi query that returns the name,  and email address of each user based on the user id.

for the users table, create an ansi query that returns the name,  and email address of each user based on the email address.

for the users table, create an ansi query that returns the name,  and email address of each user based on the name;

select user based on name starting with three letters and the email address ending with .com, and id greater than 100.

for the users table, select users where name starts with three letters and create_at is between two dates.

for the users table, select the top 10 most recent users.

for the users table, select the first 10 rows.

*/
```

**Amazon Q Developer Suggestion #1:**
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


