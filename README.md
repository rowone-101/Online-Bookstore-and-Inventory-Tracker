# Online Bookstore & Inventory Tracker (SQL Project)

A simple SQL project on an online bookstore. It tracks book orders, customers,
and stock levels, and uses SQL to answer common business questions.

## Files

- `bookstore_data.csv` — the dataset (221 rows, one row per book ordered)
- `bookstore_queries.sql` — table creation + all SQL queries in one file
- `README.md` — this file

## About the Data

Each row in `bookstore_data.csv` represents one book within one order.

| Column | Description |
|---|---|
| order_id | Unique order number |
| order_date | Date the order was placed |
| customer_id | Unique customer number |
| customer_name | Customer's name |
| city | Customer's city |
| membership_type | Regular or Premium |
| book_id | Unique book number |
| title | Book title |
| author | Book author |
| genre | Book genre |
| quantity | Number of copies ordered |
| unit_price | Price per copy |
| line_total | quantity × unit_price |
| order_total | Total value of the whole order |
| status | Delivered / Shipped / Processing / Cancelled |
| payment_mode | UPI / Credit Card / Debit Card / Net Banking / COD |
| stock_quantity | Current stock left for that book |
| reorder_level | Stock level at which the book should be reordered |

## How to Use

1. Open `bookstore_queries.sql` in any SQL tool (MySQL, PostgreSQL, or SQLite).
2. Run the `CREATE TABLE` statement at the top of the file.
3. Load `bookstore_data.csv` into the table (instructions are in the SQL file).
4. Run any of the queries below the `-- ANALYSIS QUERIES` section.

## What the Queries Answer

1. Total revenue and total orders
2. Top 5 best-selling books
3. Revenue by genre
4. Books that need restocking (low stock)
5. Top 5 customers by total spending
6. Order status breakdown (delivered, cancelled, etc.)
7. Most used payment method

## Tools Used

SQL only — GROUP BY, ORDER BY, subqueries.

## Note

This is a practice dataset created for learning and portfolio purposes. It is
not real business data.
