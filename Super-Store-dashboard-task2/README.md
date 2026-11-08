# Superstore Sales & Profit Dashboard (Power BI)

**Elevate Labs Data Analyst Internship – Task 2: Data Visualization and Storytelling**

An interactive Power BI dashboard that analyzes four years of Superstore retail data (2014–2017) and turns it into a clear business story: sales are growing, but heavy discounts and three loss-making sub-categories are eroding profit.

## Dashboard Preview

![Dashboard](screenshots/dashboard.png)

## Objective

Use visualization to answer:
- How are sales and profit trending over time?
- Which categories and sub-categories drive profit, and which lose money?
- How do discounts affect profitability?
- Which regions and customer segments perform best?

## Dataset

- **Source:** Superstore dataset (Kaggle, `vivek468/superstore-dataset-final`)
- **Size:** 9,994 rows, 21 columns
- **Period:** January 2014 – December 2017
- **Key fields:** Order Date, Segment, Region, State, Category, Sub-Category, Sales, Quantity, Discount, Profit

## Tools

- Power BI Desktop (Power Query for cleaning, DAX for measures)

## Data Preparation

1. Loaded the CSV with Windows-1252 encoding.
2. Converted Order Date and Ship Date using the English (United States) locale (M/D/YYYY).
3. Set correct data types (Postal Code as text, Sales/Profit as decimal).
4. Set data categories for State and Country for map visuals.

## DAX Measures

```DAX
Total Sales = SUM('Sample - Superstore'[Sales])
Total Profit = SUM('Sample - Superstore'[Profit])
Profit Margin % = DIVIDE([Total Profit], [Total Sales])
Total Orders = DISTINCTCOUNT('Sample - Superstore'[Order ID])
Total Quantity = SUM('Sample - Superstore'[Quantity])
```

## Dashboard Contents

| Visual | Purpose |
|---|---|
| KPI cards | Total Sales, Total Profit, Profit Margin %, Total Orders |
| Line chart | Sales trend by year |
| Bar chart | Profit by sub-category (losses in red) |
| Clustered column | Sales vs profit by category |
| Scatter / bar | Profit margin by sub-category, discount impact |
| Donut / map | Sales by segment or profit by state |
| Slicers | Year, Region, Category |

## Key Insights

1. **Sales are growing.** Sales rose from about $484K in 2014 to about $733K in 2017 (+51%), with a Q4 peak each year. Overall: $2.30M sales, $286K profit, 12.5% margin.
2. **Three sub-categories lose money.** Tables (-$17.7K), Bookcases (-$3.5K) and Supplies (-$1.2K) are unprofitable despite meaningful sales.
3. **Furniture is high sales, low profit.** It generates $742K in sales but only $18K in profit, compared with Technology ($145K) and Office Supplies ($122K).
4. **Discounts above 20% destroy profit.** Orders with 0–20% discounts are profitable on average; at 30% and above the average order makes a loss.
5. **West and East lead on profit.** West ($108K) and East ($92K) outperform Central ($40K) and South ($47K).
6. **Consumer is the biggest segment**, at about 50% of total sales.

## Recommendations

- Cap discounts at around 20% and review approval rules for deeper discounts.
- Reprice, renegotiate supplier costs, or phase out Tables and Bookcases.
- Invest in high-margin lines such as Copiers, Phones and Accessories.
- Investigate loss-making states (e.g. Texas, Ohio, Pennsylvania, Illinois) for discount and shipping issues.

## Repository Structure

```
├── data/           Superstore.csv
├── dashboard/      superstore_dashboard.pbix, dashboard.pdf
├── screenshots/    dashboard.png
└── README.md
```

## How to Use

1. Download `superstore_dashboard.pbix`.
2. Open it in Power BI Desktop.
3. Use the slicers to filter by year, region and category.

## Author

**Ahemad Maheed Khan**
GitHub: [samadkhan-18](https://github.com/samadkhan-18) · [LinkedIn](https://www.linkedin.com/in/ahemad-maheed-khan-76a0a1301/) · [Portfolio](https://samad-portfolio.onrender.com/)
