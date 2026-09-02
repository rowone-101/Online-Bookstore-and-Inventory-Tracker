-- =========================================================
-- Online Bookstore & Inventory Tracker - SQL Project
-- =========================================================

-- STEP 1: CREATE TABLE
DROP TABLE IF EXISTS bookstore_data;

CREATE TABLE bookstore_data (
    order_id         VARCHAR(10),
    order_date       DATE,
    customer_id      VARCHAR(10),
    customer_name    VARCHAR(100),
    city             VARCHAR(60),
    membership_type  VARCHAR(20),
    book_id          VARCHAR(10),
    title            VARCHAR(150),
    author           VARCHAR(100),
    genre            VARCHAR(50),
    quantity         INT,
    unit_price       DECIMAL(10,2),
    line_total       DECIMAL(10,2),
    order_total      DECIMAL(10,2),
    status           VARCHAR(20),
    payment_mode     VARCHAR(30),
    stock_quantity   INT,
    reorder_level    INT
);

-- STEP 2: LOAD DATA
-- SQLite (CLI):
--   .mode csv
--   .import --skip 1 bookstore_data.csv bookstore_data
--
-- MySQL:
--   LOAD DATA LOCAL INFILE 'bookstore_data.csv'
--   INTO TABLE bookstore_data
--   FIELDS TERMINATED BY ',' ENCLOSED BY '"'
--   LINES TERMINATED BY '\n'
--   IGNORE 1 ROWS;
--
-- PostgreSQL (psql):
--   \copy bookstore_data FROM 'bookstore_data.csv' DELIMITER ',' CSV HEADER;

-- STEP 3: QUERIES

-- 1. Total revenue and total orders
SELECT
    COUNT(DISTINCT order_id) AS total_orders,
    SUM(order_total) AS total_revenue
FROM (SELECT DISTINCT order_id, order_total, status FROM bookstore_data)
WHERE status <> 'Cancelled';

-- 2. Top 5 best-selling books by quantity sold
SELECT
    title,
    author,
    SUM(quantity) AS total_units_sold
FROM bookstore_data
WHERE status <> 'Cancelled'
GROUP BY title, author
ORDER BY total_units_sold DESC
LIMIT 5;

-- 3. Revenue by genre
SELECT
    genre,
    SUM(line_total) AS genre_revenue
FROM bookstore_data
WHERE status <> 'Cancelled'
GROUP BY genre
ORDER BY genre_revenue DESC;

-- 4. Books that need restocking (low stock)
SELECT DISTINCT
    title,
    stock_quantity,
    reorder_level
FROM bookstore_data
WHERE stock_quantity <= reorder_level;

-- 5. Top 5 customers by total spending
SELECT
    customer_name,
    SUM(order_total) AS total_spent
FROM (SELECT DISTINCT order_id, order_total, customer_name, status FROM bookstore_data)
WHERE status <> 'Cancelled'
GROUP BY customer_name
ORDER BY total_spent DESC
LIMIT 5;

-- 6. Order status breakdown
SELECT
    status,
    COUNT(*) AS order_count
FROM (SELECT DISTINCT order_id, status FROM bookstore_data)
GROUP BY status;

-- 7. Most used payment method
SELECT
    payment_mode,
    COUNT(*) AS orders_count
FROM (SELECT DISTINCT order_id, payment_mode FROM bookstore_data)
GROUP BY payment_mode
ORDER BY orders_count DESC;
