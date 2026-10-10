# E-Commerce Order Management System Database

This database system provides a robust solution for managing e-commerce transactions, inventory, customer details, payment tracking, and shipping operations. Built using MySQL/MariaDB, it features a 7-table normalized structure, custom analytical queries, window functions, and business reporting.

---

## 📌 Project Overview

* **Database Name:** `ecommerce_db`
* **File Name:** `e-commerce order management system.sql`
* **RDBMS Engine:** MySQL / MariaDB (via XAMPP / MySQL Server)
* **Core Functionalities:** Full CRUD operations, complex joins, nested subqueries, date & string manipulations, window functions, and advanced aggregation.

---

## 🗄️ Database Structure & Schema (7 Tables)

1. **`Categories`**: Stores main product classification categories (`category_id`, `category_name`).
2. **`Products`**: Tracks items available in store, stock levels, and category linkage (`product_id`, `name`, `category_id`, `price`, `stock_quantity`, `added_date`).
3. **`Customers`**: Contains customer profiles and registration records (`customer_id`, `name`, `email`, `phone_number`, `address`, `registration_date`).
4. **`Orders`**: Tracks placed orders, total costs, status, and customer connections (`order_id`, `customer_id`, `order_date`, `total_amount`, `status`).
5. **`Order_Items`**: Junction table for order details and itemized pricing (`order_item_id`, `order_id`, `product_id`, `quantity`, `subtotal`).
6. **`Payments`**: Records order payments, payment status, and gateway modes (`payment_id`, `order_id`, `payment_date`, `payment_method`, `payment_status`).
7. **`Shipping`**: Manages shipment status, dates, and delivery tracking (`shipping_id`, `order_id`, `shipping_date`, `delivery_date`, `shipping_status`).

---

## 🔑 Key Features & SQL Concepts Demonstrated

* **Primary & Foreign Key Constraints:** Defined with `ON DELETE CASCADE` and `ON DELETE SET NULL` for relational integrity.
* **Basic CRUD Operations:** `INSERT` statements for data population, `UPDATE` for inventory adjustment, and `DELETE` with `DATE_SUB()` for cancelling aged orders.
* **Complex Joins & Aggregations:** Multi-table joins across `Orders`, `Order_Items`, `Products`, `Categories`, and `Shipping` to determine sales revenue per category.
* **Window Functions:** Customer rankings based on expenditure (`DENSE_RANK()`) and monthly cumulative running totals (`SUM() OVER ()`).
* **Subqueries:** Isolating top customers, unpurchased items, and registered user order histories.
* **CASE Expressions:** Dynamic categorization of customer loyalty levels ('Gold', 'Silver', 'Bronze') and product sales popularity.

---

## 🚀 How to Run the Script

### Prerequisites
1. **MySQL / MariaDB Server** (via XAMPP or Standalone installation).
2. **VS Code** with *Database Client / MySQL extension* or **phpMyAdmin**.

### Execution Steps
1. Start your **MySQL Server** (e.g., click **Start** for MySQL in XAMPP Control Panel).
2. Open VS Code and connect to your local database host (`127.0.0.1:3306`).
3. Open the file `e-commerce order management system.sql`.
4. Execute the script from top to bottom. It will automatically:
   * Create the `ecommerce_db` database if it does not exist.
   * Build all 7 relational tables with appropriate key constraints.
   * Insert sample records for seamless query testing.
   * Run analytical reports and summary queries.

---

## 📝 License & Maintainer
Created for educational DBMS Lab project coursework.
