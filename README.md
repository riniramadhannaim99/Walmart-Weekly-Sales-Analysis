# Walmart Weekly Sales Analysis

Exploratory data analysis (EDA) and an interactive Power BI dashboard built on weekly
sales from **45 Walmart stores** (Feb 2010 – Oct 2012, 6,435 records). The goal is to
understand what drives sales: store size, holidays, seasonality, and external factors.

## Dashboard Preview

![Walmart Sales Dashboard](dashboard/screenshots/dashboard_preview.png)

### What the dashboard shows
| Visual | Purpose |
|---|---|
| KPI cards | Total weekly sales (**6.74bn**), average weekly sales (**~1,047K**), total stores (**45**) |
| Total Weekly Sales Trend | Weekly sales over time, with clear spikes at year-end |
| Sales Share by Year | Share of total sales for 2010, 2011, and 2012 |
| Avg Weekly Sales: Holiday vs Non-Holiday | Average sales in holiday weeks (~1,122K) vs regular weeks (~1,041K) |
| Average Weekly Sales by Store | Stores ranked by average weekly sales |
| Avg Weekly Sales by Store: Holiday vs Non-Holiday | Holiday effect compared store by store |
| Slicers (Month, Store) | Filter every visual by month or by individual store |

> Note: 2010 starts in February and 2012 ends in October, so the yearly share is not a
> like-for-like comparison.

## Key Findings
- **Store identity matters most.** The largest store averages ~8x the weekly sales of the
  smallest, so comparisons should be made relative to each store's own average.
- **Holiday weeks lift sales by ~7.8% on average** (statistically significant), but the
  effect varies by store and by holiday (Thanksgiving ~+38%, Super Bowl ~+3%,
  Christmas week slightly lower).
- **Strong year-end seasonality.** December is ~39% above January, and the pattern repeats
  every year while the overall yearly trend stays flat.
- **Weekly sales are right-skewed.** A few very high weeks (large stores, Thanksgiving,
  December) pull the mean above the median.
- **Temperature, fuel price, CPI, and unemployment** show no clear linear relationship
  with sales.

## Recommendations
- Prepare stock and staffing for **November–December**.
- Set targets **per store** rather than one holiday assumption for the whole chain.
- Review small stores that do not gain during holiday weeks.
- Use month/week together with the holiday flag for forecasting.

## Tools
Python (Jupyter Notebook, pandas, matplotlib/seaborn) and Power BI Desktop.

## Repository Structure
```
walmart-sales-analysis/
├── README.md
├── data/
│   └── Walmart.csv
├── notebooks/
│   └── walmart_data_analysis_final.ipynb
├── dashboard/
│   ├── walmart_dashboard.pbix
│   └── screenshots/
│       └── dashboard_preview.png
└── requirements.txt
```

## How to Use
1. **Notebook:** install the requirements (`pip install -r requirements.txt`) and open
   `notebooks/walmart_data_analysis_final.ipynb` in Jupyter.
2. **Dashboard:** open `dashboard/walmart_dashboard.pbix` in Power BI Desktop
   (if the data source path breaks, point it to `data/Walmart.csv` via
   *Transform data → Data source settings*).

## Limitations
About 3 years of data, no product or promotion data, and a limited holiday flag.
