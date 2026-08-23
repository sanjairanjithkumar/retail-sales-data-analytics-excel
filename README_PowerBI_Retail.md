# Retail Store Multi-Year Sales & Profitability — Power BI Dashboard

Interactive Power BI dashboard analyzing multi-year retail sales data, modeled as a star schema with two report pages covering sales performance and time-based trends.

---

## 📌 Overview

This Power BI report (`Retail_Sales_Multi_year.pbix`) loads the retail sales dataset and models it into a relational star schema, then presents it through two interactive report pages — an overview of sales, profit, and regional/category performance, and a dedicated time-series view for tracking trends across years, quarters, and months.

## 🗂️ Data Model (Star Schema)

| Table | Type | Key Fields |
|---|---|---|
| **Fact Sales** | Fact | Sales, Profit, CostPrice, UnitPrice, Quantity, DiscountPct, ReturnFlag + keys to each dimension |
| **Dim_Customer** | Dimension | CustomerID, CustomerName, City, Region |
| **Dim_Product** | Dimension | ProductID, ProductName, Category, Brand |
| **Dim_Store** | Dimension | StoreID, StoreName, Channel |
| **Dim Calender** | Dimension (Date table) | Date, Year, Quarter, Month — marked as the model's official Date table for time intelligence |

## 🛠️ Tools & Tech Stack

- **Power BI Desktop** — data import, modeling, DAX measures, report design
- **Power Query Editor** — cleaning and shaping the raw data, splitting it into fact/dimension tables
- **Data Model / Relationships View** — one-to-many relationships from each dimension to Fact Sales
- **DAX** — measures for totals, YTD/QTD/MTD, previous-year comparisons, and filtered KPIs

## 📊 Report Pages

### Overview
- KPI cards: total sales, orders, customers, products, profit, and stores
- Slicers: Store, Brand, Region, Channel, City
- Sales by Region (column chart), Profit by Brand (pie chart), Top 10 Products (bar chart), Sales by Brand (treemap), Sales vs Profit by City (table)

### Time Series Analysis
- KPI cards plus slicers for Month, Brand, Region, Year, City
- Previous Year vs Current Year Sales (line chart) using prior-year DAX measures
- Sales by Quarter across Channel, Sales by Month, and Sales by Month across Region (line charts), driven by the Dim Calender date hierarchy

## 💡 Key DAX Measures

Total Sales, Total Profit, Total Cost Price, Total YTD/QTD/MTD Sales and Profit, Previous Year Sales, Average Sales, Max/Min Sales, plus filtered measures for specific slices (e.g. Online-channel average sales, South-region orders, brand-specific sales).

## 👤 Author

Sanjai — Data Analytics student (Python with Data Analytics, QSpiders, Bengaluru)
