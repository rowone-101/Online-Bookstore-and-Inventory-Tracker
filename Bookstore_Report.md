# Bookstore Analysis Report

## Overview

This report summarizes the results of running the SQL queries in
`bookstore_queries.sql` on the bookstore dataset (221 order-line records).

---

## 1. Total Revenue and Orders

- **Total orders (excluding cancelled):** 62
- **Total revenue:** ₹2,16,727.94

---

## 2. Top 5 Best-Selling Books

| Book | Author | Units Sold |
|---|---|---|
| Echo Chamber | R.K. Sharma | 22 |
| Shattered Mirrors | Sudha Murty | 13 |
| The Glass Garden | Sudha Murty | 13 |
| The Wildflower Field | Robin Sharma | 12 |
| Rivers of Gold | J.D. Rowling | 11 |

**Takeaway:** *Echo Chamber* is the clear top seller, almost double the next book.

---

## 3. Revenue by Genre (Top 5)

| Genre | Revenue |
|---|---|
| Biography | ₹39,215.49 |
| History | ₹31,095.35 |
| Self-Help | ₹27,802.97 |
| Thriller | ₹22,804.04 |
| Comics | ₹17,999.29 |

**Takeaway:** Biography and History bring in the most revenue. These genres
should be prioritized in stocking and promotions.

---

## 4. Books That Need Restocking

| Book | Stock Left | Reorder Level |
|---|---|---|
| Fault Lines | 3 | 10 |
| Moonlit Roads | 9 | 20 |
| The Quiet War | 13 | 20 |
| The Iron Gate | 24 | 25 |

**Takeaway:** These 4 books are below their reorder level and should be
restocked soon, especially *Fault Lines*, which is almost out of stock.

---

## 5. Top 5 Customers by Spending

| Customer | Total Spent |
|---|---|
| Vivaan Das | ₹17,717.74 |
| Nisha Bhatt | ₹16,277.32 |
| Harsh Bhatt | ₹15,680.61 |
| Shreya Singh | ₹15,543.19 |
| Anika Kapoor | ₹12,239.98 |

**Takeaway:** These are the store's most valuable customers and good
candidates for loyalty offers or a premium membership upgrade.

---

## 6. Order Status Breakdown

| Status | Number of Orders |
|---|---|
| Delivered | 40 |
| Cancelled | 18 |
| Shipped | 15 |
| Processing | 7 |

**Takeaway:** Cancelled orders make up about 22% of all orders, which is
fairly high. It would be worth checking why so many orders get cancelled.

---

## 7. Most Used Payment Method

| Payment Mode | Orders |
|---|---|
| Cash on Delivery | 20 |
| Net Banking | 19 |
| UPI | 15 |
| Debit Card | 13 |
| Credit Card | 13 |

**Takeaway:** Cash on Delivery is still the most common payment method,
ahead of digital options.

---

## Summary

- The store generated **₹2,16,727.94** in revenue from **62 completed orders**.
- **Biography** and **History** are the strongest genres.
- **4 books** need restocking soon.
- Cancelled orders (22%) are worth investigating further.
- Cash on Delivery is the most-used payment method, though digital payments
  together outnumber it.

