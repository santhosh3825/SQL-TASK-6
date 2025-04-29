# SQL-TASK-6
TASK6

---

## 📘 Version 2: ✅ **Detailed README.md**

```markdown
# 📊 Task 6: Sales Trend Analysis Using SQL Aggregations

## 🧾 Objective
Analyze **monthly revenue** and **order volume** from the `orders` table in the `online_sales` database using SQL aggregation functions.

---

## 🧰 Tools Supported
- ✅ MySQL  
- ✅ PostgreSQL  
- ✅ SQLite (with minor syntax tweaks)

---

## 📂 Dataset Description

| Column Name  | Data Type | Description               |
|--------------|------------|---------------------------|
| order_id     | INT        | Unique ID per order       |
| order_date   | DATE       | Date of the order         |
| amount       | DECIMAL    | Total amount of the order |
| product_id   | INT        | Product involved in order |

---

## 🧠 Hints Implemented

- `a.` Used `EXTRACT(MONTH FROM order_date)` for month extraction
- `b.` Grouped data by both year and month
- `c.` Summed `amount` to calculate monthly revenue
- `d.` Counted distinct `order_id`s for order volume
- `e.` Sorted results using `ORDER BY`
- `f.` Filtered for Jan–Apr 2024 using `WHERE`

---

## 💡 SQL Query Used

```sql
SELECT
    EXTRACT(YEAR FROM order_date) AS year,
    EXTRACT(MONTH FROM order_date) AS month,
    SUM(amount) AS total_revenue,
    COUNT(DISTINCT order_id) AS order_volume
FROM
    orders
WHERE
    order_date BETWEEN '2024-01-01' AND '2024-04-30'
GROUP BY
    year, month
ORDER BY
    year, month;
