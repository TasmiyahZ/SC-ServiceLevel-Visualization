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
2. **Insight 2**: The average Line Fill Rate for the company is 66%.
3. The details on which customers, products or cities are most affected can be viewed in the dashboard attached. The primary reason for customers not renewing their contracts with the company thus are driven from poor KPI of the company against targets.

