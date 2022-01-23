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
    
     
