# SQL-Bank-Customer-Database-Project
sql-bank-database-project repository.
# SQL Bank Customer Database Project

This project demonstrates practical SQL Server skills by designing and querying a simple banking database. It includes table creation, one‑to‑many relationships, sample data insertion, and multiple SELECT queries that show how customers, orders, and order details connect in a relational database.

---

## 📌 Project Overview

The goal of this project is to:

- Create a structured SQL Server database
- Understand and implement one‑to‑many relationships
- Insert realistic sample data
- Query multiple tables using joins
- Analyze customer orders and order details

This project is part of a college assignment and has been expanded into a polished GitHub portfolio project.

---

## 🧱 Database Structure

The database contains **three related tables**:

### **1. customers**
Stores basic customer information.

| Column      | Type          | Description              |
|-------------|---------------|--------------------------|
| CustomerID  | INT (PK)      | Unique customer ID       |
| FirstName   | VARCHAR(50)   | Customer first name      |
| LastName    | VARCHAR(50)   | Customer last name       |
| Email       | VARCHAR(100)  | Customer email address   |

---

### **2. orders**
Stores customer orders.

| Column     | Type        | Description                     |
|------------|-------------|---------------------------------|
| OrderID    | INT (PK)    | Unique order ID                 |
| CustomerID | INT (FK)    | Links to customers table        |
| OrderDate  | DATE        | Date the order was placed       |

---

### **3. orderDetails**
Stores detailed information about each order.

| Column         | Type            | Description                     |
|----------------|-----------------|---------------------------------|
| OrderDetailID  | INT (PK)        | Unique detail ID                |
| OrderID        | INT (FK)        | Links to orders table           |
| ProductID      | INT             | Product identifier              |
| Quantity       | INT             | Number of items ordered         |
| Price          | DECIMAL(10,2)   | Price per item                  |

---

## 🔗 Relationship Diagram (Text-Based ERD)


- One customer can have many orders  
- One order can have many order details  

This is a classic relational structure used in banking, retail, and e‑commerce systems.

---

## 🧪 SQL Queries Included

The project includes five SQL queries:

### **1. Select all customers**
```sql
SELECT * FROM customers;
SELECT * FROM orders;
SELECT * FROM orderDetails;
SELECT 
    customers.CustomerID,
    customers.FirstName,
    customers.LastName,
    orders.OrderID,
    orders.OrderDate
FROM customers
JOIN orders
    ON customers.CustomerID = orders.CustomerID
ORDER BY customers.CustomerID;

SELECT 
    customers.CustomerID,
    customers.FirstName,
    customers.LastName,
    orders.OrderID,
    orders.OrderDate,
    orderDetails.ProductID,
    orderDetails.Quantity,
    orderDetails.Price
FROM customers
JOIN orders
    ON customers.CustomerID = orders.CustomerID
JOIN orderDetails
    ON orders.OrderID = orderDetails.OrderID
ORDER BY customers.CustomerID, orders.OrderID;
sql-bank-database-project/
│
├── README.md
├── bank_customer_database.sql
│
├── part-1-relationships/
│   └── answers.md
│
├── part-2-queries/
│   ├── answers.md
│   └── screenshots/
│
└── scripts/
    └── (optional .sql files)
