# Supply Chain Analytics Dashboard

[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com/)
[![DAX](https://img.shields.io/badge/DAX-Data%20Analysis%20Expressions-blue?style=for-the-badge)](https://learn.microsoft.com/dax/)
[![Power Query](https://img.shields.io/badge/Power%20Query-Data%20Transformation-5C2D91?style=for-the-badge)](https://learn.microsoft.com/power-query/)
[![Data Modeling](https://img.shields.io/badge/Data%20Modeling-Star%20Schema-orange?style=for-the-badge)](https://learn.microsoft.com/power-bi/guidance/star-schema)
[![Git](https://img.shields.io/badge/Git-Version%20Control-critical?style=for-the-badge&logo=git)](https://git-scm.com/)

## Project Overview

**Supply Chain Analytics Dashboard** is an interactive Power BI analytics solution designed to analyze supply chain performance across orders, sales, products, customers, shipping, delivery, departments, and regions.

The project transforms raw supply chain data into a structured analytical model and presents the results through interactive dashboards, KPI cards, charts, slicers, and page navigation.

The dashboard is designed to provide a clear view of operational and commercial performance and help users explore the data from multiple business perspectives.

---

## Business Objective

Supply chain operations generate large amounts of order, product, customer, shipping, and delivery data. Without a centralized analytical view, it can be difficult to monitor performance and identify important patterns.

The objective of this project is to build an interactive Power BI solution that enables users to:

- Monitor order and sales performance
- Analyze product and category performance
- Understand customer contribution
- Monitor shipping and delivery performance
- Analyze late-delivery risk
- Compare department performance
- Compare regional performance
- Explore trends using interactive filters

---

## Dataset Information

The project uses a supply chain dataset containing order-level business information related to:

- Orders
- Customers
- Products
- Product categories
- Departments
- Sales
- Benefit
- Shipping
- Delivery status
- Delivery risk
- Order regions
- Shipping modes
- Customer segments

The raw dataset is stored in the repository under:



##  Data Analytics Workflow

Raw Supply Chain Data
        ↓
Data Cleaning & Transformation
        ↓
Data Modeling
        ↓
DAX Measures
        ↓
Dashboard Development
        ↓
Interactive Analysis
        ↓
Business Insights

# Data Model

The Power BI report uses a fact-and-dimension structure based on a star-schema approach.

## Fact Table
Fact_Supply_Chain_Dataset

## Dimension Tables
Dim_Product
Dim_Customers
Dim_Department
Dim_Order

The dimension tables are connected to the main fact table to support filtering, aggregation, and interactive analysis.


# Dashboard Pages
## Page 1: Home

The Home page serves as the landing page for the dashboard.

Features
Supply Chain Analytics title
Project introduction
Dashboard navigation
Navigation cards for major analysis areas
Navigation
Home
Executive Overview
Product & Sales
Shipping & Delivery
Customer / Regional Analysis
 ## Page 2: Executive Overview

Provides a high-level overview of supply chain performance.

KPIs
Total Orders
Total Sales
Total Customers
Total Benefit
Late Delivery %
Late Deliveries
Visualizations
Orders Trend by Quarter
Delivery Status
Benefit by Department
Orders by Department
Filters
Delivery Status
Department Name
Order Region
Shipping Mode
## Page 3: Product & Sales

Focuses on sales, product, and benefit performance.

KPIs
Total Sales
Total Benefit
Average Order Value
Average Benefit per Order
Total Orders
Visualizations
Sales by Product Category
Sales Trend Over Time
Top 10 Products by Sales
Benefit by Product Category
Filters
Category Name
Product Name
Department Name
Order Region
Shipping Mode
## Page 4: Shipping & Delivery

Focuses on shipping performance and delivery status.

KPIs
Total Orders
Late Deliveries
Late Delivery %
Average Shipping Days
Average Order Value
Visualizations
Delivery Status
Average Shipping Days by Shipping Mode
Late Deliveries by Department
Orders by Shipping Mode
Filters
Shipping Mode
Delivery Status
Department Name
Order Region
## Page 5: Customer & Regional Analysis

Combines customer and regional performance analysis.

KPIs
Total Customers
Average Order Value
Visualizations
Top 10 Customers by Sales
Customer Performance
Sales by Region
Orders by Region
Filters
Customer Name
Order Region
Category Name
Shipping Mode


## Key Performance Indicators
KPI	Description
Total Orders	Distinct number of orders
Total Customers	Distinct number of customers
Total Sales	Total sales generated from orders
Total Benefit	Total benefit recorded in the dataset
Average Benefit per Order	Average benefit per order
Late Deliveries	Distinct orders with late-delivery risk
Late Delivery %	Percentage of orders with late-delivery risk
Average Shipping Days	Average actual shipping duration
Average Order Value	Sales divided by total orders

# DAX Measures

### Total Orders
Total Orders =
DISTINCTCOUNT(Fact_Supply_Chain_Dataset[Order Id])


### Total Customers
Total Customers =
DISTINCTCOUNT(Fact_Supply_Chain_Dataset[Customer Id])


### Total Sales
Total Sales =
SUM(Fact_Supply_Chain_Dataset[Sales])


### Total Benefit
Total Benefit =
SUM(Fact_Supply_Chain_Dataset[Benefit per order])


### Average Benefit per Order
Average Benefit per Order =
AVERAGE(Fact_Supply_Chain_Dataset[Benefit per order])


### Late Deliveries
Late Deliveries =
CALCULATE(
    DISTINCTCOUNT(Fact_Supply_Chain_Dataset[Order Id]),
    Fact_Supply_Chain_Dataset[Late_delivery_risk] = 1
)


### Late Delivery %
Late Delivery % =
DIVIDE(
    [Late Deliveries],
    [Total Orders],
    0
)


### Average Shipping Days
Average Shipping Days =
AVERAGE(Fact_Supply_Chain_Dataset[Days for shipping (real)])


### Average Order Value
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders],
    0
)

## Interactive Features

The dashboard includes:

Interactive page navigation
KPI cards
Dropdown slicers
Cross-filtering between visuals
Top 10 analysis
Sales trend analysis
Regional analysis
Customer analysis
Product analysis
Shipping analysis
Delivery analysis


ey Business Questions
Sales Performance
What is the total sales performance?
Which product categories generate the most sales?
How does sales change over time?
Which products are among the top performers by sales?
Customer Performance
How many customers are represented in the dataset?
Which customers contribute the most sales?
Which customers have the highest order activity?
Shipping & Delivery
What is the average shipping duration?
Which shipping modes are used most frequently?
How many orders have late-delivery risk?
How does late delivery vary by department?
Regional Performance
Which regions generate the highest sales?
Which regions have the highest number of orders?

 
 #  Tools & Technologies
Power BI Desktop — Dashboard development
Power Query — Data cleaning and transformation
DAX — Analytical measures and KPIs
Data Modeling — Fact and dimension modeling
CSV — Source data
Git — Version control
GitHub — Repository and project documentation

#Repository Structure

Supply-Chain-Analytics-Dashboard/
│
├── Power_BI_Report/
│   └── Supply Chain.pbix
│
├── Raw Data/
│   └── SupplyChainDataset.csv
│
├── assets/
│   ├── icons8-benefit-58.png
│   ├── icons8-box.gif
│   ├── icons8-cash-48.png
│   ├── icons8-customers-48.png
│   ├── icons8-delivery-time.gif
│   ├── icons8-order-100 (1).png
│   ├── icons8-order-100.png
│   ├── icons8-order-64.png
│   ├── icons8-percentage-64.png
│   ├── icons8-sales-100 (1).png
│   └── icons8-sales-100.png
│
└── README.md
Dashboard Screenshots

Add screenshots of the completed Power BI pages to the assets folder when available.

##Recommended screenshots:

 ### Home
![Home Page](D:\Supply-Chain-Analytics-Dashboard\assets\home_page.png)


### Executive Overview
![Executive Overview](D:\Supply-Chain-Analytics-Dashboard\assets\executive_overview.png)

### Product & Sales
![Product & Sales](D:\Supply-Chain-Analytics-Dashboard\assets\product_sales.png)

### Shipping & Delivery
![Shipping & Delivery](D:\Supply-Chain-Analytics-Dashboard\assets\shipping_delivery.png)

### Customer & Regional Analysis
![ Customer & Regional Analysis](D:\Supply-Chain-Analytics-Dashboard\assets\customer_regional.png)

## How To Use

Clone or download this repository.
Open the Power_BI_Report folder.
Open Supply Chain.pbix using Power BI Desktop.
Use the page navigator at the top to move between dashboard pages.
Use slicers to filter the analysis.
Interact with charts to explore supply chain performance.


## Project Highlights

✔ End-to-End Supply Chain Analytics

✔ Interactive Power BI Dashboard

✔ Fact & Dimension Data Modeling

✔ DAX-Based KPI Development

✔ Sales & Product Analysis

✔ Customer & Regional Analysis

✔ Shipping & Delivery Analysis

✔ Interactive Slicers and Navigation

✔ Top 10 Performance Analysis

✔ Git & GitHub Version Control

# Skills Demonstrated

Data Cleaning
Data Transformation
Data Modeling
Star Schema Concepts
DAX
KPI Development
Business Intelligence
Data Visualization
Power BI Dashboard Design
Interactive Reporting
Git
GitHub
Future Improvements



