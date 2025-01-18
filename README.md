# Supply Chain Service Level Visualization 

## Overview  
Understanding Customer Service Levels through various parameters using PowerBI and DAX

**Problem Statement** Customers at AtliQ Mart are not renewing contracts, since the company has not been tracking their service levels, as a DA we need to analyze what might be going wrong and highlight some rights too.

**Goals** Calculate various KPI's to understand current performance vs. targets.

## Dataset  
- **Dataset source** The dataset was part of codebasics resume challenge
  https://codebasics.io/challenge/codebasics-resume-project-challenge
- **Dataset Contains** 3 dim tables and 2 facts tables    
-  **Tools/technologies used** Power BI, DAX, PowerQuery 

## Workflow  
### Step 1: [Data Cleaning/Preparation]  
- Basic data cleaning and preparation handled in PowerBI Powerquery  
### Step 2: [Data Modelling]  
- Connected various dim and facts tables through 1:1 or 1:Many relationship
### Step 3: [Measures table and Key Dax Calculations]
![image](https://github.com/user-attachments/assets/beb0587f-d23c-42fd-b062-654ebe4a283e)


*for example*
--In Full: Measures the % shipments shipped in full
--Ontime In Full OTIF% : Measures shipments shipped on time and in full
--VOFR: Measures the total volume shipped vs total ordered volume

```
IF% = CALCULATE(count(fact_orders_aggregate[order_id]),fact_orders_aggregate[in_full]=1)/COUNT(fact_orders_aggregate[order_id])*100
```
```
OTIF % = CALCULATE(count(fact_orders_aggregate[order_id]),fact_orders_aggregate[otif]=1)/COUNT(fact_orders_aggregate[order_id])*100
``` 




## Key Findings  
1. **Insight 1**:  The company's overall Ontime In Full is @ 29% vs the target of 66%
2. **Insight 2**: The average Line Fill Rate for the company is 66% that shows potential 
3. **Additional Insights//Outcomes**

Line Fill Rate (LIFR%) and Volume Fill Rate (VOFR%): Products like "AM Biscuits 750" and "AM Milk 500" have higher LIFR% and VOFR%, indicating better fulfillment efficiency. For low LIFR% products (e.g., "AM Tea 100"), stocking or production bottlenecks could be investigated.

Short Ship% : Dairy's high short-ship quantity suggests supply issues or higher demand than available inventory.The company should prioritize optimizing the dairy supply chain and review its demand forecasts.

Customer Highlights: Prioritize addressing fulfillment issues for key customers like "Coolblue" and "Acclaimed Stores" to prevent further churn. Analyze delivery routes, order volumes, and demand variability for these customers.

City Highlights: Ahmedabad and Vadodara should be prioritized for logistical improvements.Investigate warehouse distribution or transit times causing delays in these regions.

**Outcomes**
Several correlated factors show reasons for customer drop out rate. Consistent poor performance on KPI's over six months show systematic supply chain inefficiencies and need thorough review. 


