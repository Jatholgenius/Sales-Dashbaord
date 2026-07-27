# Sales Dashboard (Power BI)

An interactive Power BI dashboard for monitoring sales performance, profitability, order economics, and product quality across regions, product categories, and customer segments.

## Overview

This `.pbix` file is a two-page Power BI report built on a star-schema data model. It gives a single-pane view of revenue, profit, orders, and product-quality KPIs, with filters to drill into specific time periods, customer segments, product lines, and regions.

## Report Pages

### Page 1 — Sales Dashboard (main)
The primary landing page, combining top-line KPIs with trend, breakdown, and geographic visuals.

**KPI cards**
- Net Revenue (MTD) and Net Revenue (Last Month)
- Gross Profit (MTD) and Gross Profit (Last Month)
- Profit Margin % and Profit Month-over-Month %
- Average Order Value (current and last month)
- Total Orders and Orders (Last Month)
- YoY Revenue Growth % vs. YoY Target
- Overall Defect Rate vs. Defect Rate Target

**Charts**
- Daily Net Revenue trend with weekend highlighting (combo line + stacked column chart)
- Monthly Net Revenue vs. Profit trend (area chart)
- Gross Profit (MTD) by product (bar charts)
- Profit Margin % by churn risk segment (donut chart)
- Lead time by size (clustered column chart)
- Revenue and customer count by country (filled map)
- Defect rate vs. target (gauge)

**Slicers / filters**
- Payment terms
- Category and sub-category
- Supplier
- Acquisition source
- Region

## Data Model

The report is built on a star schema with the following tables:

| Table | Type | Purpose |
|---|---|---|
| `fact_sales` | Fact | Order/transaction-level sales, revenue, and profit records |
| `fact_production` | Fact | Production records used for defect rate / quality metrics |
| `dim_customer` | Dimension | Customer attributes (region, acquisition source, churn risk, etc.) |
| `dim_product` | Dimension | Product attributes (category, sub-category, supplier, size) |
| `dim_date` | Dimension | Calendar table for time intelligence (MTD, LM, YoY) |
| Calculated measures | Measure table | Houses DAX measures used across visuals |

Key measures include Net Revenue, Gross Profit, Profit Margin %, Average Order Value, YoY Revenue Growth %, and Overall Defect Rate, each with current, prior-period, and target variants to support MTD/LM/YoY comparisons.

## Theme

Fluent2 base theme with the **Accessible City Park** custom color theme applied, for improved color-contrast accessibility.

## Getting Started

1. Clone this repository.
2. Open `sales_dashboard.pbix` in Power BI Desktop.
3. Use the slicers on Page 1 to filter by category, region, supplier, payment terms, or acquisition source.
4. Switch to Page 2 for a larger geographic breakdown of revenue and customers by country.

## File

- `sales_dashboard.pbix` — the Power BI report and data model

