# 🌿 Plant Co. Sales & Profitability Dashboard

This Power BI report provides an interactive overview and deep analysis of sales and gross profit performance for a fictional plant company. It allows users to explore KPIs across products, time periods, and countries, with tools for both monitoring and strategic insight.

---

## 🧠 Thought Process – Data Modeling & Preparation

### 1. Understanding the Goal
The primary goal of this project was to analyze plant sales performance and profitability over time, across product types, customer accounts, and regions. I wanted to build a dashboard that could highlight trends, compare performance year-over-year, and support decision-making.

### 2. Designing the Data Model
To support clean and efficient analysis, I used a **star schema** structure:

- **Fact_Sales**: Central table containing transactional data (`Price`, `Quantity`, `COGS`, `Sales`, `Date_Time`)
- **Dim_Date**: Date dimension to enable filtering and aggregation by year, month, and day
- **Dim_Product**: Includes product details like type, family, and size
- **Dim_Account**: Contains customer and geographic information for location-based insights
- **Slicer Table**: A helper table to support dynamic chart titles and filtering
- **Measures Table**: Stores all DAX measures and dynamic labels for visual clarity

### 3. Creating Measures
Custom DAX measures were created to calculate:
- **Gross Profit** = `Sales - COGS`
- **Gross Profit % (GP%)** = `Gross Profit / Sales`
- **YTD and PYTD** values using `TOTALYTD()` and `SAMEPERIODLASTYEAR()`
- **YTD vs PYTD** difference
- Dynamic text values for chart titles based on slicer selections

### 4. Optimizing the Model
- Used **one-to-many** relationships for efficient filtering
- Removed unnecessary columns and hid non-report fields
- Kept the data model clean and scalable for future enhancements

---

## 📊 Dashboard Breakdown

The report is divided into two core views:

### 🔹 Performance Overview (Basic)
![image](https://github.com/user-attachments/assets/64ee1c7e-262e-407e-b0f9-01c84eddd065)


A high-level summary of business performance in a selected year and month:

- **KPI Cards**: Sales, Gross Profit, Gross Profit %, Quantity
- **Monthly Trend Chart**: Tracks changes in Sales, Gross Profit, and GP%
- **Daily Sales Line Chart**: Displays day-by-day sales within a month
- **Sales by Product Type**: Donut chart showing share by Indoor, Outdoor, and Landscape
- **Top Countries by Sales**: Bar chart ranking top-performing regions
- **World Map**: Geolocation of sales activity across countries

This view is designed for **quick monitoring** and time-based slicing.

---

### 🔸 Profitability Analysis (Advanced)
![image](https://github.com/user-attachments/assets/8727eeab-605a-4ddc-b8bd-dabacf581031)

This page is designed to go beyond monitoring and support **strategic business decisions** using detailed comparisons and segmentation:

- **YTD vs PYTD KPIs**: These metrics show how gross profit has changed compared to the previous year. If a country's YTD profit is significantly lower than its PYTD, it signals the need to investigate causes (e.g., pricing, volume, cost changes). On the other hand, positive growth can confirm that current strategies are working.

- **Waterfall Chart**: Breaks down the change in gross profit month-by-month, helping identify which months contributed most to gains or losses. This is useful for understanding **seasonal trends**, campaign effectiveness, or supply chain disruptions.

- **Gross Profit by Product Type**: Analyzing gross profit distribution by product type (e.g., Outdoor, Landscape) helps determine which categories drive the most margin. Businesses can then prioritize high-margin products or optimize the weaker ones.

- **Scatter Plot – Account Segmentation**: Plots customer accounts by total value (YTD) and gross profit %. This visual helps answer:
  - Who are our most valuable and profitable clients?
  - Which accounts generate revenue but deliver poor margins?
  - Where can we upsell or renegotiate contracts?
  
  Based on this, the business can **refocus efforts** on high-value, high-margin accounts and **develop targeted strategies** for lower-performing segments.

- **Bottom 10 Countries (Treemap)**: Identifies countries where gross profit has decreased the most. This allows for regional performance reviews and helps guide **localized strategy changes**, such as adjusting pricing, changing distribution, or reallocating marketing budgets.




