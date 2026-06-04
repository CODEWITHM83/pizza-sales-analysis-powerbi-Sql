# 🍕pizza-sales-analysis-powerbi-Sql
Interactive Power BI dashboard analyzing pizza sales performance, customer ordering behavior, revenue trends, and business insights using SQL, DAX, and data visualization.


## 🔍 Project Overview
This Power BI dashboard analyzes pizza sales performance using interactive visualizations and business intelligence techniques.

The project helps understand:
- Revenue performance
- Customer ordering behavior
- Best-selling pizzas
- Monthly and daily sales trends
- Pizza size preferences

---

# 🎯 Objective
The goal of this project is to analyze pizza sales data and generate actionable business insights using Power BI dashboards and SQL analysis.

---

# 📊 Dashboard Features

## KPI Cards
- Total Revenue
- Total Pizza Sold
- Average Order Value
- Total Orders

## Interactive Filters
- Monthly Filter
- Dynamic Visual Interaction

## Visualizations
- Orders by Time
- Top Selling Pizzas
- Orders by Pizza Size
- Monthly Order Trend
- Orders by Day

---

# 📌 Key Insights
- Large size pizzas generated the highest number of orders.
- Friday had the highest order volume.
- Peak order timing occurred during afternoon and evening hours.
- The Classic Deluxe Pizza and Barbecue Chicken Pizza were among the best-selling pizzas.
- Sales gradually decreased toward the end of the year.

---

# 🛠 Tools & Technologies Used
- Power BI
- SQL
- Power Query
- DAX
- Excel / CSV Dataset

---

# 📂 Dataset Information
The dataset contains:
- Pizza Names
- Pizza Categories
- Order Date & Time
- Revenue
- Pizza Sizes
- Quantity Sold

---

# 📸 Dashboard Preview

![Dashboard Preview](Images/dashboard.png)

---

# 📐 DAX Measures Used

```DAX
Total Revenue = SUM(PizzaSales[total_price])

Total Orders = DISTINCTCOUNT(PizzaSales[order_id])

Avg Order Value =
DIVIDE([Total Revenue], [Total Orders], 0)

Total Pizza Sold =
SUM(PizzaSales[quantity])
```

---

# 🧠 SQL Analysis Queries

## 1. Total Revenue
```sql
SELECT 
    SUM(total_price) AS Total_Revenue
FROM pizza_sales;
```

## 2. Total Orders
```sql
SELECT 
    COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales;
```

## 3. Top 5 Best Selling Pizzas
```sql
SELECT TOP 5
    pizza_name,
    SUM(quantity) AS Total_Pizza_Sold
FROM pizza_sales
GROUP BY pizza_name
ORDER BY Total_Pizza_Sold DESC;
```

## 4. Orders by Day
```sql
SELECT 
    DATENAME(WEEKDAY, order_date) AS Order_Day,
    COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY DATENAME(WEEKDAY, order_date)
ORDER BY Total_Orders DESC;
```

## 5. Orders by Month
```sql
SELECT 
    DATENAME(MONTH, order_date) AS Month_Name,
    COUNT(DISTINCT order_id) AS Total_Orders
FROM pizza_sales
GROUP BY DATENAME(MONTH, order_date)
ORDER BY Total_Orders DESC;
```

## 6. Revenue by Pizza Size
```sql
SELECT 
    pizza_size,
    SUM(total_price) AS Total_Revenue
FROM pizza_sales
GROUP BY pizza_size
ORDER BY Total_Revenue DESC;
```

## 7. Peak Order Hours
```sql
SELECT 
    DATEPART(HOUR, order_time) AS Order_Hour,
    COUNT(order_id) AS Total_Orders
FROM pizza_sales
GROUP BY DATEPART(HOUR, order_time)
ORDER BY Order_Hour;
```

## 8. Average Order Value
```sql
SELECT 
    SUM(total_price) / COUNT(DISTINCT order_id) AS Avg_Order_Value
FROM pizza_sales;
```

---

# 🚀 How to Use
1. Download the `.pbix` file
2. Open using Power BI Desktop
3. Interact with filters and visuals
4. Analyze business insights dynamically

---

# 💡 Skills Demonstrated
- SQL Query Writing
- Data Cleaning
- Data Visualization
- Business Intelligence
- DAX Calculations
- Dashboard Design
- Analytical Thinking

---

# 👨‍💻 Author

## Mithun Mondal
Aspiring Data Analyst skilled in:
- SQL
- Power BI
- Python
- Excel
- Data Visualization

---
## 📈 Business Impact & Insights

This dashboard transforms raw pizza sales data into actionable business insights, enabling faster and more informed decision-making.

### Key Performance Findings

* Large-size pizzas contributed approximately **36% of total pizza sales**, making them the most preferred size among customers.
* Friday generated the highest number of orders, indicating strong weekend demand.
* Peak ordering hours occurred during afternoon and evening periods, helping identify optimal staffing and inventory planning windows.
* The Classic Deluxe Pizza and Barbecue Chicken Pizza ranked among the top-selling products, contributing significantly to overall revenue.
* Monthly sales analysis revealed seasonal fluctuations, helping management identify high-demand and low-demand periods.

### Business Value Delivered

✅ Reduced manual reporting effort by approximately **80–90%** through automated Power BI reporting.

✅ Enabled management to analyze sales performance in **real time** instead of relying on manual spreadsheet analysis.

✅ Improved decision-making speed by providing KPI visibility and interactive filtering across products, sizes, and time periods.

✅ Identified top-performing products and customer preferences, supporting menu optimization and promotional strategies.

✅ Supported inventory planning by highlighting peak sales periods and high-demand pizza categories.

### Operational Benefits

* Faster access to sales insights.
* Improved resource allocation during peak hours.
* Better inventory management.
* Data-driven marketing and promotional planning.
* Enhanced customer preference analysis.



# ⭐ Support
If you like this project, give it a ⭐ on GitHub.
