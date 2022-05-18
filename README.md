# rekind13_sales_insights
Background info : Case Study : 'rekind13'
Rekind13 is an ecommerce store which specialises in the sale of refurbished iPhones. Rekind13 also offers an iPhone repair service. Replacing cracked screens, internal batteries, cameras and internal parts. Rekind13 was founded at the start of the COVID-19 pandemic in March 2020 after a niche in the market was noticed by Oisin. Rekind13 has been a roaring success, starting off with a simple screen repair in the west of Ireland, rekind13 now has fifty customers who are based all over Europe. Rekind13 has approached SpireDigita, a consulting company, to provide them with sales insights in order to help them make better data driven decisions. 

# One - Define business objective
Rekin13 has contracted SpireDigita to derive sales insights from the data which they have collected since opening at the start of the pandemic in 2019. SpireDigita will use data from the following csv files : x x x x x x x

# Two - Source and clean the data 
The explosive growth of SpireDigita over the pandemic led to records of their transactions being slightly inconsistent. SpireDigita's first task was to ensure that the information they were given was in a readable format.

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


# Four Remove Outliers
Remove null transactions that have the sale_amount of -1 from sales
SELECT * FROM salestransaction WHERE sales_amount = -1;

This removed transactions from X X X X


# Five : ETL
SpireDigita were provided with six CSV files which included data on Customers, Sales Transactions, Sales Markets, Sales Products and Sales Date. Upon first glance, SpireDigita noticed a number of issues with the data provided.

a) Currency
b) Databases not linked
c) 


# Six Create Models

# Seven Data Visualisation

# Eight Insights

# Nine Analysis
