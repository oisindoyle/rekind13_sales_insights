# rekind13_sales_insights
Background info - Case Study : 'rekind13'
Rekind13 is an ecommerce store which specialises in the sale of refurbished iPhones. Rekind13 also offers an iPhone repair service which includes replacing cracked screens, internal batteries, cameras and internal parts. Rekind13 was founded at the start of the COVID-19 pandemic in March 2020 after a niche in the market was noticed by Oisin Doyle. Rekind13 has been a roaring success, starting off with simple screen repairs in the west of Ireland, rekind13 now has fifty customers who are based all over Europe and frequently use the services offered by Rekind13. Rekind13 has approached SpireDigita, a consulting company, to provide them with sales insights in order to help them make better data-driven decisions. 

# One - Define business objective
Rekin13 has contracted SpireDigita, a consulting company owned by Oisin Doyle, to derive sales insights from the data which they have collected since opening at the beginning of the COVID-19 pandemic in 2020. SpireDigita will provide analysis using the data from the csv files attached.

# Two - Source and clean the data 
The explosive growth of SpireDigita over the pandemic led to records of their sales transactions being slightly inconsistent. SpireDigita's first task was to ensure that the information they were given was in a format which was suitable for data modelling. The csv files were imported as tables in to MySQL workbench where the following steps were taken to ensure consistencies:

1) Import csv files as tables in to MySQL
2) Replace column headers that contain unicode characters with regular text as a string
3) Insert a column 'price'
4) Update the column sales_amount with the total of sales_quantity * price
5) Drop the column cy_date
6) As the salesamount was in euro, SpireDigita has to calculate the sale amount in USD. The currency rate at the time was 1.15 dollars to 1 euro so the formula : UPDATE salestransaction set usd_rate = (1.15+rand()*0.2);
7) This needed to be rounded to two decimal places where was used
FROM salestransaction; was used
8) Insert a column named norm_usd -> UPDATE salestransaction
SET norm_usd = usd_rate * sales_amount;
9) Insert a column 'product' to help easily segment the different iphone models by generation / 
ALTER table salestransaction
ADD COLUMN product varchar (9) NOT NULL;

SELECT * FROM salestransaction;

UPDATE salestransaction
SET product = 'iPhone 13'
WHERE product_code = 'P313' OR product_code = 'P312'/
10)


# Three Exploratory data analysis (EDA)
1) The transactions recorded were in Euro & GBP, it was decided that the sales transactions would be listed in USD.
2) Calculate the number of Euro & GBP transactions
3) Some transactions contained a -1 sale quantity, these outliers will need to be removed
4) SpireDigita was able to identify the region with the highest number of transactions by using the count function, this helps to ensure prioritise important regions for analysis
5) Identify which year where the majority of transactions have taken place
6) Join tables sales date & transactions together to view all information in one place

# Four Remove Outliers
Remove null transactions that have the sale_amount of -1 from sales
SELECT * FROM salestransaction WHERE sales_amount = -1;

This removed transactions from X X X X


# Five : ETL
After exploratory analysis was completed and outliers removed, the MySql database was inserted into PowerBi where data wrangling took place. This included the following modifications:

SalesCustomers
string - 
currency
double

SalesMarkets
add location data types


SalesProducts

SalesTransactions




# Six Create Models
Add a date table

Create star schema

Link the following columns 



# Seven Data Visualisation
After SpireDigita was satisified that the data they had gathered from rekind13 was ready for data visualisation, four dashboards were built.

1) Sales Insights
Includes the following:
- Year / Country Slicer
- Interactive Map
- Total Revenue by Country bar chart
- Top 5 Repair Sales Treemap
- Total Revenue card
- Year on Year Sales Growth card
- Total Sales Revenue by Quarter Line Graph
- Split of Sales Donut Chart
- 
3) Customer Segmentation
4) Repair Services Insights
5) Refurbished Phones Insights


# Eight Insights
SpireDigita then derived the following insights which were presented to rekind13 using a powerpoint and interactive dashboards to create an immersive experience.

# Nine Analysis
