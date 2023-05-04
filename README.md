# Market_Research_Excel
Price Elasticity and Product Demand Forecasting conducted on sales data in excel

![image](https://user-images.githubusercontent.com/131872943/236243902-478757fd-9d7f-42e6-bfad-de89c0db5795.png)

Data is imported, cleaned and order totals calculated. Month number is extracted for use in seasonality exploration.

![image](https://user-images.githubusercontent.com/131872943/236244239-f955806f-7ed8-4e69-8728-fd40863cbb52.png)

The extracted month number is changed to month name in a separate column for clarity in visualisation. There appears to be certain seasonal peaks September, December and January, with the largest peak in April. This will need to be taken into account when refining predictions. 

Unit Sales are calculated for two distinct products. 
![image](https://user-images.githubusercontent.com/131872943/236245026-fff37894-bd35-4f4b-969a-99e65e79dc98.png)

Initial rough predictions can be calculated using moving averages and weighted moving averages. 
![image](https://user-images.githubusercontent.com/131872943/236245218-5e99f152-57ac-442f-94fe-f629e217effd.png)

April is weighted accordingly due to it's previous seasonal peak. 

A new product is being considered and demand forecasting is calculated based off of a weighting of it's similarity to three existing products. 
![image](https://user-images.githubusercontent.com/131872943/236245658-cbb83d67-8588-42aa-bb0c-6dc7d5576e02.png)

In order to analyse how sensitive customers are to an increase in price, price elasticity analysis is conducted.
Price Elasticity for product 1 is calculated in order to ensure revenue maximisation. Here, unit sales are calculated across each of a series of theoretical price points based off of known unit sales at specific price points. Unit Demand Curves always slope down as the price increases and this is what appears. The product sees a reduction in demand of 36% when the price changes from $4.99 to $6.99. From this we can calculate the reduction in demand on hypothetical pricing at $7.99 and $8.99. We can predict the demand will reduce by 56% if the price is raised from $4.99 to $7.99. A further dramtic reduction in demand would be witnessed of approximatately 90% if the price were raised from $4.99 to $8.99. 

We can project sales of 313 units at a price of $7.99, with a Revenue of $2,504.76. Revenue would increase from $1,991.01 at a price of $4.99 with 399 unit sales. 

![image](https://user-images.githubusercontent.com/131872943/236247832-497018ef-da97-4e09-b165-4f63b0d9ccf7.png)

Using regression alone is of limited value, conveying what factors affect sales but not what our sales would be. However, we can take a Regression and use it to create a demand forecast. 

![image](https://user-images.githubusercontent.com/131872943/236248920-c7e2a7f3-ee2c-401a-b543-66c74fbfab97.png)

The Regression tells us we can capture about 15% of the variation in units sold based simply on product_type, price and month. 
The t-statistics in this regression tell us that product_type and price are statistically significant drivers of our units sold. 
In Summary: Price and Product_Type are the important factors to take into account when sales forecasting. 

Applying the Regression to conclude a forecast.
<img width="1093" alt="image" src="https://user-images.githubusercontent.com/131872943/236249881-024745bd-8fca-44be-9f02-22f4186329af.png">

What this tells us is that Product 2 has a negative unit demand of 28 sales relative to Product 1. 
Having a price point of $9.99 has a negative impact of 34 unit sales. 
The month has an impact of positive 4 sales. 

The R-Squared value in this regression indicates that the regression is not going to be particularly accurate. More datapoints would increase accuracy metrics as in this instance we are only able to capture about 15% of the variation in our unit_sales. The confidence interval also has a wide relative range.  
