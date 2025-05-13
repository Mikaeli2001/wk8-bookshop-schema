# Bookshop Database Management System

## Description
This project implements a database schema for managing a bookshop. It includes tables to store information about books, authors, publishers, customers, and orders, as well as the relationships between these entities. This database is designed to track book inventory, manage customer purchases, and organize information about authors and publishers.

## Database Schema
The database consists of the following tables:

* **Publishers:** Stores information about publishing houses.
* **Authors:** Stores information about book authors.
* **Books:** Stores details of individual books, including their title, ISBN, publication year, publisher, genre, price, and stock quantity.
* **Book_Authors:** A junction table to handle the Many-to-Many relationship between books and authors.
* **Customers:** Stores information about the bookshop's customers.
* **Orders:** Stores details of customer orders, including the customer, order date, shipping information, and status.
* **Order_Items:** A junction table to handle the Many-to-Many relationship between orders and books, also storing the quantity and price at the time of order.

## Table Relationships

* A **Publisher** can publish many **Books** (One-to-Many).
* A **Book** can have multiple **Authors**, and an **Author** can write multiple **Books** (Many-to-Many, resolved by the **Book_Authors** table).
* A **Customer** can place multiple **Orders** (One-to-Many).
* An **Order** can contain multiple **Books**, and a **Book** can be part of multiple **Orders** (Many-to-Many, resolved by the **Order_Items** table).

## How to Setup/Run the Project (Import SQL)
To create the database schema, you can import the `bookshop_schema.sql` file into a MySQL database. You can use tools like MySQL Workbench or the MySQL command-line client.

**Using MySQL Workbench:**
1.  Connect to your MySQL server.
2.  Go to `File` -> `Open SQL Script...` and select the `bookshop_schema.sql` file.
3.  Click the "Execute" button (usually a lightning bolt icon) to run the script.

**Using MySQL Command-Line Client:**
1.  Open your terminal or command prompt.
2.  Log in to your MySQL server using the command: `mysql -u your_username -p`
3.  Select the database where you want to create the tables (you might need to create one first using `CREATE DATABASE bookshop_db;` and then `USE bookshop_db;`).
4.  Execute the SQL file using the command: `mysql -u your_username -p your_database_name < bookshop_schema.sql` (replace `your_username` and `your_database_name` accordingly).

## ERD
*(A visual Entity-Relationship Diagram illustrating the database schema was part of the design process.)*

## Repository Contents
* `bookshop_schema.sql`: Contains the SQL `CREATE TABLE` statements for the bookshop database schema.
* `README.md`: This file, providing an overview of the project and setup instructions.
