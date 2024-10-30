# SuperStore_Sales

## Objective
Using a kaggle superstore dataset, data was explored and cleaned in SQL before using Power BI to visualise trends related towards company sales and profit metrics for owners and shareholders. Dashboard was created to give insights for which customer segments and regions should be prioritised to maximise profit margins and sales in the future.


## Tools used:
| SQL | cleaning and exploring |
| --- | ---  |
| Power BI | Visualising the data via interactive dashboards |

## Data Cleaning and Transformation

SQL was used to grab relevant columns

```SQL
select select Order_date, Segment, State, Region, Category, Sales, Quantity, Discount, Profit
from StoreData
```


Data transformation was completed in Power BI, where values were given the correct format. Then DAX measures were created to be used for the different charts and vizulisations on the dashboards. Finally, A date table was created and then joined to the sales table using a one-to-many relationship. This allows for certain metrics to be used to show both annually and quarterly.
Dax Measures
```Dax
Total Profit = SUM(Sales[Profit])
```
```Dax
Total Sales = SUM(Sales[Sales])
```
```DAX
Profit Margin = SUM(Sales[Profit]) / SUM(Sales[Sales])
```

## Visualisation:

![Dashboard](assets/images/Superstore_Dashboard.png)


## Analyse and Recomendation
Dashboard indicates that while the profit margin between all 3 segments are fairly simulary, the consumer segments bring the most amount of revenue ($661K) on average, suggesting that products in that segment may cost more to ship, or are more expensive to purchase for inventory. 

Regarding regions, the west brings hasa brought in the most sales ($725K) and have the highest profit margins (14.94%). Central significantly struggles to see profit margins despite fairly high revenue, again suggesting difficulty in shipping or high amount sales with products that do not earn much profit. Overtime, east and west have been the most consistent regions for profit margin by quarter usually in the 10-20% range with high Q4s. Central again struggles, hovering around the 1% range although having a couple of outlier Q4s.

## Recommendation
Overall, heavy focus on West and east regions as they regularly have high and consistent profit margins and generate the most sales both in revenue and in total. In the central region, explore options in improve profit margins such as increase shipping price for customers, invest in a warehouses or other facilities for stock. Futhermore, focus on pushing home office and corporate products. Ivestigate South Q4s interms of why they are inconsistant and how to improve them for the future. 
