# 🛒 ecommerce-relational-db-design

This project simulates the backend data architecture of an Amazon-like e-commerce platform. It includes a normalized relational database schema, stored procedures for business logic, and sample queries to extract insights — all written in  PL/SQL.

> 🎯 Ideal for showcasing relational modeling, procedural SQL, and query writing skills.

---

## 🛠️ Technologies Used

![Oracle SQL](https://img.shields.io/badge/SQL-Oracle-blue?logo=oracle)
![Relational DB](https://img.shields.io/badge/Database-3NF%20Relational%20Model-green)
![PL/SQL](https://img.shields.io/badge/PL--SQL-Stored%20Procedures-lightgrey)
![Data Modeling](https://img.shields.io/badge/ERD-Normalized%20Schema-purple)

---

## ✍️ Overview

The database models a typical online marketplace with the structural business rules:
- A Seller can sell many products
- A product is sold by a single seller
- Each product belongs to a category
- A product belongs to single category.
- A category can have many products.
- Product should have category ID, Name, Price, Quantity.
- An inventory belongs to single seller.
- A seller can have a single inventory.
- A customer can place many orders.
- An order belongs to a single customer.
- Customer should have username, address, phone number and email address.
- An order can have many products.
- A product belongs to a single order.
- Order should belong to a particular shipping speed.
- A return request belongs to one and only customer.
- A customer can have zero to many return requests.
- Return request should have Person ID and Product ID.
- A customer can have zero to many customers service request.
- A customer service request belongs to one and only one customer.
- Each order should have a tracking ID.
- A product list belongs to only one order.
- A order list has many order to product pairs.

---

## 📊 Database Structure

The schema is based on **3rd Normal Form (3NF)** and includes:

- `person`: Base user table for sellers and buyers
- `seller`, `buyer`: Specialized user roles
- `products`, `prod_category`, `inventory`: Product catalog and stock management
- `orders`, `orders_list`, `shipping`: Order processing and fulfillment
- `returns`, `customer_service`: Post-order operations

This is viasually represented by the image below:
<img width="2125" height="1428" alt="ERD" src="https://github.com/user-attachments/assets/c65374ca-6702-450a-977f-295ae10fed0f" />

Stored procedures are provided for:
- Inserting entities (e.g., `ADD_PRODUCTS`, `ADD_PERSON`)
- Updating status (e.g., `update_orders`, `update_returns`)

---


## 📁 Folder Structure

ecommerce-relational-db-design/

├── schema/

│ └── create_tables.sql # All CREATE TABLE statements

├── procedures/

│ ├── insert_procedures.sql # Stored procedures to insert data

│ └── update_procedures.sql # Stored procedures to update records

├── data/

│ └── insert_values.sql # Sample data loaded using procedures

├── queries/

│ └── aspect_queries.sql # Business insight queries with context

└── README.md # You're reading it 🙂


## 💻 How to Use

1. **Load the schema**
   [Create Tables](schema/create_tables.sql)
   
3. Create stored procedures
   [Insert Procedures](procedures/insert_procedures.sql)
   [Insert Procedures](procedures/update_procedures.sql)
   
5. Insert sample data
   [Insert Values](data/insert_values.sql)
   
7. Run business queries
   [Aspect Queries](queries/aspect_queries.sql)
   
⚠️ Note: This project is designed for Oracle SQL/PL-SQL environments (e.g., Oracle SQL Developer, AWS RDS with Oracle engine).

