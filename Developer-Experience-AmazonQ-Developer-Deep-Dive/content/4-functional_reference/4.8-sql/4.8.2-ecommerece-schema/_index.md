---
title: "Introduction to Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

SQL - E-Commerce Schema
Amazon Q Developer can generate ANSI & database specific SQL DDL and DML statements. If a database vendor has specific DLL or DML implementation, Amazon Q Developer generates the specific implementation.

NOTE
As a general rule, always check to see if Amazon Q Developer has more than one suggestion.

Create E-Commerce Schema
General Prompt:
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
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
given the following, create e-commerce database tables for an online store:

- Tables
-- Products
--- ProductID (primary key and sequence auto increment starting with value 1)
--- Name
--- Description
--- Price
--- CategoryID (foreign key to Categories table)
--- ImageURL
-- Categories
--- CategoryID (primary key and sequence number auto increment starting with value 1)
--- Name
-- Customers
--- CustomerID (primary key and sequence number auto increment starting with value 1)
--- FirstName
--- LastName
--- Email
--- Phone
--- Address
-- Orders
--- OrderID (primary key and sequence number auto increment starting with value 1)
--- CustomerID (foreign key to Customers table)
--- OrderDate
--- ShippingAddress
--- BillingAddress
--- TotalAmount
-- OrderItems
--- OrderItemID (primary key and sequence number auto increment starting with value 1)
--- OrderID (foreign key to Orders table)
--- ProductID (foreign key to Products table)
--- Quantity
--- UnitPrice
-- Shipping
--- ShippingID (primary key and sequence number auto increment starting with value 1)
--- OrderID (foreign key to Orders table)
--- Shipper (shipping company name)
--- TrackingNumber
-- Reviews
--- ReviewID (primary key and sequence number auto increment starting with value 1)
--- CustomerID (foreign key to Customers table)

create the tables for an oracle server if the tables do not exist for a  database called my-ecomm



ANSI

MySQL

Postgres

Oracle

SQL-Server
Create a file in your VSCode and name it create_table_ecomm_ansi.sql.

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
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
/**

given the following, create e-commerce database tables for an online store:

- Tables
-- Products
--- ProductID (primary key and sequence auto increment starting with value 1)
--- Name
--- Description
--- Price
--- CategoryID (foreign key to Categories table)
--- ImageURL
-- Categories
--- CategoryID (primary key and sequence number auto increment starting with value 1)
--- Name
-- Customers
--- CustomerID (primary key and sequence number auto increment starting with value 1)
--- FirstName
--- LastName
--- Email
--- Phone
--- Address
-- Orders
--- OrderID (primary key and sequence number auto increment starting with value 1)
--- CustomerID (foreign key to Customers table)
--- OrderDate
--- ShippingAddress
--- BillingAddress
--- TotalAmount
-- OrderItems
--- OrderItemID (primary key and sequence number auto increment starting with value 1)
--- OrderID (foreign key to Orders table)
--- ProductID (foreign key to Products table)
--- Quantity
--- UnitPrice
-- Shipping
--- ShippingID (primary key and sequence number auto increment starting with value 1)
--- OrderID (foreign key to Orders table)
--- Shipper (shipping company name)
--- TrackingNumber
-- Reviews
--- ReviewID (primary key and sequence number auto increment starting with value 1)
--- CustomerID (foreign key to Customers table)

create the tables for ANSI database called my-ecomm if table does not exist

*/


In the file, copy and paste the prompt, and press enter, Amazon Q Developer will provide:

Amazon Q Developer Suggestion #1:
Create Schema
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
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
CREATE DATABASE IF NOT EXISTS my-ecomm;

USE my-ecomm;

CREATE TABLE IF NOT EXISTS products (
    productid INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    description TEXT,
    price DECIMAL(10, 2) NOT NULL,
    categoryid INT NOT NULL,
    imageurl VARCHAR(255) NOT NULL,
    FOREIGN KEY (categoryid) REFERENCES categories(categoryid)
);

CREATE TABLE IF NOT EXISTS categories (
    categoryid INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL

);

CREATE TABLE IF NOT EXISTS customers (
    customerid INT PRIMARY KEY AUTO_INCREMENT,
    firstname VARCHAR(255) NOT NULL,
    lastname VARCHAR(255) NOT NULL,
    email VARCHAR(255) NOT NULL,
    phone VARCHAR(255) NOT NULL,
    address VARCHAR(255) NOT NULL

);

CREATE TABLE IF NOT EXISTS orders (
    orderid INT PRIMARY KEY AUTO_INCREMENT,
    customerid INT NOT NULL,
    orderdate DATE NOT NULL,
    shippingaddress VARCHAR(255) NOT NULL,
    billingaddress VARCHAR(255) NOT NULL,
    totalamount DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (customerid) REFERENCES customers(customerid)
);

CREATE TABLE IF NOT EXISTS orderitems (
    orderitemid INT PRIMARY KEY AUTO_INCREMENT,
    orderid INT NOT NULL,
    productid INT NOT NULL,
    quantity INT NOT NULL,
    unitprice DECIMAL(10, 2) NOT NULL,
    FOREIGN KEY (orderid) REFERENCES orders(orderid),
    FOREIGN KEY (productid) REFERENCES products(productid)
);

CREATE TABLE IF NOT EXISTS shipping (
    shippingid INT PRIMARY KEY AUTO_INCREMENT,
    orderid INT NOT NULL,
    shipper VARCHAR(255) NOT NULL,
    trackingnumber VARCHAR(255) NOT NULL,
    FOREIGN KEY (orderid) REFERENCES orders(orderid)
);

CREATE TABLE IF NOT EXISTS reviews (
    reviewid INT PRIMARY KEY AUTO_INCREMENT,
    customerid INT NOT NULL,
    FOREIGN KEY (customerid) REFERENCES customers(customerid)
);

CRUD, Functions, and Stored Procedures
You can use Amazon Q Developer to generate your Complex CRUD Queries (Create, Update, Read, Delete), functions and stored procedures.

General Prompts:
These prompts will be used individually.
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

/**

-- select all order over $50 given a customer name. Return the product list with order id, product ID, product name, product image, shipper Name and shipper tracking number

-- select all reviews given a product name. Return the customer name, review, rating

-- create a function for GetProductsByCategory

-- create a procedure for GetProductsByCategory

*/

Use this prompt as is.
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
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38

/**
given a json object with a list of items for a  customer
json object will have the following format:

{
    customer_id: 1,
    order_date: '2022-01-01',
    shipping_address: '123 Main St',
    billing_address: '456 Main St',
    tracking_number: 'ABC123',
    shipper: 'FedEx',
    total_amount: 300,
    items: [
        {
            product_id: 1,
            quantity: 2,
            unit_price: 100
        
        },
        {
            product_id: 2,
            quantity: 1,
            unit_price: 200
        }
    ]
}

Given the above json object
And the customer exists in the customers table
Then add the order to the orders table and use the returned orderId for insert into other tables
And add a record to the ORDERITEMS table for each order item in the json
And add the shipping record to the shipping table

do not add the customer to the customer table 
call the procedure AddOrders2
*/




ANSI

MySQL

Postgres

Oracle

SQL-Server
In the file create_table_ecomm_ansi.sql, copy and paste the prompt and press enter, Amazon Q Developer will provide::

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
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50

/**

-- select all order over $50 given a customer name. Return the product list with order id, product ID, product name, product image, shipper Name and shipper tracking number

-- select all reviews given a product name. Return the customer name, review, rating

-- create a function for GetProductsByCategory

-- create a procedure for GetProductsByCategory

*/


/**
given a json object with a list of items for a  customer
json object will have the following format:

{
    customer_id: 1,
    order_date: '2022-01-01',
    shipping_address: '123 Main St',
    billing_address: '456 Main St',
    tracking_number: 'ABC123',
    shipper: 'FedEx',
    total_amount: 300,
    items: [
        {
            product_id: 1,
            quantity: 2,
            unit_price: 100
        
        },
        {
            product_id: 2,
            quantity: 1,
            unit_price: 200
        }
    ]
}

Given the above json object
And the customer exists in the customers table
Then add the order to the orders table and use the returned orderId for insert into other tables
And add a record to the ORDERITEMS table for each order item in the json
And add the shipping record to the shipping table

do not add the customer to the customer table 
call the procedure AddOrders2
*/


Amazon Q Developer Suggestion #1:
CRUD, Functions, Stored Prcedures
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
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100
101
102
103
104
105
106
107
108
109
110
111
112
113
114
115
116
117
118
119
120
121
122
123
124
125
126
127
128
129
130
131
132
133
134
135
136
137
138
139
140
141
142
143
144
145
146
147
148
149
150
151
152
153
154
155
156
157
158
159
160
161
162
163
164
165

-- select all order over $50 given a customer name. Return the product list with order id, product ID, product name, product image, shipper Name and shipper tracking number

SELECT p.productid, p.name, p.imageurl, s.shipper, s.trackingnumber
FROM products p
JOIN orders o ON o.orderid = p.productid

JOIN shipping s ON s.orderid = o.orderid
WHERE o.totalamount > 50
AND o.customerid IN (
    SELECT customerid
    FROM customers
    WHERE firstname = 'XXXX'
    AND lastname = 'XXX'
    );

-- select all reviews given a product name. Return the customer name, review, rating

SELECT c.firstname, c.lastname, r.review, r.rating
FROM customers c
JOIN reviews r ON r.customerid = c.customerid

JOIN products p ON p.productid = r.reviewid
WHERE p.name = 'XXXX';

-- create a function for GetProductsByCategory

DELIMITER $$

CREATE FUNCTION GetProductsByCategory(category_name VARCHAR(255))

RETURNS TABLE (productid INT, name VARCHAR(255), description TEXT, price DECIMAL(10, 2), categoryid INT, imageurl VARCHAR(255))

BEGIN

    RETURN (
        SELECT *
        FROM products
        WHERE categoryid IN (
            SELECT categoryid
            FROM categories
            WHERE name = category_name
            )
        );

END $$

DELIMITER ;

-- create a procedure for GetProductsByCategory

DELIMITER $$

CREATE PROCEDURE GetProductsByCategory(IN category_name VARCHAR(255))

BEGIN

    SELECT *
    FROM products
    WHERE categoryid IN (
        SELECT categoryid
        FROM categories
        WHERE name = category_name
        );

END $$

DELIMITER ;

/**
given a json object with a list of items for a  customer
json object will have the following format:

{
    customer_id: 1,
    order_date: '2022-01-01',
    shipping_address: '123 Main St',
    billing_address: '456 Main St',
    tracking_number: 'ABC123',
    shipper: 'FedEx',
    total_amount: 300,
    items: [
        {
            product_id: 1,
            quantity: 2,
            unit_price: 100

        },
        {
            product_id: 2,
            quantity: 1,
            unit_price: 200
        }
    ]
}

Given the above json object
And the customer exists in the customers table
Then add the order to the orders table and use the returned orderId for insert into other tables
And add a record to the ORDERITEMS table for each order item in the json
And add the shipping record to the shipping table

do not add the customer to the customer table
call the procedure AddOrders2
*/

DELIMITER $$

CREATE PROCEDURE AddOrders2(IN json_object JSON)

BEGIN

    DECLARE customer_id INT;
    DECLARE order_date DATE;
    DECLARE shipping_address VARCHAR(255);
    DECLARE billing_address VARCHAR(255);
    DECLARE tracking_number VARCHAR(255);
    DECLARE shipper VARCHAR(255);
    DECLARE total_amount DECIMAL(10, 2);
    DECLARE items JSON;
    
    SET customer_id = json_object->'customer_id';
    SET order_date = json_object->'order_date';
    SET shipping_address = json_object->'shipping_address';
    SET billing_address = json_object->'billing_address';
    SET tracking_number = json_object->'tracking_number';
    SET shipper = json_object->'shipper';
    SET total_amount = json_object->'total_amount';
    SET items = json_object->'items';
    
    insert into orders (customerid, orderdate, shippingaddress, billingaddress, totalamount)
    VALUES (customer_id, order_date, shipping_address, billing_address, total_amount);
    
    DECLARE order_id INT;
    SET order_id = LAST_INSERT_ID();
    
    DECLARE item_id INT;
    DECLARE item_quantity INT;
    DECLARE item_unit_price DECIMAL(10, 2);
    
    DECLARE item_cursor CURSOR FOR SELECT item_id, item_quantity, item_unit_price FROM items;
    
    OPEN item_cursor;
    
    LOOP
    
        FETCH item_cursor INTO item_id, item_quantity, item_unit_price;
        EXIT WHEN item_cursor IS NULL;
        
        insert into orderitems (orderid, productid, quantity, unitprice)
        VALUES (order_id, item_id, item_quantity, item_unit_price);
        
    END LOOP;
    
    CLOSE item_cursor;
    
    insert into shipping (orderid, shipper, trackingnumber)
    VALUES (order_id, shipper, tracking_number);

END $$

DELIMITER ;


