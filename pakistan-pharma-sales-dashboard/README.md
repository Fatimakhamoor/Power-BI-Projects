# Pakistan Pharmaceutical Sales Dashboard (2023-2026)

An interactive 2-page Power BI dashboard that analyses pharmaceutical sales across Pakistan.

> **Data note:** The dataset is AI-generated and was created for practice. The insights reflect this dataset, not real market figures.

## Dashboard Preview

### Page 1: Executive Overview
![Executive Overview](screenshots/01-executive-overview.png)

### Page 2: Product & Regional Analysis
![Product and Regional Analysis](screenshots/02-product-regional-analysis.png)

## Features
- KPI cards: Net Sales, Net Profit, Profit Margin %, Units Sold, YoY Sales Growth %
- Monthly net sales and profit margin trend
- Product performance table and units-vs-profit scatter chart
- Breakdown by therapeutic category, city and sales channel
- Slicers for Year, Province, Sales Channel and Therapeutic Category, synced across pages

## Key Insights (all years, 2023-2026)
- Total net sales of PKR 231M, with a profit margin of about 30.7%
- Diabetes is the top therapeutic category; Lantus Solostar is the best-selling product
- Karachi and Lahore together account for more than half of total sales
- Wholesale Distributor and Hospital Supply generate about 70% of revenue; Online Pharmacy is under 2%

## Tools Used
- Power BI Desktop
- DAX

## DAX Measures
See [dax-measures.md](dax-measures.md).

## Lesson Learned
My YoY growth KPI showed 33% when no year was selected, because `DATEADD` was comparing a 4-year total against a shifted 3-year range. I fixed it using `SAMEPERIODLASTYEAR` and `HASONEVALUE`, so growth only shows for a single selected year.

## How to Open
Download `Pakistan_Pharma_Sales.pbix` and open it in Power BI Desktop.
