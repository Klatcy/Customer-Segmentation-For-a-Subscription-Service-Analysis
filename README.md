# LITA_CLASS-PROJECT
 # LITA_Project 2

### Project Title: : Customer Segmentation for a Subscription Service

[Introduction](#introduction)

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[About the Dataset](#about-the-dataset)

[Tools Used](#tools-used)

[Data Cleaning and Preparations](#data-cleaning-and-preparations)

[Exploratory Data Analysis (EDA)](#exploratory-data-analysis)

[Data Analysis](#data-analysis)

[Data Visualization](#data-visualization)
  
---
### Introduction
 The world of business thrives on data-driven decisions, and the ability to harness the power of data is essential. In this project, i embark on an exciting journey to analyze customer data to uncover trends, and reveal valuable insights that will drive strategic decision-making.
 
 --- 
### Project Overview
This Data Analysis aims at generating insight into the customer segmentation for a subscription service over the past years. In analyzing the customer data, i seek to extract necessary information from the dataset, to provide valuable insights that can guide decision-making process across various aspects of the business. These insights include the identification of totalnumber of customers from each region, find subscription pattern, top 3 region by subscription cancellations, most popular subscription type of the number of customers among others. This will enable us to tell compelling stories around the data from the insight gotten, to enable the business make informed decisions to optimize operations, enhance marketing efforts, and maximize revenue.

---
 ###  Data Sources
The primary source of the Data used here is Sales Data.Csv. This is an open source data that an be freely downloaded from an open source online such as kaggle or any other data repository site.
 
---
### About the Dataset
The dataset has sales data from January 2022 to 2024. It consists originally of 8 columns which was modified further for the purpose of the analysis.

- CustomerName: Unique identifier of each customer name

- CustomerID: Unique identifier of each customer

- Region : Region of each customers

- SubscriptionType: Type of Subscription made by each customer
 
- SubscriptionStart: Day each customers subscribed started

- SubscriptionEnd: Day each customers subscription ends
  
- Cancellation:
  
- Revenue: Revenue generated from subscription by each customers

- Subscription Pattern:
  
---
### Tools Used
- Microsoft Excel {Download Here}{https://www.microsoft.com}
  1. For Data Cleaning, 
  2. For Analysis
  3. For Data Visualization

 - Structured Query Language {SQL] for Quering of Data
  
- PowerBI for Dynamic and Interactive Data Visualization.

- GitHub for Portfolio Building

---
### Data Cleaning and Preparations.
In the initial phase of the Data cleaning and preparations, the following actions were performed; 
 1. Data Loading and Inspection
 2. Handling Missing Variables
 3. Data Cleaning and Formatting

---
### Exploratory Data Analysis (EDA)
EDA involved the exploration of Data to answer some questions about the Data in order to gain insights. Some of the questions include;

- What is the total number of customers from each region?
- What is the most popular subscription type?
- What is the average subscription duration?
- What is the total revenue by subscription type?

---
### Data Analysis
This is where i include some basic lines of code or queries or even some of the DAX functions used during the analysis.These include
1. SQL
```SQL
SELECT* FROM [dbo].[ Customer Data]
```
- TO RETRIEVE TOTAL NUMBER OF CUSTOMERS FROM EACH REGION
```SQL
SELECT Region,COUNT (CustomerID) AS Total_Number_of_Customer FROM [dbo].[ Customer Data]
GROUP BY Region
```
 - TO FIND THE MOST POPULAR SUBSCRIPTION TYPE BY NUMBER OF CUSTOMERS
```SQL
SELECT SubscriptionType, COUNT (CustomerID) As Number_of_Customers FROM [dbo].[ Customer Data]
GROUP BY SubscriptionType
```
- TO FIND CUSTOMERS WHO CANCELED THEIR SUBSCRIPTION WITHIN 6 MONTHS
```SQL
SELECT CustomerName, Canceled,SubscriptionStart FROM[dbo].[ Customer Data]
WHERE Canceled= 0 AND MONTH (SubscriptionStart) Between 1 AND 6
```
- TO CALACULATE AVERAGE SUBSCRIPTION DURATION FOR ALL CUSTOMERS
```SQL
SELECT COUNT (CustomerID) As All_Customers, AVG(DATEDIFF(DAY,SubscriptionStart,SubscriptionEnd))
AS Average_Subscription_Duration FROM [dbo].[ Customer Data]
WHERE SubscriptionEnd is not Null
```
- TO FIND CUSTOMERS WITH SUBSCRIPTION LONGER THAN 12 MONTHS
```SQL
SELECT CustomerName,SubscriptionType,SubscriptionStart,SubscriptionEnd FROM [dbo].[ Customer Data]
WHERE DATEDIFF(MONTH, SubscriptionStart,SubscriptionEnd) >=12
```
- TO CALCULATE TOTAL REVENUE BY SUBSCRIPTION TYPE
```SQL
SELECT SubscriptionType, SUM (Revenue) AS Total_Revenue FROM [dbo].[ Customer Data]
GROUP BY SubscriptionType
```
- TO FIND TOP 3 REGION BY SUBSCRIPTION CANCELLATION
```SQL
SELECT TOP 3 Region, Canceled FROM [dbo].[ Customer Data]
```
- TO FIND TOTAL NUMBER OF ACTIVE AND CANCELED SUBSCRIPTIONS
```SQL
SELECT SUM (Case When Canceled =0 Then 1  Else 0 End) As ActiveSubscriptions,
SUM (Case When Canceled = 1 Then 1 Else 0 End) As CanceledSubscriptions
from [dbo].[ Customer Data]
GROUP BY CustomerID
```

2. PowerBI
   -
   
--- 
### Data Visualization
















