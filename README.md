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
1. **Insight 1**: Brief explanation.  
2. **Insight 2**: Brief explanation.  

## Dashboard Preview  
Include screenshot links to dashboards, graphs, or other outputs.

## How to Use (Optional)  
Instructions for replicating your analysis or accessing files.

















-

This repository contains:  
- **CSV Files** for raw datasets
- **Power BI dashboard** for supply chain analysis.  

## Key Features  
- Interactive charts to understand service levels  
- Pivot tables for quick data slicing.

## File Descriptions   
- **Atliq Supply Chain.pbix**: Power BI dashboard with visuals for service level analysis.  

## Screenshots  

