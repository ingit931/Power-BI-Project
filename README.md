Plant Co. Performance Analysis - Power BI Project
This repository contains the files for a Power BI project analyzing the sales performance of Plant Co. for the year 2023. The dashboard provides insights into key performance indicators (KPIs) such as gross profit, sales quantity, and profitability by customer.

📊 Dashboard Preview
📖 Project Overview
The main goal of this project is to provide a comprehensive view of Plant Co.'s sales performance. The dashboard allows users to dynamically filter and analyze data to identify trends, compare performance against previous periods, and understand customer profitability. This enables data-driven decision-making to improve sales strategies and overall business performance.

🗃️ Data Sources
The project uses the following data files:

Plant_DTS.xls - Plant_Hierarchy.csv: Contains the product hierarchy, including product types.

Plant_DTS.xls - Accounts.csv: Includes details about the different customer accounts.

Plant_DTS.xls - Plant_FACT.csv: The main fact table containing transactional sales data like quantity and sales amount.

📈 Data Model
The data model in Power BI connects these tables to allow for robust analysis. The relationships are set up as follows:

Fact_Sales: The central table with all sales transactions.

Dim_Account: A dimension table with information about each customer account.

Dim_Date: A date dimension table to enable time-based analysis (YTD, PYTD).

Dim_Product: A dimension table containing details about the products sold.

These tables are linked in a star schema, with Fact_Sales at the center, which is optimal for performance and ease of use in Power BI.

visualizations
The dashboard is composed of several interactive visualizations:

KPI Cards: At the top of the dashboard, there are key metric cards that show:

Gross Profit: Total profit from sales.

YTD (Year-to-Date) Quantity: The total quantity of products sold in the current year up to the selected date.

YTD vs PYTD (Previous Year-to-Date): A comparison of sales quantity between the current year and the previous year.

PYTD (Previous Year-to-Date) Quantity: The total quantity sold in the same period last year.

GP% (Gross Profit Percentage): The ratio of gross profit to revenue.

Country Slicer: A slicer on the left allows users to filter the entire dashboard by a specific country, focusing the analysis on a particular region.

Quantity YTD vs PYTD Month - Country - Product: This bar chart compares the Year-to-Date (YTD) sales quantity against the Previous Year-to-Date (PYTD) quantity, broken down by product, month, and country. This helps in identifying growth or decline in sales for specific products over time.

Quantity YTD & PYTD (Month): A combination chart that shows the YTD and PYTD sales quantity for each month. The bars represent the PYTD figures, while the line graph shows the YTD trend, providing a clear comparison of performance over the year.

Account Profitability by Segmentation (GP% and Quantity): This scatter plot analyzes the profitability of different customer accounts. Each dot represents a customer, plotted based on the gross profit percentage (GP%) and the quantity of products purchased. This is useful for identifying high-value customers.

💡 Key Metrics (DAX Measures)
The following DAX measures were created to power the visualizations:

Gross Profit: SUM(Fact_Sales[Gross_Profit])

YTD Quantity: TOTALYTD(SUM(Fact_Sales[Quantity]), Dim_Date[Date])

PYTD Quantity: CALCULATE(SUM(Fact_Sales[Quantity]), SAMEPERIODLASTYEAR(Dim_Date[Date]))

YTD vs PYTD: [YTD Quantity] - [PYTD Quantity]

GP%: DIVIDE([Gross Profit], SUM(Fact_Sales[Sales]))

🚀 How to Use
Download the .pbix file.

Open the file in Power BI Desktop.

Interact with the Dashboard:

Use the "Country" slicer on the left to filter the data for a specific country.

Hover over the charts to see detailed tooltips with exact figures.

Click on data points in one visual to see how it affects the others (cross-filtering).
