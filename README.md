# 📊 Sales Performance Dashboard — Power BI

An end-to-end business intelligence project built on a real normalised PostgreSQL database, analysed and visualised using Power BI with a live database connection.

---

## 📌 Project Overview

This dashboard analyses the complete sales data of a toy manufacturing company covering **June 2003 to May 2005**. It provides business stakeholders with an interactive, multi-page report to explore revenue performance, product trends, and customer behaviour.

---

## 🗄️ Database Schema (PostgreSQL)

The project uses a normalised relational database with 5 tables:

| Table | Description |
|---|---|
| `customers` | Customer records including name, country, territory and contact details |
| `orders` | All completed orders with dates, status and deal size |
| `order_items` | Line items for each order including quantity, price and sales amount |
| `products` | Product catalogue with product line, product code and MSRP |
| `sales_raw` | Staging table used during data preparation |

**Relationships:**
- `customers` → `orders` (one customer, many orders)
- `orders` → `order_items` (one order, many line items)
- `order_items` → `products` (many items reference one product)

---

## 🔧 Tools & Technologies

- **PostgreSQL** — database design, normalisation and storage
- **Power BI Desktop** — data modelling, DAX measures, report building
- **DAX** — calculated measures for KPIs
- **Power BI Service** — publishing and sharing

---

## 📐 DAX Measures

```dax
Total Revenue = SUM('public order_items'[sales])

Total Orders = DISTINCTCOUNT('public orders'[order_id])

Total Quantity = SUM('public order_items'[quantity])

Avg Order Value = DIVIDE([Total Revenue], [Total Orders])
```

---

## 📊 Dashboard Pages

### Page 1 — Overview
- 4 KPI cards: Total Revenue, Total Orders, Total Quantity, Avg Order Value
- Revenue Trend line chart (2003–2005)
- Revenue by Country bar chart
- Year slicer for interactive filtering

### Page 2 — Product Analysis
- Revenue by Product Line
- Top 10 Products by Revenue

### Page 3 — Customer Analysis
- Revenue by region
- Top 10 Customers by Revenue

---

## 💡 Key Business Insights

- 💰 **Total Revenue: $10.03M** across 307 orders over 3 years
- 📦 **Classic Cars** is the highest revenue-generating product line, significantly ahead of all others
- 🌍 **USA** is the top revenue-generating country by a wide margin
- 🏆 **Euro Shopping Channel** is the single highest-value customer with nearly $1M in revenue
- 📉 Revenue shows a **declining trend from 2004 to 2005**, which could indicate market saturation or seasonal effects worth investigating
- 💵 **Average Order Value of $32.68K** indicates a B2B sales model with high-value bulk orders

---

## 📸 Dashboard Preview

### Overview
![Overview](https://raw.githubusercontent.com/Siddhi2k04/sales-dashboard-powerBI/main/Overview.png)

### Product Analysis
![Products](https://raw.githubusercontent.com/Siddhi2k04/sales-dashboard-powerBI/main/Products.png)

### Customer Analysis
![Customers](https://raw.githubusercontent.com/Siddhi2k04/sales-dashboard-powerBI/main/Customers.png)

---

## 🚀 How to Run Locally

1. Clone this repository
2. Set up PostgreSQL and restore the database
3. Open `sales_dashboard.pbix` in Power BI Desktop
4. Update the data source credentials to point to your local PostgreSQL instance
5. Click Refresh

---

## 🔗 Live Dashboard

👉 https://app.powerbi.com/groups/me/reports/cbf7da6a-8e1d-48f8-b15c-9c37eed6e4d4/ba9a2a613ce559fabdd1?experience=power-bi


## 👩‍💻 Author

**Siddhi Bhalekar**  
Aspiring Data Analyst | SQL · Power BI · PostgreSQL

[![GitHub](https://img.shields.io/badge/GitHub-Siddhi2k04-pink?style=flat&logo=github)](https://github.com/Siddhi2k04)
