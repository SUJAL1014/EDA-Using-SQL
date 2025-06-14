# 📊 EDA Using SQL on Star Schema Sales Data

## 📁 Dataset Overview

Performed **Exploratory Data Analysis (EDA)** using SQL on the following datasets stored in a star schema structure:

- `gold.dim_customer`
- `gold.dim_product`
- `gold.fact_sales`

These datasets represent a dimensional model typically used in data warehouses or lakehouses, where:
- `dim_customer` contains customer-related information
- `dim_product` contains product-related details
- `fact_sales` stores sales transaction facts

---

## 🧠 Knowledge & Skills Gained

### ✅ DATABASE EXPLORATION
- Understood schema structure and table relationships
- Verified data types, constraints, and foreign key mappings

### ✅ DIMENSION EXPLORATION
- Explored customer demographics and product categories
- Joined dimension tables with fact data to enrich context

### ✅ DATA EXPLORATION
- Identified nulls, duplicates, and outliers in datasets
- Profiled data distributions across various attributes

### ✅ MEASURE EXPLORATION
- Analyzed key metrics such as:
  - Total Sales
  - Quantity Sold
  - Revenue and Profit
- Used SQL aggregations and filters for deeper insights

### ✅ MAGNITUDE ANALYSIS
- Ranked customers and products by revenue contribution
- Identified high-performing and underperforming segments

---

## 🛠️ Tools & Technologies

- **SQL**: Joins, Aggregations, Window Functions, CTEs, Filtering, Grouping
- **Data Modeling**: Star Schema (Fact and Dimension Tables)
- **Environment**: SQL Workbench / DB client (or cloud data platform)

---

## 📈 Example Analyses Performed

```sql
-- Top 5 customers by total revenue
SELECT c.customer_id, c.customer_name, SUM(s.sales_amount) AS total_revenue
FROM gold.fact_sales s
JOIN gold.dim_customer c ON s.customer_id = c.customer_id
GROUP BY c.customer_id, c.customer_name
ORDER BY total_revenue DESC
LIMIT 5;
