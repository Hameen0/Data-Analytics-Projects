# BIKE SALES ANALYSIS
## Summary
Anlysis of bike sales dataset containing the characteristics of customers was carried out with Microsoft-excel, pivot tables, visualizations and filtering
were utilized to derive insights. The data indicated that middle aged costomers and professional workers buy more bikes, while income influence the buying of single males and not females. Marriage and children reduce the buying power of customers also commute distance have a milder effect. In conclusion different marketing strategies will have to be adopted for different groups for effiecient customer conversion.
## Problem Statement
Which customer demographics should be targeted customers for future marketing activities?
## Data Source
Kaggle: https://www.kaggle.com/datasets/chiomabridgetnwankwo/bike-buyers
## Data Description
* rows: 1026
* columns:13\
ID: Numerical  
Martial Status: Categorical (M, S).  
Gender: Categorical (M, F).  
Income: Numerical.  
Children: Numerical.  
Education: Categorical (Bachelors, Partial College, High School, Partial High School, Graduate Degree).  
Occupation: Categorical (Skilled Manual, Clerical, Professional, Management, Manual).  
Home Owner: Categorical (Yes, No).  
Cars: Numerical.  
Commute Distance: Categorical (0-1 Miles, 1-2 Miles, 2-5 Miles, 5-10 Miles, More than 10 Miles).  
Region: Categorical (Europe, Pacific, North America).  
Age: Numerical.  
Purchased Bike: Categorical (Yes, No).
## Methodology
**Cleaning and Processing**
* Find function was used to look for missing data retuns none.
* Conditional formatting was used on ID column to find 26 duplicated rows, then removed.
* Formats of all columns was assigned appropriately
* The dataset was converted to a table
* A new Age bracket column was created using (=IFS([@Age]>54,"Old",[@Age]>=31,"Middle Age",[@Age]<31,"Adolescent")
  
**Analysis Insights**
* Average income of male customers is higher than that of female customers by ~ 6%, while for each gender average income of married customers is greater than that of single customers by ~9%.
* Male Single customers with higher income buy more while income have less effect on single females. Single customers that buy bikes have an average income of ~$56000 ( ~$59k males & ~$53k for females) while does that do not buy earn an average of ~$51000 ( ~$50k males & ~52k for females)
* For married customers income have more impact on  females buying than on males.
* About 37% of customers have commute distance of 0-1miles of which over 54% buy the bike. For longer commute distance the percent of buyers falls as distance increase reaching less than 30% for those have more than 100 miles commute.
* Majority of customers ~70% are Middle aged (31-54years) of which ~55% buy, while ~10% are younger than 31years (35% buy) and ~20% are older than 54years (31% buy).
* Professional workers buy more bike compared to other workers.
* Number of Customers reduce with increase in number of children. And probability of buying reduce with increase in children
## Recommendations
* Middle aged customers should be targeted for more efficient marketing.
* Those that have short commute and are single can be targeted with enjoying freedom themed strategy.
* Sales discount event can be done to target married customers and single males while freedom themed marketing event can be done to target single females.
