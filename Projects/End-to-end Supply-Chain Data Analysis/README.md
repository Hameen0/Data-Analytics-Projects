
# DATA-CO SUPPLY CHAIN ANALYSIS
## Summary
Anlysis of Data-co supply-chain dataset (having a size of 180519, 53) containing information on orders covering customer identifiers and demographics, product categories, location,  shipping and delivery details, profits, discounts, and inventory. During the data cleaning stage, 'Product Description' column with no data and 'Order Zipcode' column with 155679 nulls were dropped also were 3 rows with missing data, all PII columns were also dropped consequntly reducing the data size to (180516, 39). There was no duplicated rows however 5 duplicated columns were found and dropped. The columns were formatted appropriately with dates formatted to datetime, categories to str, and numbers left as int64 and float64. New features were created i.e year, quarter, month, shipping variance, order_shipping_lag and profited as new columns. Descriptive statistics, aggregation and visuals were utilized to find patterns and insights. 

The data indicated that some product categories have higher chance of loss than others, shipping delays and late delivery reduce profit however same day delivery also reduce profits, most of the sales are on products with prices below 500 and overall profit increase with sales. In Q4 2017 sales nearly halved compared to previous years. The most profitable customers are consumers and coporate customers and the Technology department generates the highest revenue and profit.

In conclusion to increase sales and profit, investigation should be carried out to find the cause of the revenue drop in 2017, and the cause of high standard deviation in profit from Strength training and basketball product categories. As Seen on  TV! and  Men's Clothing categories should also be investigated or eliminated. Marketing activities should be carried-out to target more consumers and coporate customers, particularly from the Technology department. Shipping and delivery should be optimized to reduce lag and increase advance delivery, however same day delivery option should either be eliminated or have a higher cost.


## Problem Statement
Data-co sales data indicate negative earning in some transactions which result in reduced overall earnings. Data exploration, finding and solving bottlenecks can increase the earnings per order. I also believe that finding seasonal patterns  on sales will help in optimizing inventory and increasing sales.

## Data Source
Kaggle: https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis/data

## Data Description
* rows: 180519 rows
* columns:53
  The columns description are attached in the data file.
  
## Methodology
**Cleaning and Processing**
* $\color{blue}{\text{print(f"Missing values:\n{df.isnull().sum()}")}}$ was used to look for missing data, columns 2 columns with >15000 nulls were dropped were dropped using $\color{blue}{\text{df.drop(['Order Zipcode','Product Description'], axis=1)}}$.
* PII columns were dropped using $\color{blue}{\text{df.drop(['Customer Email','Customer Fname','Customer Lname','Customer Password',
            'Product Status','Order Item Id','Product Image'], axis=1)}}$
* $\color{blue}{\text{df.dropna()}}$ was used to drop rows with missing data which are only 3.
* $\color{blue}{\text{print(f"\nDuplicate rows: {df.duplicated().sum()}")}}$ returned 0 duplicated rows.
* Similar columns were compared and 5 duplicated rows were dropped e.g $\color{blue}{\text{df['Benefit per order'].equals(df['Order Profit Per Order'])}}$ returns true so one of the columns was dropped.
* True date colums, "order date (DateOrders)" and "shipping date (DateOrders)"  were converted to datetime format.
* String format was assigned to categorical columns appropriately i.e. "Late_delivery_risk","Category Id","Customer Id","Customer Zipcode","Department Id",
"Order Id","Order Item Cardprod Id"
* New features were created for month, quarter and year using $\color{blue}{\text{df['year']=df["order date (DateOrders)"].dt.year;
 df['quarter']=df["order date (DateOrders)"].dt.quarter; df['month']=df["order date(DateOrders)"].dt.month}}$
* The column shipping_variance was created were negative value indicate ealier shipment, using
$\color{blue}{\text{df['shipping variance']= df["Days for shipping (real)"]-df["Days for shipment (scheduled)"]}}$
* order_shipping_lag column was created using
 $\color{blue}{\text{df['order shipping lag']= (df["shipping date (DateOrders)"]-df["order date (DateOrders)"]).dt.days}}$
* A boolean profited column was created by
 $\color{blue}{\text{df["profited"]= df["Order Profit Per Order"]>0}}$
  
**Analysis Insights**
* Average profit per order is aprox. 22, minimum was -4275 and maximu profit was 912, indicating that the overall orders are profitable but can be improved. At 95% confidence interval the Computer category show the highest possible profitability followed by Strength Training and, Basketball, while the categories with negative profits ranked from most negative to least negative profit per order were Strength Training, Basketball, As Seen on  TV! and  Men's Clothing. Most sold categories in descending order are Computers, Strength Training, Garden, Crafts, and Basketball.
* Over 54% of the orders were delivered later than scheduled and have 100% late delivery risk exposure. Orders with 100% delivery risk are less profitable. Late delivered and cancelled orders are less profitable than orders that were delivered on time or advanced but there is no impact on sales. Although a linear model does not perfectly capture  the behaviour of the data, at 95% confidence interval there is negative correlation between shipping variance and order-shipping lag with profit per order indication more profit on orders that were shipped with less delay and delivered earlier than scheduled.
* First class shipment orders are more profitable followed by standard then second class while same day shipping is less profitable.
* Sales are majorly on products with price less than 500 with majority of the profit in the range of -1500 to 1000, a positive correlation was seen between sales and profit per order. 
* Sales are mostly evenly distributed in 2015 and 2016 with a slight drop in february, june, november and december, Q1-Q3 of 2017 had slightly more sales than previous years but Q4 of 2017 saw about 50% drop in sales compared to the previous years
* Selling to consumers and coporate customers is slightly more profitable than to home offices, and the Technology department is the most profitable with the highest sales while the Book shop is the least profitable with least sales. 
  
## Recommendations
* To increase profits categories with high demand and high chance of loss like Strength training and basketball should be further investigated to reduce the standard deviation and ensure profit on sales, while categories with less demand and likelihood of loss can be eliminated.
* Orders shipment and delivery should be optimized to reduce lag, reduce order cancellation, and increase advance delivery.
* Same day delivery is less profitable and should either be eliminated altogether or increase its cost as it is a premium service.
* Sales are mostly on products less than 500, therefore to increase sales more costly items should have an option within the range if possible.
* The cause of the slight increase in Q1-Q3 2017  and the drop in Q4 of 2017 should be investigated thoroughly to mitigate the loss in revenue and avoid future losses.
* Marketing activities should be done to target more consumers and coporate customers, particularly within the Technology department.
