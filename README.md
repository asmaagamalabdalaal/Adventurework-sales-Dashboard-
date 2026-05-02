# AdventureWorks Sales Dashboard 📊

---

## 1. Project Overview

This repository contains the implementation of an **interactive Sales Analytics Dashboard** built on the **AdventureWorks** dataset using **Microsoft Power BI**. The project demonstrates end-to-end business intelligence development — from raw CSV data ingestion and data modeling to DAX-powered KPIs and executive-level visual storytelling.

The dashboard is designed to provide a **360° view of sales performance**, enabling business stakeholders to monitor revenue trends, evaluate product profitability, analyze customer behavior, and track regional performance — all through a single, cohesive reporting interface.

---

## 2. Dashboard Preview

![AdventureWorks Sales Dashboard](https://github.com/asmaagamalabdalaal/Adventurework-sales-Dashboard-/blob/b58ef29b10ce639153c28517138a3ffca78d404f/Photos/Customer%20Detail.png)
![AdventureWorks Sales Dashboard](https://github.com/asmaagamalabdalaal/Adventurework-sales-Dashboard-/blob/8b047b1dd3f16ae92ab4d65953476d1a9dc5257b/Photos/Exec%20Dashboard.png)
![AdventureWorks Sales Dashboard](https://github.com/asmaagamalabdalaal/Adventurework-sales-Dashboard-/blob/8b047b1dd3f16ae92ab4d65953476d1a9dc5257b/Photos/Map.png)
![AdventureWorks Sales Dashboard](https://github.com/asmaagamalabdalaal/Adventurework-sales-Dashboard-/blob/8b047b1dd3f16ae92ab4d65953476d1a9dc5257b/Photos/Product%20Detail.png)


---

## 3. Key Features

| Feature | Description |
|---|---|
| **Sales KPIs** | Total Revenue, Total Orders, Total Profit, Return Rate — all at a glance |
| **Time Intelligence** | Month-over-month and year-over-year comparisons using DAX time intelligence functions |
| **Product Analysis** | Performance breakdown by category, subcategory, and individual product |
| **Customer Insights** | Customer segmentation by revenue contribution, order frequency, and geography |
| **Territory Analysis** | Regional sales heatmaps and territory-level drill-through capabilities |
| **Returns Monitoring** | Return rate tracking across products and time periods |
| **Interactive Filtering** | Cross-page slicers for date range, territory, product category, and customer segment |

---

## 4. Data Model

The data model follows a **Star Schema** design, optimized for Power BI's columnar engine and DAX calculations.

```
                        ┌─────────────────────┐
                        │  Calendar Lookup     │
                        │  (Date Dimension)    │
                        └──────────┬──────────┘
                                   │
┌──────────────────┐    ┌──────────▼──────────┐    ┌──────────────────────┐
│  Customer Lookup │    │                     │    │   Territory Lookup   │
│  (Dim_Customer)  │────►   Sales Data        │◄───│   (Dim_Territory)    │
└──────────────────┘    │   (Fact_Sales)      │    └──────────────────────┘
                        │                     │
┌──────────────────┐    └──────────┬──────────┘    ┌──────────────────────┐
│  Product Lookup  │               │               │   Returns Data       │
│  (Dim_Product)   │◄──────────────┘               │   (Fact_Returns)     │
└────────┬─────────┘                               └──────────────────────┘
         │
┌────────▼─────────┐
│  Product Subcats │
│  (Dim_Subcat)    │
└────────┬─────────┘
         │
┌────────▼─────────┐
│  Product Cats    │
│  (Dim_Category)  │
└──────────────────┘
```

### Fact Tables

- **Sales Data (2020–2022)** — Core transactional fact table containing order-level records with keys to all dimension tables, plus measures like order quantity and unit price.
- **Returns Data** — Tracks product returns linked to product and calendar dimensions for return rate analysis.

### Dimension Tables

- **Calendar Lookup** — Full date dimension with day, week, month, quarter, and year attributes enabling time intelligence.
- **Customer Lookup** — Customer demographics including name, birth date, annual income, education level, and homeowner status.
- **Product Lookup** — Product-level attributes including SKU, product name, model name, product cost, and product price.
- **Product Subcategories Lookup** — Bridges products to their subcategory grouping.
- **Product Categories Lookup** — Top-level product categorization (Bikes, Accessories, Clothing, Components).
- **Territory Lookup** — Sales territory information including region, country, and continent for geographic analysis.

---

## 5. Data Sources

All source data is provided as **CSV files** in the `AdventureWorks Raw Data/` folder. The dataset covers **3 years of transactional history (2020–2022)** and includes:

| File | Description |
|---|---|
| `AdventureWorks Sales Data 2020.csv` | Sales transactions for fiscal year 2020 |
| `AdventureWorks Sales Data 2021.csv` | Sales transactions for fiscal year 2021 |
| `AdventureWorks Sales Data 2022.csv` | Sales transactions for fiscal year 2022 |
| `AdventureWorks Customer Lookup.csv` | Customer profile and demographic data |
| `AdventureWorks Product Lookup.csv` | Product catalog with cost and price details |
| `AdventureWorks Product Categories Lookup.csv` | Product category definitions |
| `AdventureWorks Product Subcategories Lookup.csv` | Product subcategory definitions |
| `AdventureWorks Territory Lookup.csv` | Sales territory and regional mapping |
| `AdventureWorks Calendar Lookup.csv` | Date dimension for time intelligence |
| `AdventureWorks Returns Data.csv` | Product return records |

---

## 6. Tools & Technologies

| Tool | Purpose |
|---|---|
| **Microsoft Power BI Desktop** | Data modeling, DAX measures, and interactive dashboard creation |
| **Power Query (M Language)** | Data ingestion, transformation, and cleaning |
| **DAX (Data Analysis Expressions)** | KPI calculations, time intelligence, and custom measures |
| **CSV / Flat Files** | Raw data source format |



