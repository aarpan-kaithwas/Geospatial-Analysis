# Geospatial Data Analysis — Retail Expansion Strategy

## Project Overview
This project analyzes location-based retail sales data across major Indian cities to identify optimal regions for business expansion. By evaluating total revenue demand alongside shipping delays (as a proxy for local warehouse/store presence), the analysis highlights high-demand markets that are currently underserved.

## Dataset
- **Source:** Indian Retail Sales Dataset (`retail_sales_dataset.csv`)
- **Key Features Used:** `city`, `region`, `sales_amount`, `order_id`, `order_status`, `days_to_ship`, `shipping_cost`
- **Data Cleaning:** Removed missing geographic/sales entries, standardized city/region casing, excluded cancelled orders, capped extreme 99th-percentile synthetic outliers, and filtered invalid shipping durations.

## Methodology
1. **Demand Aggregation:** Calculated total sales revenue and order volume per city.
2. **Presence Gap Proxy:** Used average `days_to_ship` to measure fulfillment bottlenecks caused by low local physical presence.
3. **Expansion Opportunity Score:** Combined normalized sales demand with normalized shipping delay to rank cities with both high revenue and high fulfillment lag.
4. **Geospatial Visualization:** Mapped city coordinates across India using `plotly.express.scatter_geo` (`india_expansion_map.html`).

## Top 5 Expansion Target Cities

| Rank | City | Region | Total Sales (₹) | Total Orders | Avg Ship Days | Expansion Score |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: |
| 1 | **Chennai** | South | ₹14,531,595 | 213 | 5.55 | 0.925 |
| 2 | **Guwahati** | East | ₹11,696,852 | 215 | 5.61 | 0.753 |
| 3 | **Delhi** | North | ₹11,158,448 | 184 | 5.80 | 0.742 |
| 4 | **Hyderabad** | South | ₹11,171,310 | 202 | 5.45 | 0.698 |
| 5 | **Mumbai** | West | ₹10,308,786 | 206 | 5.78 | 0.684 |

## Key Recommendations
- **Primary Expansion Markets:** Prioritize establishing regional fulfillment hubs or retail stores in **Chennai** and **Guwahati**, which generate the highest sales volume while experiencing 5.5+ day shipping times.
- **Secondary Expansion Markets:** Target **Delhi**, **Hyderabad**, and **Mumbai** next to reduce 5.4–5.8 day delivery times across high-volume customer bases.

## Files in This Repository
- `Geospatial_Expansion_Analysis.ipynb` — Complete data cleaning, scoring, and visualization notebook
- `india_expansion_map.html` — Interactive geospatial bubble map of expansion opportunities
- `retail_sales_dataset.csv` — Retail sales dataset used for the analysis
