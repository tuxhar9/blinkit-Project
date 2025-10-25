# 🛒 Blinkit City Insights — Estimated Sales Analysis (SQL Project)
## Project Objective
Analyze Blinkit store-level and city-level inventory data to estimate quantity sold per SKU and generate a comprehensive interactive report for demand and restocking insights. The goal is to create a derived table blinkit_city_insights that combines inventory, category, and store-city information to support business decision-making.

## Dataset Used
- <a href ="https://drive.google.com/drive/folders/13Ra1PQuOT5Nv5HVb2ygrW2QAKBsqv6uY">Dataset</a>


## Key Questions / KPIs
- Estimate quantity sold (est_qty_sold) per SKU at each store and time interval.
- Identify top-selling SKUs and categories per city.
- Understand restock patterns and inventory fluctuations.
- Analyze city-wise sales distribution.
- Determine the impact of discounts and promotions on sales.
- Identify high-demand stores and regions for strategic stocking.
## Process
### Data Cleaning & Validation

- Verified inventory, store, and category tables for missing or inconsistent values.
- Excluded stores without city mapping.

### Inventory Movement Analysis

-Tracked inventory changes over time per SKU per store.
- Case 1 – Inventory Decrease: Indicates sales → est_qty_sold = previous_inventory - current_inventory.
- Case 2 – Inventory Increase (Restock): Estimate sales using the average of previous 3 sales intervals.

### Data Integration

- Joined inventory data with blinkit_categories and blinkit_city_map.
- Created the derived table blinkit_city_insights with SKU, store, city, category, price, discount, inventory, and estimated sales.

### SQL Implementation

- Used window functions (LAG, AVG) to calculate previous inventory and estimate sales.
- Aggregated data for city-level and category-level insights.

## Key Insights
- Certain SKUs consistently sell more in specific cities, indicating regional preferences.
- Restock events often coincide with increased sales, helping predict inventory needs.
- Discounted SKUs show higher estimated sales, highlighting the effectiveness of promotions.
- Categories like staples and beverages dominate sales in multiple cities.

## Final Conclusion
To optimize Blinkit operations and increase sales:

- Focus on high-demand SKUs and categories in each city.
- Plan restocking schedules based on historical sales trends to avoid stockouts.
- Leverage discounts strategically to boost sales of slower-moving items.
- Use the blinkit_city_insights table as a dynamic source for dashboards, city-wise sales tracking, and inventory planning.

## Tools Used

- SQL (PostgreSQL / MySQL) – data integration, window functions, derived table creation
- Analytical Techniques – inventory tracking, estimated sales calculation
