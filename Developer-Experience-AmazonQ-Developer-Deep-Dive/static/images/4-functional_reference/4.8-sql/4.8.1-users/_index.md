---
title: "Introduction to Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---



SQL - Users
Amazon Q Developer can generate ANSI & database specific SQL DDL and DML statements. If a database vendor has specific DLL or DML implementation, Amazon Q Developer generates the specific implementation.

NOTE
As a general rule, always check to see if Amazon Q Developer has more than one suggestion.

Create Users Table
General Prompt:
For a relational database, create the following tables using ansi sql if they do not exist:
- users

ANSI

MySQL

Postgres

Oracle

SQL-Server
Create a file in your VSCode and name it create_table_users_ansi.sql.

Prompt:
1
2
3
4
/*
For a relational database, create the following tables using ansi sql if they do not exist:
- users
*/ 


In the file, copy and paste the prompt, and press enter, Amazon Q Developer will provide:

Amazon Q Developer Suggestion #1:
Create Table
1
2
3
4
5
6
7
CREATE TABLE IF NOT EXISTS users (
    id INT NOT NULL AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    password VARCHAR(255) NOT NULL,
    PRIMARY KEY (id)
);


ALTER Users Table
You can use Amazon Q Developer to ALTER the table for adding Columns, modifying columns, adding indexes, etc.

General Prompt:

For the users table, ALTER the table and add the following columns:
-- add unique email constraint
-- add phone number column
-- add is_student column
-- add is_admin column
-- add is_active column
-- add an index to phone number column
-- add an index to name column



ANSI

MySQL

Postgres

Oracle

SQL-Server
In the file create_table_users_ansi.sql, copy and paste the prompt and press enter, Amazon Q Developer will provide::

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
-- 
-- for the users table,alter the table and add the following columns:
-- add unique email constraint
-- add phone number column
-- add is_student column
-- add is_admin column
-- add is_active column
-- add an index to phone number column
-- add an index to name column
--


Amazon Q Developer Suggestion #1:
ALTER Table
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
11
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


Triggers Users Table
You can use Amazon Q Developer to ADD Triggers for the table

General Prompt:

Create a trigger to update the is_active column when a user is created


ANSI

MySQL

Postgres

Oracle

SQL-Server
In the file create_table_users_ansi.sql, copy and paste the prompt and press enter, Amazon Q Developer will provide::

Prompt:
1
2
3
--
-- create a trigger to update the is_active column when a user is created
--


Amazon Q Developer Suggestion #1:
Triggers for Table
1
2
3
4
5
6
7
CREATE TRIGGER update_is_active
AFTER
INSERT ON users 
FOR EACH ROW
    UPDATE users
    SET is_active = 1
WHERE id = NEW.id;


CRUD Statements for Users Table
You can use Amazon Q Developer to generate your CRUD Statements (Create, Update, Read, Delete) for the table.

General Prompt:

/*
for the users table, create an ansi query that returns the name,  and email address of all users.

for the users table, create an ansi query that returns the name,  and email address of each user based on the user id.

for the users table, create an ansi query that returns the name,  and email address of each user based on the email address.

for the users table, create an ansi query that returns the name,  and email address of each user based on the name;

select user based on name starting with three letters and the email address ending with .com, and id greater than 100.

for the users table, select users where name starts with three letters and create_at is between two dates.

for the users table, select the top 10 most recent users.

*/

ANSI

MySQL

Postgres

Oracle

SQL-Server
In the file create_table_users_ansi.sql, copy and paste the prompt and press enter, Amazon Q Developer will provide::

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
11
12
13
14
15
16
17
18
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


Amazon Q Developer Suggestion #1:
CRUD Statements for Table
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
SELECT name, email FROM users;
SELECT name, email FROM users WHERE id = 1;
SELECT name, email FROM users WHERE email = 'XXXXXXXXXXXXXX';
SELECT name, email FROM users WHERE name LIKE 'XXX';
SELECT name, email FROM users WHERE name LIKE 'XXX%' AND email LIKE '%.com' AND id > 100;
SELECT name, email FROM users WHERE name LIKE 'XXX%' AND create_at BETWEEN '2020-01-01' AND '2020-01-31';
SELECT name, email FROM users ORDER BY create_at DESC LIMIT 10;
SELECT name, email FROM users LIMIT 10;


