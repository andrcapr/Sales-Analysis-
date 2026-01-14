# Sales-Analysis-
Python Data Analysis project as part of the Kodree course.
Project Overview
This project performs a comprehensive data analysis on sales data from three interconnected datasets: events.csv, countries.csv, and products.csv. The goal is to extract valuable business insights by analyzing sales performance across various dimensions, including product categories, geographical regions, sales channels, and temporal trends. The analysis covers data overview, cleaning, merging, calculating key performance indicators, and in-depth analysis of sales dynamics, shipping times, and seasonality, culminating in actionable business conclusions.
Datasets Used
events.csv: Contains detailed information about each order, including order ID, dates, priority, country code, product ID, sales channel, units sold, unit price, and unit cost.
countries.csv: Provides geographical details for countries, including country names, alpha-2 and alpha-3 codes, region, and sub-region.
products.csv: Maps product IDs to their respective item types (product categories).
Analysis Steps and Methodology
1. Data Overview
Objective: Familiarize with dataset structures, identify key fields, and initial data types.
Outcome: Initial inspection of events_data, countries_data, and products_data revealed column names, data types, and potential issues like missing values and incorrect data types (Order Date, Ship Date). Key fields for merging (Country Code/alpha-3, Product ID/id) were identified.
2. Data Cleaning - Missing Values
Objective: Identify and handle missing values appropriately.
Methodology:
events_data: Country Code (6.17% missing) was filled with 'Unknown'. Units Sold (0.15% missing) rows were dropped due to their small proportion.
countries_data: region and sub-region had one missing entry (for 'Antarctica'), which was manually filled with 'Antarctica'.
products_data: No missing values were found.
3. Data Cleaning - Data Types
Objective: Convert columns to appropriate data types for analysis.
Methodology: Order Date and Ship Date in events_data were converted from object to datetime objects.
4. Data Cleaning - Duplicates and Anomalies
Objective: Detect and resolve duplicates and inconsistencies in categorical data.
Methodology:
No fully duplicate rows were found in any of the three datasets.
Categorical columns like Order Priority and Sales Channel in events_data were cleaned by stripping whitespace and standardizing casing (e.g., ' C' to 'C', 'online' to 'Online').
5. Data Merging and Preparation
Objective: Combine the three datasets into a single, cohesive DataFrame and refine its structure.
Methodology:
events_data was left-merged with products_data on Product ID and id to add Product Category.
The resulting DataFrame was then left-merged with countries_data on Country Code and alpha-3 to incorporate geographical details (Country Name, Region, Sub-Region).
Redundant columns (id, alpha-2, alpha-3) were dropped.
New columns Revenue, Cost, and Profit were calculated for each order.
6. Key Performance Metrics (KPIs)
Objective: Calculate fundamental business metrics.
Outcome:
Total Revenue: $1,702,129,408.21
Total Cost: $1,200,694,949.21
Total Profit: $501,434,459.00
Total Number of Orders: 1328
Total Number of Covered Countries: 45
7. Sales Analysis and Visualization
Objective: Analyze sales performance across product categories, geography, and sales channels.
Methodology:
By Product Category: Aggregated total revenue, profit, and units sold. Visualized using bar plots. Top categories by revenue were 'Office Supplies', 'Household', and 'Cosmetics'.
By Geography (Countries & Regions): Aggregated total revenue, profit, and units sold for countries (top 10 visualized) and regions. Europe significantly dominated sales. Top countries by revenue included Czech Republic, Ukraine, and Bosnia and Herzegovina.
By Sales Channel: Aggregated total revenue, profit, and units sold for 'Online' and 'Offline' channels. Visualized using bar plots. 'Offline' slightly outperformed 'Online'.
8. Shipping Time Analysis
Objective: Investigate the impact of shipping duration on profit.
Methodology:
Shipping Duration (in days) was calculated as Ship Date - Order Date.
Average shipping duration and total profit were analyzed by product category, country (top 10), and region. Visualizations included bar plots for average shipping duration and scatter plots to observe the relationship between profit and shipping duration.
Outcome: No strong linear correlation was observed between shipping duration and profit across product categories, countries, or regions. Overall, average shipping durations were consistent, ranging from ~21 to 33 days.
9. Sales Dynamics Over Time
Objective: Identify trends and seasonality in sales over time.
Methodology:
Extracted Order Year and Order Month from Order Date.
Analyzed total revenue and profit trends over time using line plots.
Examined revenue trends over time by product category, top 5 countries, and regions using line plots.
Outcome: Sales exhibit fluctuating dynamics with peaks and troughs across years and months, with specific trends varying by product category and geographic entity.
10. Seasonal Sales Analysis
Objective: Analyze sales patterns by days of the week to identify seasonality.
Methodology:
Extracted Order Day of Week from Order Date.
Aggregated and visualized total revenue by day of the week using bar plots.
Aggregated and visualized total revenue by product category and day of the week using grouped bar plots.
A heatmap was generated to show the average daily profit by product category, revealing variations in profit patterns across different days for different products.
Outcome: Daily sales patterns vary by product category, indicating diverse purchasing behaviors across days of the week, with no single dominant day for all categories.
Business Conclusions and Insights
Overall Performance: The company demonstrates strong financial health with substantial total revenue and profit, indicating a robust market presence.
Strategic Focus on High-Profit Categories and Regions: Given the significant profit contribution from 'Cosmetics', 'Office Supplies', and 'Household' categories, and Europe's overwhelming dominance, the company should consider increased investment and targeted marketing strategies in these areas to further capitalize on existing strengths.
Optimize Offline Sales Channel: The 'Offline' sales channel currently slightly outperforms the 'Online' channel. Investigating the factors contributing to this performance gap could lead to actionable insights to either enhance the 'Online' channel's effectiveness or further leverage the strengths of the 'Offline' channel.
Shipping Impact: Shipping duration does not appear to be a primary driver of profit, suggesting that current shipping logistics are likely not significantly deterring sales or impacting profitability negatively. Focus should remain on efficiency rather than speed as a competitive differentiator if other factors are stable.
Temporal and Seasonal Analysis: Understanding the temporal and seasonal sales patterns for specific product categories and regions can help in optimizing inventory management, marketing campaigns, and resource allocation throughout the year.
Technical Details
Libraries Used: pandas for data manipulation, matplotlib.pyplot and seaborn for data visualization.
Key Techniques: Data loading, cleaning (handling missing values, data type conversion, duplicate removal, anomaly detection), merging DataFrames, aggregation, and various plotting techniques (bar plots, line plots, scatter plots, heatmaps).
This project provides a solid foundation for understanding the company's sales landscape and offers data-driven recommendations for strategic business decisions.
