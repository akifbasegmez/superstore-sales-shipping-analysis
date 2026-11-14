# Superstore Sales & Shipping Analysis

A Tableau business intelligence project examining **sales trends, profitability, and order-to-shipment performance** using the Sample Superstore dataset (2020–2023).

**[Explore the Interactive Dashboard on Tableau Public](https://public.tableau.com/views/SuperstoreSalesShippingAnalysis_17946629183810/GnderimPerformans)**

![Shipping Performance Dashboard](assets/shipping-performance.png)

## Project Objectives

- Track monthly sales and profit trends to identify performance changes over time.
- Compare profitability across product categories, subcategories, and shipping methods.
- Evaluate order processing time and shipping patterns across US states.

## Key Metrics

| Metric | Result |
| --- | ---: |
| Total unique orders | **5,009** |
| Average order-to-ship time | **3.96 days** |
| Same-day shipping rate | **5.03%** |
| Most common order-to-ship time | **4 days (1,401 orders)** |

## Analysis & Methods

- **Sales and profit trends:** Created monthly dual-axis time-series charts to compare sales and profit, with filters for customer segment and shipping method.
- **Profitability analysis:** Built a color-coded comparison by category, subcategory, and ship mode using a calculated **profit margin** measure.
- **Shipping analysis:** Used Tableau calculated fields and aggregations to measure shipping time, count distinct orders by processing-day bucket, and compare average times across shipping methods.
- **Geographic analysis:** Visualized average order-to-ship time by US state on an interactive map, with date, segment, and ship mode filters.

### Core Calculations

```tableau
// Order-to-ship time
DATEDIFF('day', [Order Date], [Ship Date])

// Profit margin
SUM([Profit]) / SUM([Sales])

// Distinct order count
COUNTD([Order ID])
```

The profit-margin calculation includes a zero-sales check in the workbook. Same-day shipping rate is calculated as distinct orders shipped on the order date divided by total distinct orders.

## Tools & Project Files

**Tools:** Tableau Public · Calculated Fields · Dual-Axis Charts · Geographic Maps · Interactive Filters

- [Tableau packaged workbook (.twbx)](tableau/Superstore-Sales-Shipping-Analysis.twbx)
- [Dashboard screenshot (.png)](assets/shipping-performance.png)
- [Sample Superstore dataset](https://docs.google.com/spreadsheets/d/1B6NRip0PBVx9uUgYYUO6iczNwOnSJCPO/edit?gid=580066455#gid=580066455)

> **Metric definition:** Shipping time measures the number of days between order date and ship date; it does not measure final customer delivery time.
