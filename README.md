Project Title:  Superstore Sales Performance Dashboard
___________________________________________________________________________________________________________________________________________________________________

Project Overview

This project focuses on building an interactive Power BI dashboard for analyzing sales data from a Superstore. The goal is to provide key insights into various aspects of the store’s performance, including sales, profits, returns, product categories, and customer segmentation, with a focus on geographic and temporal analysis.
___________________________________________________________________________________________________________________________________________________________________

Objectives:

1. Analyze sales and profit trends by year-over-year (YOY) comparisons.

2. Examine regional and state-wise sales distributions.

3. Segment sales by categories, sub-categories, and shipping modes.

4. Identify top-performing products and payment modes.

5. Visualize sales trends by order date and ship mode.
___________________________________________________________________________________________________________________________________________________________________

Data Sources

*Superstore Sales Data: This dataset contains 23 columns and 5901 rows of data containing sales records, customer details, product categories, shipping details, and geographic information (cities, states).

*Key Variables include:

1) Sales: Total sales in USD.

2) Profit: Profit margin from the sales.

3) Quantity: Number of products sold.

4) Returns: Items returned by customers.

5) Products and Categories: Breakdown by product type, category, and subcategory.

6) Shipping Details: Ship date, modes, and delivery time.

7) Geographic Information: Regions and states.
___________________________________________________________________________________________________________________________________________________________________

Key Metrics Visualized

1. Total Quantity Sold: 22K units

2. Total Sales: $2M

3. Total Profit: $175K

4. Returns: 5901 items

5. Number of Products: 1755 unique products

6. Total Cities: 452 cities covered

7. Average Shipping Days: 4 days
___________________________________________________________________________________________________________________________________________________________________

Dash Board Screenshot

___________________________________________________________________________________________________________________________________________________________________

DAX-Formula used :

1. Year-Over-Year (YOY)  Sales Growth = 
VAR PreviousYearSales = CALCULATE([Total Sales], SAMEPERIODLASTYEAR('Sales'[Order Date])) RETURN IF(NOT(ISBLANK(PreviousYearSales)), ([Total Sales] - PreviousYearSales) / PreviousYearSales, BLANK())

2.Total Sales= SUM('Sales'[Sales])

3.Total Profit = SUM('Sales'[Profit])

4.Profit Margin = DIVIDE([Total Profit], [Total Sales], 0)

5. Total Quantity Sold = SUM('Sales'[Quantity])
   
6. Total Returns = COUNT('Sales'[Return ID])

7. Unique Products Count = DISTINCTCOUNT('Sales'[Product ID])

8. Average Shipping Days= AVERAGE('Sales'[Shipping Days])

9. Sales by Category = SUMX(FILTER('Sales', 'Sales'[Category] = EARLIER('Sales'[Category])), 'Sales'[Sales])

10.Sales by Subcategory = SUMX(FILTER('Sales', 'Sales'[Sub-Category] = EARLIER('Sales'[Sub-Category])), 'Sales'[Sales])

11. Sales by State = CALCULATE(SUM('Sales'[Sales]), 'Sales'[State])

12. Sales by Shipping Mode = CALCULATE(SUM('Sales'[Sales]), 'Sales'[Ship Mode])

13.Sales by Region = CALCULATE(SUM('Sales'[Sales]), 'Sales'[Region])

14. Sales by Customer Segment = CALCULATE(SUM('Sales'[Sales]), 'Sales'[Segment])

15. Sales by Payment Mode = CALCULATE(SUM('Sales'[Sales]), 'Sales'[Payment Mode])
    
16. Sales Trends by Order Date = CALCULATE([Total Sales], DATESYTD('Sales'[Order Date]))

17. Sales Trends by Ship Date = CALCULATE([Total Sales], DATESYTD('Sales'[Ship Date]))

18.YOY Profit Growth = VAR PreviousYearProfit = CALCULATE([Total Profit], SAMEPERIODLASTYEAR('Sales'[Order Date]))
RETURN IF(NOT(ISBLANK(PreviousYearProfit)), ([Total Profit] - PreviousYearProfit) / PreviousYearProfit, BLANK())

___________________________________________________________________________________________________________________________________________________________________

Dashboard Components

* Sales by Category and Subcategory: This bar chart displays sales breakdowns for key product categories such as Technology, Furniture, and Office Supplies. Subcategories like Phones, Chairs, and Binders have been highlighted as top-selling products.

* Monthly Sales & Profit by YOY Comparison: A line graph comparing sales and profits for the years 2019 and 2020 shows the fluctuation in sales trends over time.

* Sales and Profit by State: A geographical heat map highlights top states such as California, New York, and Texas in terms of sales contribution. This helps to pinpoint high-revenue states and target sales strategies accordingly.

* Sales by Shipping Mode: The dashboard illustrates the sales performance for different shipping modes like Standard Class, Second Class, First Class, and Same Day.

* Sales by Region: A pie chart categorizing sales by regions such as Central, East, South, and West provides insights into how different regions are contributing to the overall performance.

* Sales by Segment: Another pie chart segments sales into categories like Consumer, Corporate, and Home Office, giving a clear picture of customer types.

* Sales by Payment Mode: Payment distribution is visualized across multiple modes, with a focus on COD, Online payments, and Cards.

* Sales Trend over Time: Two time-series graphs showing the progression of sales over time (by Order Date and by Ship Date) give insight into sales fluctuations, peaks, and slowdowns.

_________________________________________________________________________________________________________________________________________________________________

Challenges Encountered:

Data Cleaning:

Challenge: Inconsistent data entries across different categories, null values, and missing geographic data points.

Solution: Power Query was used to clean the data by removing duplicates, handling missing values, and correcting inconsistent state names.

Calculating Suitable Measures:

Challenge: Determining the appropriate KPIs for tracking store performance effectively across multiple categories and segments.

Solution: Identified critical KPIs such as YOY sales growth, sales per product, profit margin, and shipping efficiency. Created custom measures using DAX in Power BI to accurately calculate these values.

Handling High Volume of Data:

Challenge: Large datasets can slow down report generation and affect performance.

Solution: Applied appropriate filters and aggregated data at necessary granularity (monthly and yearly totals) to enhance performance without sacrificing detail.

Dynamic Visualizations:

Challenge: Displaying trends dynamically by region, category, and customer segment.

Solution: Leveraged slicers and dynamic filters in Power BI to allow users to explore the data by different criteria interactively.
__________________________________________________________________________________________________________________________________________________________________
Key Insights:

1. Performance Across Categories: Technology and Office Supplies are the best-performing categories, while Furniture has potential for improved sales.

2. State and Regional Focus: States like California and New York lead in sales, indicating potential for focused marketing in these areas. States with lower sales could benefit from targeted promotional campaigns.

3. Shipping Optimization: Standard Class dominates shipping mode usage, with minimal reliance on First Class and Same Day, suggesting potential areas for optimizing shipping costs.

4. Seasonal Sales Trends: Sales peak around holiday seasons (December) and experience slowdowns in earlier months like January and February, allowing for season-specific strategies.
___________________________________________________________________________________________________________________________________________________________________

Conclusion:

The Superstore Sales Dashboard has enabled a comprehensive view of the store’s performance, helping stakeholders make informed decisions. By leveraging Power BI’s dynamic filtering and interactive visuals, key insights into product sales, customer segmentation, and geographic performance have been uncovered, guiding future strategies for maximizing revenue and improving shipping logistics.

