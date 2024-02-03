
# AtliQ Hardware Sales Dashboard

## Dashboard Link : https://www.novypro.com/project/atliq-hardware---sales-insights-1 

### Problem Statement
𝗔𝘁𝗹𝗶𝗤 𝗛𝗮𝗿𝗱𝘄𝗮𝗿𝗲 is a company which supplies computer hardware and peripherals to many of their clients. And AtliQ Hardware has head office in delhi. They also have lot of regional offices throughout the India.
𝗕𝗵𝗮𝘃𝗶𝗻 𝗣𝗮𝘁𝗲𝗹 is the sales director in this company and he's facing lot of challenges. He is facing issues in terms of tracking the sales of AtliQ Hardware in this dynamically growing market.

🎯 So, as a data analytics team member, I need to provide the insights like revenue, sales quantity, profit, profit margin, top customers, top markets, revenue trend etc..to Bhavin Patel about his business.

Data Visualization: 𝗣𝗼𝘄𝗲𝗿 𝗕𝗜  
Database: 𝗠𝘆𝗦𝗤𝗟

### Steps Followed In SQL 

- Step 1 :  Loaded the sql dump file into MySQL Workbench.
- Step 2 :  Started analyzing the data to understand the basic and intermediate business problems.
- Step 3 : Identified solutions for business questions by running SQL queries against the database.

### Steps Followed In Power BI 

- Step 1 : Loaded the data into Power BI desktop using data source MySQL.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : Have some blank rows in transaction table, so cleaned those blank rows in that table.

- Step 5 : In Transactions table, i'm having INR and USD currency codes in currency column. So, converted all the currency code into INR.

- Step 6 : As part of my analysis, I need to get TOTAL REVENUE, so for that I did some calculation to create a Measure.
𝗥𝗲𝘃𝗲𝗻𝘂𝗲 = 𝗦𝗨𝗠('𝘀𝗮𝗹𝗲𝘀 𝘁𝗿𝗮𝗻𝘀𝗮𝗰𝘁𝗶𝗼𝗻𝘀'[𝘀𝗮𝗹𝗲𝘀_𝗮𝗺𝗼𝘂𝗻𝘁])

- Step 7 : Created "TOTAL SALES QUANTITY" Measure using below DAX formula.

𝗦𝗮𝗹𝗲𝘀 𝗤𝘁𝘆 = 𝗦𝗨𝗠('𝘀𝗮𝗹𝗲𝘀 𝘁𝗿𝗮𝗻𝘀𝗮𝗰𝘁𝗶𝗼𝗻𝘀'[𝘀𝗮𝗹𝗲𝘀_𝗾𝘁𝘆])

- Step 8 : Created "TOTAL PROFIT MARGIN" Measure using below DAX formula.

𝗧𝗼𝘁𝗮𝗹 𝗣𝗿𝗼𝗳𝗶𝘁 𝗠𝗮𝗿𝗴𝗶𝗻 = 𝗦𝗨𝗠('𝘀𝗮𝗹𝗲𝘀 𝘁𝗿𝗮𝗻𝘀𝗮𝗰𝘁𝗶𝗼𝗻𝘀'[𝗽𝗿𝗼𝗳𝗶𝘁_𝗺𝗮𝗿𝗴𝗶𝗻]) 

- Step 9 : Created "PROFIT MARGIN %" Measure using below DAX formula.

𝗣𝗿𝗼𝗳𝗶𝘁 𝗠𝗮𝗿𝗴𝗶𝗻 % = 𝗗𝗜𝗩𝗜𝗗𝗘([𝗧𝗼𝘁𝗮𝗹 𝗣𝗿𝗼𝗳𝗶𝘁 𝗠𝗮𝗿𝗴𝗶𝗻],[𝗥𝗲𝘃𝗲𝗻𝘂𝗲],𝟬) 

- Step 10 : Created "REVENUE CONTRIBUTION %" Measure using below DAX formula.

𝗥𝗲𝘃𝗲𝗻𝘂𝗲 𝗖𝗼𝗻𝘁𝗿𝗶𝗯𝘂𝘁𝗶𝗼𝗻 % = 𝗗𝗜𝗩𝗜𝗗𝗘([𝗥𝗲𝘃𝗲𝗻𝘂𝗲],𝗖𝗔𝗟𝗖𝗨𝗟𝗔𝗧𝗘([𝗥𝗲𝘃𝗲𝗻𝘂𝗲],𝗔𝗟𝗟('𝘀𝗮𝗹𝗲𝘀 𝗽𝗿𝗼𝗱𝘂𝗰𝘁𝘀'),𝗔𝗟𝗟('𝘀𝗮𝗹𝗲𝘀 𝗰𝘂𝘀𝘁𝗼𝗺𝗲𝗿𝘀'),𝗔𝗟𝗟('𝘀𝗮𝗹𝗲𝘀 𝗺𝗮𝗿𝗸𝗲𝘁𝘀'))) 

- Step 11 : Created "PROFIT MARGIN CONTRIBUTION %" Measure using below DAX formula.

𝗣𝗿𝗼𝗳𝗶𝘁 𝗠𝗮𝗿𝗴𝗶𝗻 𝗖𝗼𝗻𝘁𝗿𝗶𝗯𝘂𝘁𝗶𝗼𝗻 % = 𝗗𝗜𝗩𝗜𝗗𝗘([𝗧𝗼𝘁𝗮𝗹 𝗣𝗿𝗼𝗳𝗶𝘁 𝗠𝗮𝗿𝗴𝗶𝗻],𝗖𝗔𝗟𝗖𝗨𝗟𝗔𝗧𝗘([𝗧𝗼𝘁𝗮𝗹 𝗣𝗿𝗼𝗳𝗶𝘁 𝗠𝗮𝗿𝗴𝗶𝗻],𝗔𝗟𝗟('𝘀𝗮𝗹𝗲𝘀 𝗽𝗿𝗼𝗱𝘂𝗰𝘁𝘀'),𝗔𝗟𝗟('𝘀𝗮𝗹𝗲𝘀 𝗰𝘂𝘀𝘁𝗼𝗺𝗲𝗿𝘀'),𝗔𝗟𝗟('𝘀𝗮𝗹𝗲𝘀 𝗺𝗮𝗿𝗸𝗲𝘁𝘀'))) 

- Step 12 : After getting all the required columns and measures, started analyzing the data using different types of visualization charts.

## Snapshot of REVENUE Analysis report:

![revenue_analysis_powerbi_img](https://github.com/saikrishnatummidi/AtliQHardware_Sales-Analysis_Power-BI_Project/assets/108604409/a9c69df1-b1c2-43c4-92d3-6e4570431411)


## Snapshot of PROFIT Analysis report:

![profit_analysis_powerbi_img](https://github.com/saikrishnatummidi/AtliQHardware_Sales-Analysis_Power-BI_Project/assets/108604409/11beb7bd-adb8-4bdf-aa4a-6a724a89ba63)

### Below are some of the Insights Generated:-

- Total Revenue generated from 2017 to 2020 is "985 Million Rupees".
- Total Sales Quantity is "2 Million".
- Delhi NCR, Mumbai and Ahmedabad are the top 3 Markets in terms of REVENUE.
- Delhi NCR, Mumbai and Nagpur are the top 3 Markets in terms of highest Sales quantity.
- Brick Motor(75%) type of customers are performing well compared to E-Commerce(25%).
- Electricalsara stores, Electricalslytical, Excel stores, Premium Stores and Nixon are the top 5 stores generating highest Revenue.
- Delhi NCR, Mumbai and Ahmedabad are the top 3 markets in profit contribution to overall profit.
