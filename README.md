# task-7
# Task 7 - Data Analyst Internship

## 🧠 Objective
Use Python and SQLite to extract and visualize a simple sales summary, including total quantity and revenue per product, using SQL and matplotlib.

---

## 🛠️ Tools Used
- **Python** with:
  - `sqlite3` – to interact with the SQLite database
  - `pandas` – to manipulate SQL results
  - `matplotlib` – to plot bar and pie charts
- **SQLite** – for lightweight database storage
- **Jupyter Notebook** – for interactive development

---

## 📂 Files Included
| File Name                | Description                                      |
|--------------------------|--------------------------------------------------|
| `task7_sales_summary.ipynb` | Main notebook with all SQL queries, charts, and output |
| `task7_sales_summary.py` | Python script version of the notebook            |
| `sales_data.db`          | SQLite database with a single sales table        |
| `sales_chart.png`        | Revenue bar chart by product                     |
| `README.md`              | Task explanation and Q&A                         |

---

## 📊 Task Summary
- Created a SQLite database `sales_data.db`
- Added a table `sales` with fields: `product`, `quantity`, `price`
- Inserted multiple product entries with quantities and prices
- Used SQL to:
  - Get **total quantity sold** and **revenue per product**
  - Identify **top-selling product**
  - Calculate **average price per product**
  - Display **total revenue**
- Used matplotlib to plot:
  - Bar chart of **revenue by product**
  - Pie chart of **revenue share by product**

---

## 🔎 SQL Queries Used
```sql
-- Total revenue and quantity per product
SELECT product, SUM(quantity) AS total_qty, SUM(quantity * price) AS revenue
FROM sales
GROUP BY product;

-- Total revenue
SELECT SUM(quantity * price) AS total_revenue FROM sales;

-- Top-selling product
SELECT product, SUM(quantity) AS total_quantity
FROM sales
GROUP BY product
ORDER BY total_quantity DESC
LIMIT 1;

-- Average price per product
SELECT product, AVG(price) AS avg_price
FROM sales
GROUP BY product;
