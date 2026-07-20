# Adidas US Sales Analysis (2020-2021) — Excel & Power Pivot

**Data Cleaning, Modeling, Dashboard Design & Business Insights**

Tools: Microsoft Excel (Power Query, Pivot Tables, Formulas, Dashboard Design)

## Overview

This project analyzes a full year of Adidas' US retail sales transactions to uncover performance patterns across regions, products, sales channels, and time periods. Starting from raw retailer-level transaction data, I cleaned and structured the data, built a proper date dimension, summarized it through pivot tables, and presented it as an interactive one-page executive dashboard.

**Headline results:** $120M in total revenue from 2.5M units sold, 42% average operating margin, $47.2M in operating profit — a 9.4% revenue increase and 9.5% profit increase vs. the prior period.

**Business question:** Where are we winning? What is driving margin? Which channels, products, regions, and time periods deserve more investment?

## Dataset

Transaction-level records with: Retailer, Retailer ID, Invoice Date, Region, State, City, Product, Price per Unit, Units Sold, Total Sales, Operating Profit, Operating Margin, and Sales Method (In-store, Online, Outlet).

## Workbook Structure

| Tab | Purpose |
|---|---|
| Data | Raw, unmodified source transactions |
| Cleaned Data | Standardized and de-duplicated dataset used for analysis |
| Date | A dedicated date dimension table with derived time attributes |
| Pivot table | Summary tables driving each dashboard visual |
| Analysis | Supporting breakdowns (week type, price band, sales method, etc.) |
| Dashboard | The final one-page executive report |

## Process — Step by Step

**1. Import & audit the raw data**
Imported the raw retailer sales export into the Data tab and reviewed column headers and data types (dates, currency, percentages, text).

**2. Clean without touching the source**
Checked each field for blanks, duplicate transaction rows, and inconsistent text entries (e.g. inconsistent spelling of city/state names or product categories). Corrected these in a separate Cleaned Data tab so the original source remained untouched.

**3. Fix data types**
Converted the Invoice Date column to a proper Excel date format and confirmed Price per Unit, Units Sold, Total Sales, and Operating Profit were numeric rather than text, so they would aggregate correctly in pivot tables.

**4. Validate calculated fields — and catch a data entry error**
Spot-checked Total Sales (Price × Units Sold) and Operating Margin (Operating Profit ÷ Total Sales) against the raw figures. This surfaced a data entry error: the raw Total Sales column did not actually equal Price per Unit × Units Sold for a number of rows. Rather than trust the source column, I rebuilt Total Sales myself as a calculated field (Price per Unit × Units Sold) in the Cleaned Data tab, so every downstream pivot table and KPI is based on a verified, internally consistent figure rather than the flawed raw value.

**5. Build a date dimension table**
Built a dedicated Date table as an Excel Table, then used formulas to derive time-intelligence columns: Year, Month Name, Quarter, Day Name, WeekType (Weekday/Weekend), and Month number — e.g. =MONTH([@[Invoice Date]]) to extract the month number for correct chronological sorting.

**6. Relate the tables**
Related the Date table to the Cleaned Data table on Invoice Date, enabling all pivot tables to slice consistently by day, week type, month, and quarter.

**7. Build the core pivot tables**
Built pivot tables by State, Region, City, Product, Price Band, Sales Method, WeekType, and Month on a dedicated Pivot table tab, each pulling from the cleaned, related data.

**8. Add period-over-period KPIs**
Added current-period-vs-previous-period comparison figures for the four headline KPIs — Total Sales, Units Sold, Operating Profit, and Average Operating Margin — to power the trend indicators on the dashboard.

**9. Stage secondary breakdowns**
Assembled the Analysis tab as a staging area for breakdowns like Top 5 Cities, Top 5 States, Sales by Price Band, and Sales by Sales Method, before formatting them into the final dashboard.

**10. Assemble the dashboard**
Consolidated 10+ pivot-driven visuals into a single executive-ready, one-page dashboard.

## Key Insights

**Headline performance**

| Metric | Current Period | vs. Prior Period |
|---|---|---|
| Total Sales | $120M | ▲ 9.4% (from $110M) |
| Units Sold | 2.5M | ▲ 7.4% (from 2.3M) |
| Operating Profit | $47.2M | ▲ 9.5% (from $43.1M) |
| Avg. Operating Margin | 42% | ▼ 0.1 pt (flat) |

Revenue and profit are growing faster than margin — growth is driven primarily by volume rather than pricing or mix improvements.

**Channel:** Online leads at $45M (37.5% of revenue), ahead of Outlet ($40M, 33%) and In-store ($36M, 30%).

**Regional:** West leads with $36M (30% of total), followed by Northeast ($25M) and a South/Southeast tie ($21M each). Midwest lags at $17M. California and New York tie as top states ($9M each).

**Product:** Men's Street leads at $28M (23%), followed by Women's Apparel ($24M) and Men's Athletic ($21M). Women's Athletic is weakest at $14M, pointing to a gap specifically in women's performance/athletic wear.

**Price band:** Mid-priced products drive $86M (72%); High-priced items contribute $31M (26%); Low-priced only $4M (3%).

**Weekday vs. weekend:** Weekdays generate more than double weekend revenue ($88M vs. $32M) with a slightly higher margin (42.4% vs. 42.1%).

**Seasonality:** Revenue peaks in July ($13M) and August ($12M); softest in February and March ($8M each).

## Recommendations

1. Invest further in Online while auditing In-store and Outlet in underperforming regions.
2. Prioritize the Midwest for a targeted regional growth plan.
3. Investigate the Women's Athletic underperformance specifically.
4. Protect and grow the Mid price band while testing modest premiumization in the High band.
5. Plan inventory, staffing, and marketing spend around the July–August peak; design a campaign for the February–March trough.
6. Monitor operating margin alongside revenue growth, since current growth is volume-led.
7. Test targeted weekend promotions to lift underperforming weekend sales.

## Skills Demonstrated

- Data cleaning and validation: de-duplication, type correction, formula-based derived fields
- Data integrity checks: catching and correcting a source data entry error by rebuilding a calculated field from first principles
- Data modeling: related Date dimension table, time-intelligence formulas
- Pivot table design across multiple business dimensions (region, product, price band, channel, time)
- KPI design: period-over-period growth tracking for revenue, units, profit, and margin
- Dashboard design: consolidating 10+ pivot-driven visuals into a single executive-ready view
- Technical troubleshooting: diagnosing and resolving a live-data-dependency error in Excel's geographic map chart
- Business analysis: translating raw metrics into channel, regional, product, and seasonal recommendations

---
*Adidas US Sales Analysis — Portfolio Project | Salau Bukola*
