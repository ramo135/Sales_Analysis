# Sales Analysis Project

## Objective

The goal of this project is to perform sales data analysis to gain insights into sales performance, customer behavior, and product trends.

## Database Schema

1. **Customers Table:**
   - `customer_id` (INT, Primary Key)
   - `customer_name` (VARCHAR(50))
   - `email` (VARCHAR(100))
   - `region_id` (INT, Foreign Key, references Regions table)

2. **Products Table:**
   - `product_id` (INT, Primary Key)
   - `product_name` (VARCHAR(100))
   - `category` (VARCHAR(50))
   - `unit_price` (DECIMAL(10, 2))

3. **Orders Table:**
   - `order_id` (INT, Primary Key)
   - `customer_id` (INT, Foreign Key, references Customers table)
   - `order_date` (DATE)
   - `order_total` (DECIMAL(10, 2))

4. **Order_Details Table:**
   - `order_detail_id` (INT, Primary Key)
   - `order_id` (INT, Foreign Key, references Orders table)
   - `product_id` (INT, Foreign Key, references Products table)
   - `quantity_ordered` (INT)

5. **Regions Table:**
   - `region_id` (INT, Primary Key)
   - `region` (VARCHAR(50))

## Steps

1. **Data Exploration:**
   - Obtain a sales dataset containing information about customers, products, orders, and sales transactions.

2. **Data Cleaning:**
   - Clean the dataset to handle missing values, remove duplicates, and format data appropriately for analysis.

3. **Data Modeling:**
   - Create a well-structured relational database schema to store the cleaned data.

4. **Data Loading:**
   - Load the cleaned data into the database tables.

5. **Data Analysis:**
   - Write SQL queries to perform data analysis and extract valuable insights from the sales data.

## SQL Examples

1. **Total Revenue by Month:**

```sql
SELECT DATE_FORMAT(order_date, '%Y-%m') AS order_month, SUM(order_total) AS total_revenue
FROM orders
GROUP BY order_month
ORDER BY order_month;


