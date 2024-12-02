# E-commerce-Insights

Created an Interactive dashboard of e-commerce sales based on 3 segments.

1. Consumer

2. Corporate

3.  Home Office

#  

The Power BI dashboard presents Year-to-Date (YTD) performance metrics, including Sales, Profit, Quantity, and Profit Margin. These metrics are visually tracked over time and across categories, leveraging dynamic DAX calculations and visual elements such as line charts and tables. Filters by Month and Category Segment enable users to drill down into specific performance insights. The dashboard integrates trend analysis (Sales Trend) and Year-over-Year (YoY) comparisons for more granular data interpretation.

#  

The dashboard incorporates spatial analytics with a map visualization showing YTD Sales by Location, segmented by region (Central, East, South, and West) using geospatial data layers. Additionally, it evaluates sales by Shipping Type and Customer Region with pie and bar charts. These insights are dynamically connected to slicers and filters, allowing stakeholders to assess regional and category-specific trends, built using Power Query for ETL processes and calculated DAX measures to ensure data consistency.

#  

**DAX measure created:** 

YTD Sales = TOTALYTD(SUM(ecommerce_data[sales_per_order]), 'Calender'[Date])

YTD quantity = TOTALYTD(SUM(ecommerce_data[order_quantity]), 'Calender'[Date])

YTD profitmargin = TOTALYTD(ecommerce_data[Profit margin], 'Calender'[Date])

YTD Profit = TOTALYTD(SUM(ecommerce_data[profit_per_order]), 'Calender'[Date])

YoY Sales = ([YTD Sales] - [PYTD Sales])/[PYTD Sales]

YoY Quantity = ([YTD quantity] - [PYTD quantity])/[PYTD quantity]

YoY profitMargin = ([YTD profitmargin] - [PYTD profitMargin])/[PYTD profitMargin]

YoY profit = ([YTD Profit] - [PYTD profit])/[PYTD profit]

SalesTrend_icon = var positive_icon = UNICHAR(9650)
                var negative_icon = UNICHAR(9660)
                var result = IF([YoY Sales]>0, positive_icon, negative_icon)
                return result

Sales Icon color = IF([YoY Sales]>0 , "Green", "Red") 

#  

![image](https://github.com/user-attachments/assets/d33a5109-8486-43d1-9fd8-4ed77b7a2b0b)

#  

![image](https://github.com/user-attachments/assets/f03121b0-44ee-42be-9d7a-bf4e7e669679)


#  
![image](https://github.com/user-attachments/assets/d5233c19-3b77-4567-9562-5b0ef81462b4)
