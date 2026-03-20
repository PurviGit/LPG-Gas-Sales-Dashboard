# LPG Gas Sales Dashboard — Power BI

![Dashboard Preview](LPG_Gas_Sales_Dashboard.png)

## Live Dashboard
👉 **[View Live Dashboard](https://purvigit.github.io/LPG-Gas-Sales-Dashboard/)**

---

## Project Overview

End-to-end Business Intelligence dashboard built in Power BI for an LPG gas distribution business.
Covers **₹149.83M revenue** across **6 zones**, **10 dealers** and **3 customer segments** for FY 2024-25.

---

## Tools Used

| Tool | Purpose |
|------|---------|
| Power BI Desktop | Dashboard building and visualizations |
| Power Query | Data cleaning and transformation |
| DAX | Calculated measures and KPIs |
| Excel | Raw data source — 4 sheets, 3,287 rows |

---

## Key Metrics

| Metric | Value |
|--------|-------|
| Total Revenue | ₹149.83M |
| Cylinders Sold | 81,473 |
| Gross Margin % | 26.06% |
| Delivery SLA % | 85.49% |
| Active Dealers | 10 |
| Zones Covered | 6 |

---

## Dashboard Features

- 5 KPI cards — Revenue, Cylinders, Gross Margin, SLA %, Active Dealers
- Line chart — Monthly revenue trend split by 3 customer types
- Donut chart — Product mix by cylinder size (5kg, 14.2kg, 19kg, 47.5kg)
- Horizontal bar chart — Zone-wise revenue with unique color per zone
- Dealer performance table — ranked by total revenue
- Gauge chart — Target vs Actual revenue
- Map visual — City-level revenue by bubble size
- 4 interactive slicers — Zone, Year, Customer Type, Quarter
- Business Insights text box — key findings written as analyst observations

---

## DAX Measures Written

```dax
Total Revenue = SUM(Sales_Transactions[Total_Revenue_INR])

Total Cylinders = SUM(Sales_Transactions[Quantity_Sold])

Gross Profit = SUM(Sales_Transactions[Gross_Profit_INR])

Gross Margin % = DIVIDE([Gross Profit], [Total Revenue], 0) * 100

SLA % = DIVIDE(
    COUNTROWS(FILTER(Sales_Transactions, Sales_Transactions[Delivery_Status] = "On-Time")),
    COUNTROWS(Sales_Transactions), 0) * 100

Revenue vs Target = [Total Revenue] - SUM(Monthly_Targets[Target_Revenue_INR])
```

---

## Data Model — 4 Tables

```
Sales_Transactions  →  Dealer_Master    (on Dealer_ID)
Sales_Transactions  →  Product_Master   (on Product_SKU)
Sales_Transactions  →  Monthly_Targets  (on Zone + Month)
```

---

## Business Insights Found

- **West zone** contributes highest revenue at ₹27M — leads all 6 zones
- **Domestic segment** shows 20–25% volume spike during Nov–Feb winter months
- **Central zone SLA** drops to ~80% — below 85% threshold, delivery route needs fixing
- **Industrial 47.5kg** cylinders generate highest revenue per unit across all SKUs
- **Revenue grew 12.4% YoY** — consistent growth across all zones

---

## Files in This Repository

| File | Description |
|------|-------------|
| `LPG Gas Sales Dashboard.pbix` | Power BI dashboard — open in Power BI Desktop |
| `LPG_Sales_Data.xlsx` | Raw dataset — 4 sheets, 3,287 rows |
| `Theme.json` | Custom dark navy theme — import in Power BI |
| `LPG_Gas_Sales_Dashboard.png` | Full resolution dashboard screenshot |
| `index.html` | GitHub Pages live preview page |

---

## How to Open Locally

1. Download `LPG Gas Sales Dashboard.pbix`
2. Open in **Power BI Desktop** (free download at powerbi.microsoft.com)
3. Data loads automatically from the Excel file
4. All slicers and visuals are interactive

---

## Connect

**Purvi Porwal**  
📧 purviporwal46@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/purvi-porwal-a6554a258)  
💻 [GitHub](https://github.com/PurviGit)
