# Data Cleaning & Visualisation with Power BI
## Overview
This project builds a Power BI sales analytics dashboard covering data cleaning, data modeling, and a suite of analyses: YTD sales, profit and averages, sales rep ranking, time series, proportions, distributions, correlations, and geospatial insights.

### Data
* **Customers.xlsx:** Customer data (ID, name, region, email, phone).
* **Products.xlsx:** Product data (ID, name, category, unit cost, discontinued flag, supplier contact, date).
* **Sales1.xlsx** and **Sales2.xlsx:** Transactions data (sale date, product, customer, quantity, unit price, total revenue, sales rep, promo codes).
* **Suppliers.xlsx:** Supplier data (ID, name, contact, country).

## Data Prep
### 1. Data Cleaning with Power Query
Promote first row to header on some imported sheets to align column names.

Removed any duplicates using Remove Rows > Duplicates.

Arranged the columns and appended the two sales tables to consolidate transactions.

### 2. Relationships:

* Sales[Customer] → Customers[CustomerID] (Many-to-One).
* Sales[Product] → Products[ProductID] (Many-to-One).
* Product[SupplierContact] → Suppliers[SupplierContact] (Many-to-One).

## Visualisation
### 1. Quick Dashboard
* Used ```CALCULATE()``` DAX function to create measures for Key KPIs: YTD Profit, Average Monthly Sales, Average Sales per Order. 
* Dual axis line & column chart showing Sales & Profit Over Time.
* Multi-row card for quick glance of units sold, revenue and profit by product category.
* Slicers for quick filtering.

### 2. Sales Rep Performance
* Monthly ranking: used ```RANKX()``` function over Sales Rep by monthly Total Sales with conditional formatting to colour columns for top 3 reps.
* Pivot Table for tabular view of sales with performance alert using conditional formatting: adds “!” icon where monthly sales fall below a defined threshold.

### 3. Time Series Analysis
* Line chart with date hierachy enabling drill down to granular details.
* Animated impact bubble (Play Axis by month) for interactive visualisation.

### 4. Proportion Analysis
* Pie chart: Share of revenue by product category.
* Stacked bar: Observe purchasing trends across different regions.

### 5. Distribution Analysis
* Histogram of order revenue to visualise frequency distribution and long-tail behavior.
* Boxplot shows spread, median, and range of revenue for each product category and region.

### 6. Correlation Analysis
Scatterplot with trendline to inspect correlation patterns between unit price of products and the number of units sold.

### 7. Geospatial Analysis
Map visual with bubble sizing to indicate which countries' products are the best-selling.

### 8. Decomposition Tree Analysis
Power BI's decision tree engine for root cause analysis.
