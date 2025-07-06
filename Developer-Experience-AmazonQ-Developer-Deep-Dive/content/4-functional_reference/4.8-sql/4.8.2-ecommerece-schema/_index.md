---
title: "SQL - E-Commerce Schema"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: " <b> 4.8.2 </b> "
---

#### SQL - E-Commerce Schema

Amazon Q Developer can generate ANSI & database-specific SQL DDL and DML statements. If a database vendor has specific DDL or DML implementation, Amazon Q Developer generates the specific implementation.

> **Note:** Always check if Amazon Q Developer has more than one suggestion.

#### Create E-Commerce Schema

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

**Generated Result:**
```sql
-- SQL code for creating the e-commerce schema will be generated here.
```


