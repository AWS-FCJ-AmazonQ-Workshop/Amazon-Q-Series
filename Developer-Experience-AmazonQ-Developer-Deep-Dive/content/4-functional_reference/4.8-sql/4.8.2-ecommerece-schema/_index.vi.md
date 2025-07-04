---
title: "SQL - Schema E-Commerce"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.8.2 </b> "
---

#### SQL - Schema E-Commerce

Amazon Q Developer có thể sinh mã SQL chuẩn ANSI và các biến thể đặc thù cho từng hệ quản trị cơ sở dữ liệu. Nếu một nhà cung cấp cơ sở dữ liệu có cú pháp DDL hoặc DML riêng, Amazon Q Developer sẽ sinh mã phù hợp với cú pháp đó.

> **Lưu ý:** Luôn kiểm tra xem Amazon Q Developer có nhiều hơn một gợi ý hay không.

#### Tạo Schema E-Commerce

**Prompt:**
```sql
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
```

**Kết quả:**
```sql
CREATE DATABASE IF NOT EXISTS my-ecomm;

USE my-ecomm;

CREATE TABLE IF NOT EXISTS categories (
    categoryid INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL
);

CREATE TABLE IF NOT EXISTS products (
    productid INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(255) NOT NULL,
    description TEXT,
    price DECIMAL(10, 2) NOT NULL,
    categoryid INT NOT NULL,
    imageurl VARCHAR(255) NOT NULL,
    FOREIGN KEY (categoryid) REFERENCES categories(categoryid)
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
```

#### CRUD, Functions và Stored Procedures

**Prompt 1:**
```sql
/**
-- select all order over $50 given a customer name. Return the product list with order id, product ID, product name, product image, shipper Name and shipper tracking number

-- select all reviews given a product name. Return the customer name, review, rating

-- create a function for GetProductsByCategory

-- create a procedure for GetProductsByCategory
*/
```

**Prompt 2:**
```sql
/**
given a json object with a list of items for a customer
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
```