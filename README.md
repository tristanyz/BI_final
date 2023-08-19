#Power BI final project--Yizhou Zhang
In this Project I created two visuals to show the most popular item per zipcode and the percentage of sales per store in the period between 2016-2019.

#step1
Creating the database and dataset in SSMS, connect to POWER BI

#step2
User Power Query Editor to change the data type for some columns, note that 'store_location' has empty values but has no influence on our project

#step3
Create measures:
Sale_amt = SUM(finance_liquor_sales[bottles_sold]) %%this is used to calculate the total sales and also for the use of the following measure

RankMeasure = RANKX(ALL(finance_liquor_sales[item_description]),[Sale_amt]) %% use this to rank the sales of each item, similar to topN

Store Sales Percentage = DIVIDE(finance_liquor_sales[Sale_amt], CALCULATE([Sale_amt], All(finance_liquor_sales[store_number]))) %%calculated the percentage of each store's sales

#result
![image](https://github.com/tristanyz/BI_final/assets/139252513/aac72a18-4e07-4a6e-8a31-fdecb4d912e2)


