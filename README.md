# HR_Analysis_for_Testraco_Ltd

## Table of Contents
- [Overview](#overview)
- [Tools](#tools)
- [Datasets](#datasets)
- [Data_Cleaning](#data_cleaning)

## Overview
Testraco Ltd., a multinational company, is experiencing challenges with employee retention, performance management, and workforce planning as it continues to grow. To address these challenges, the company is leveraging HR analytics to gain actionable insights into its workforce and improve HR processes and employee satisfaction. My task was to analyze the company’s employee training and workforce datasets to identify patterns, provide insights, and support data-driven decision-making.

##	Tools
- ### Microsoft Excel:
  Leveraged advanced Excel functionalities including formulas, conditional statements, and data visualization tools to clean, process, and analyze the data effectively.

##	Datasets
- ### Employee Data:
  Contained information on employee demographics, performance scores, employment status, and more.

- ### Training Data:
  Included details on employee participation in training programs.

## Data_Cleaning
To ensure the datasets were accurate, consistent, and ready for analysis, the following data cleaning steps were performed:
- ### Extracting First Names from Email Addresses:
  -	### Problem:
    Employee first names were not explicitly provided; instead, they were part of the email address format (firstname.lastname@bilearner.com).
  -	### Solution:
    Used Excel’s FIND and LEFT functions to extract first names.

- ### Generating the staff full name:
  -	### Problem:
    Needed to put together both first and last names.
  -	### Solution:
    Used Excel’s CONCAT function to extract to achieve the full names.
   	```r
    =CONCAT(T2," ",C2)
    ```

- ### Decoding Gender Codes:
  -	### Problem:
    Gender was represented as numeric codes (0 for Male and 1 for Female).
  -	### Solution:
    Added a new column to decode gender codes using the IF function.
   	```r
    =IF(M2=0, "Male","Female")
    ```

- ### Translating Performance Scores:
  -	### Problem:
    Employee performance scores were numeric (1, 2, 3) without clear labels.
  -	### Solution:
    Used the IF function to categorize scores as:
   	- 1: Needs Improvement
	  - 2: Fully Met
    - 3: Exceed
   	```r
    =IF(P3=1, "Exceed",IF(P3=2,"Fully Met","Needs Improvement"))
    ```

- ### Generating Promotion Remarks:
  -	### Problem:
    Needed to identify employees eligible for promotion based on specific criteria: 
   	- Employment type: Full-Time
    - Performance: Exceed
  -	### Solution:
    Created a new column “Promotion Remark” using the IF and AND functions.
   	```r
    =IF(AND(Q2="Exceed",H2="Full-Time"),"Promote","Under Review")
    ```

- ### Determining Employment Status:
  -	### Problem:
    Employees’ statuses were unclear; those with an end date were inactive, and others were active.
  -	### Solution:
    Added an “EmpStatus” column using the IF and ISBLANK functions.
   	```r
    =IF(ISBLANK(F2),"Active","Non-Active")
    ```

- ### Linking Training Data to Employee Data:
  -	### Problem:
    Insights required integration of employee data with training records.
  -	### Solution:
    Used VLOOKUP to merge relevant columns from the Employee Data into the Training Data.

##	Analysis and Insights
  With the cleaned and merged datasets, I created a dashboard to visualize key insights, enabling the management to make informed decisions:
### Key Insights
