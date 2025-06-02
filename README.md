# 🛒 Superstore Sales Analysis Using SQL

## 📌 Project Overview

This project provides a comprehensive analysis of the Superstore dataset using SQL. The goal is to extract actionable business insights around sales performance, customer behavior, shipping efficiency, and product profitability to support data-driven decision-making.

---

## 🔍 Objectives

- Identify key sales and profit trends
- Discover top-performing regions, segments, and product categories
- Analyze customer order behavior and shipping methods
- Provide strategic recommendations based on data insights

---

## 🗂️ Dataset

The dataset contains transactional sales data with the following key columns:

- `Order ID`, `Order Date`, `Ship Date`, `Ship Mode`
- `Customer ID`, `Customer Name`, `Segment`, `Region`, `State`, `City`
- `Category`, `Sub-Category`, `Product Name`
- `Sales`, `Quantity`, `Discount`, `Profit`

---

## 🧠 Key Insights

### 💸 1. Sales and Profit Trends

```sql
SELECT 
  YEAR(`Order Date`) AS Year, 
  ROUND(SUM(Sales), 2) AS Total_Sales,
  ROUND(SUM(Profit), 2) AS Total_Profit
FROM Orders
GROUP BY YEAR(`Order Date`)
ORDER BY Year;
```

📈 **Insight**: Sales and profit steadily increased from 2015 to 2018, with a noticeable dip in profit margin in 2017 due to higher discounting.

---

### 🌍 2. Regional Performance

```sql
SELECT 
  Region, 
  ROUND(SUM(Sales), 2) AS Sales, 
  ROUND(SUM(Profit), 2) AS Profit
FROM Orders
GROUP BY Region
ORDER BY Profit DESC;
```

🏆 **Insight**: The **West** region contributed the most to profit, while the **South** region had lower profitability due to high discount rates.

---

### 📦 3. Top Product Categories and Sub-Categories

```sql
SELECT 
  Category, 
  Sub_Category, 
  ROUND(SUM(Sales), 2) AS Sales, 
  ROUND(SUM(Profit), 2) AS Profit
FROM Orders
GROUP BY Category, Sub_Category
ORDER BY Profit DESC;
```

💼 **Insight**:
- **Chairs** and **Phones** were the most profitable sub-categories.
- **Tables** frequently resulted in losses due to excessive discounting.

---

### 🚚 4. Shipping Method Analysis

```sql
SELECT 
  Ship_Mode, 
  COUNT(*) AS Orders, 
  ROUND(AVG(DATEDIFF(`Ship Date`, `Order Date`)), 2) AS Avg_Shipping_Days
FROM Orders
GROUP BY Ship_Mode;
```

🚀 **Insight**: **Standard Class** shipping was used in over 60% of orders with a 3–4 day average delivery time. **Same Day** shipping had higher profit per order but lower usage.

---

### 👥 5. Customer Segmentation

```sql
SELECT 
  Segment, 
  COUNT(DISTINCT `Customer ID`) AS Unique_Customers,
  ROUND(SUM(Sales), 2) AS Sales,
  ROUND(SUM(Profit), 2) AS Profit
FROM Orders
GROUP BY Segment;
```

🧑‍💼 **Insight**: The **Corporate** and **Consumer** segments drove the majority of sales, but **Home Office** had the highest profit margin per customer.

---

## 📊 Visuals & Dashboards


---

## 🧰 Tools Used

- MySQL for querying
- Excel for preliminary cleaning
- Tableau / Power BI for visualization

---

## ✅ Business Recommendations

1. **Reevaluate Discounts** for Sub-Categories like Tables and Bookcases
2. **Invest More in West Region** – strong sales momentum and profitability
3. **Expand Same-Day Shipping** for high-value customers
4. **Focus Marketing** on Corporate/Home Office segments with high margins

---

## 👨‍💻 Author

**Alade Olufemi Austin**  
Associate Data Scientist | SQL | Excel | Power BI | Python  
📫 Aladefemi1998@gmail.com  
🌐 [GitHub](https://github.com/aladefemi001) • [LinkedIn](https://www.linkedin.com/in/alade-olufemi-a04795333)

---
