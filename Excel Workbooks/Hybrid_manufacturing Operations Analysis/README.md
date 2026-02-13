# HYBRID MANUFACTURING OPERATIONS ANALYSIS
## Summary
Anlysis of manufacturing dataset containing information on machines, operations, material, time and energy consumption was carried out with Microsoft-excel. Pivot tables, and visualizations were utilized to derive insights. The analysis indicated M01 as the most economical machine with highest completion rate, least low efficient operation, time and material consumption, and low energy consumption. Proper planning should be done to minimize delays which will increase completion rate, machine availability and efficiency particularly on M03 and M04.

## Data Source
Kaggle: https://www.kaggle.com/datasets/ziya07/manufacturing-production-data
## Data Description
This dataset captures production planning and optimization data from Hybrid Manufacturing Systems (HMS), which integrate additive and subtractive manufacturing processes. It includes detailed records of machine operations, material usage, processing time, energy consumption, and scheduling data to facilitate efficient resource allocation and decision-making.

The dataset also introduces a categorical target variable (Optimization_Category), which classifies production efficiency into four levels:
Low Efficiency (0-40) → High delays, failures. Moderate Efficiency (41-70) → Acceptable but suboptimal. High Efficiency (71-90) → Well-optimized but with minor inefficiencies. Optimal Efficiency (91-100) → Best-case scenario, minimal delays.

* rows: 1000
* columns:13\
Job_ID: unique id for each row\
Machine_ID: five machines were used (M01,M02...,M05)\
Operation_Type: (Grinding, Milling, Lathe, Drilling and Additive)\
Material_Used: Numerical (float)\
Processing_Time: Numerical (Integers)\
Energy_Consumption: Numerical (float)\
Machine_Availability: Numerical (Integers)\
Scheduled_Start: DateTime\
Scheduled_End: DateTime\
Actual_Start: DateTime\
Actual_End: DateTime\
Job_Status: Completed, Delayed and Failed\
Optimization_Category: Low Efficiency, Moderate Efficiency, High Efficiency, Optimal Efficiency\

## Methodology
**Cleaning and Processing**
* Find function was used to look for missing data retuns 258 cells, these are the Actual_Start and Actual_End data for 129 rows of which Job_Status = Failed.
* Conditional formatting was used on Job_ID column , 0 duplicated rows were found.
* Formats of all columns was assigned appropriately for datetime, categorical and numeric culumns.
* The dataset was converted to a table
* Job_ID column was dropped, Quality and Defect rate columns were created using VLOOKUP to match to the table below
  Completed	Good	0
Delayed	Good	0
Failed	Defect	100
<img width="241" height="73" alt="image" src="https://github.com/user-attachments/assets/5bd62167-ca80-481d-8809-27638fa638b7" />

* Pivot tables were created to visulaize data and generate insights

**Analysis Insights**
* M02 had the lowest falure rate followed by M01 and M05. M01 have a 72% completion rate, 17% delay and 11% failure rate, M02 have a 70% completion rate, 20% delay and 10% failure rate, M05 have a 64% completion rate, 25% delay and 11% failure rate while M03 16% failure rate and M04 18%.
* M02 had the least energy consumption of 8.4 followed by M01, M04 and M05 having 8.5 and finally M03 having 8.8. M02 had the highest time consumption of 74 and above average material consumption of 3.09 M05 had the highest material consumption of 3.13 and average time consumption of 7.1. M01 had the least material and time consumption of 2.88 and 70 respectively.
* M01 had the least low efficiency of 60% compared to other machines, M02, M03 and M04 have 65% while M05 has 70%. All machines have extremely low optimal efficiency rate while M04 had 2%, M05 1%, M01 and M02 less than 1%. The operations that achieve optimal efficiency albeit low were additive and milling, with M01, M02 and M04 having milling optimal ang M04 and M05 having additive optimal operation.
* M04 has the highest availabity on additive of 90%, M01 is the best for drilling at 90% while M03 had the highest overall availability 89.4%.
  
## Recommendations
* Proper planning should be done to minimize delays which will increase completion rate, machine availability and efficiency.
* M01, M02 and M05 shows shows lesser failure rate and energy consumption, while M01 had the lease time and material consumption therefore M01 should be considered as the most economical machine.
* M04 have the capacity of optimal operation on both additive and substractive manufacturing methods. Reducing delays and failure will reduce low efficiency operations on M03 and M04 allowing them to compete with M01.
* M03 had the highest availability making it the most ideal for smooth operation, however it had 0 optimum operation.

