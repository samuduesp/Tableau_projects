# Tableau sales insights project 1

Atliq hardware company which is supply hardwares to shop. They have regional shops. There are salas decline recently so they need get clear insights about current situation in business.
Goal- make Tableau dashboard and find real time data analysis.
.
## Aim Grid & project planning

purpose - Finding real time data insights
Stake holders- Sales team, It team, Data analysis team
End result - Funtioning working dashboard
Success criteria- !0% increassing sales

## Using SQL for simple analysis

Using SQL get aggregation data.

## ETL process
### Connect to database through tableau

 Create star schema accordding to relationship(Extract whenever your want)
   fact table- transaction table
   diamention table - customer table
                      date table
                      Market table
                      product table
cleaning data 
There is a negative price values in sales price so filtering negative values.
      Sales 
      go to data > Edit data source filters > change range 1- xxxx
There is a market codes which have null values 
      Remove, old , invalid value after discuss with regional manager.
      data > Edit the source
Normalize currency because currencey has USD values. 
      click arrow in the column and name name coloumn as normalize value
      formula
      IF [Currecy] == "USD" THEN [Sales Amount] * 74 ELSE [Sales Amount] END


## Dashboard
 
Individually build component and finally make dashboard,
  make sheet- 
     Revenue
     Quality
     Revenue by market > label them> change colur > middle
     Top five customers
     Top five products
There is different format to change structure of data. 
Testing Dashboard verificate

## Tableu transport to manager
    Export as powerpoint
    Publish tablaeu online

## Building version 2 dashboard according to Manegement feedback.
    
     
## Sales Insights Data Analysis Project

### Instructions to setup mysql on your local computer

1. SQL database dump is in db_dump.sql file above. Download `db_dump.sql` file to your local computer and import it.

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`