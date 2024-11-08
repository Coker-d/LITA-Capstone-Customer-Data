# LITA-Capstone-Customer-Data

---

## Project Title: Sales Performance Analysis for a retail Store
---
[Project Overview](#project-overview)

[Data Source](#data-source)

[Tools Used](#tools-used)

[Data cleaniing and preparation](#data-cleaniing-and-preparation)

[Exploratory Data Analysis](#exploratory-data-analysis)

 [Data Analysis](#data-analysis)

[Excel Analysis](#excel-analysis)

[SQL Analysis](sQL-analysis)

[Power BI Analysis](power-bi-analysis) 

 ---
 


### Project Overview
---
This Data aims at which enables me to tell a compelling story around this data from the iinsight gotten and to know best performance from the given Data as well as find insight within organizational Data

### Data Source
---
The primary source of Data used here is Sales Data xlsl and this is an open Data Source available for all the ladies in tech Afica to carry out their Final Examination. This is my Final Examination with Ladies in Tech Africa (Question 1)

### Tools Used
---
- Microsoft Excel [Download Here](https://www.microsoft.com)
  1. for Data Cleaning,
  2. for Analysis
  3. for Visualization
     
- SQL - Structureed Query Lanquage  
  1. Storind and processing Data in a related Database
  2. Querring of Data
  
- Github for Portfolio Building
  1. Store Share and work with others to write codes
  2. Show case work done
    
- Power BI [Download Here](https://www.microsoft.com)
  1.  Data Visualization
  2. Connect diparate Data Set
  3. find insight within given Data

### Data cleaniing and preparations
---
To start with the Data cleaning, the following were carried out
  1.  Data importing and Inspection
  2.  Data cleaning and formatting
  3.  Data Validation
  4.  Removal of duplicates

### Exploratory Data Analysis
---
this aspect involves digging deep into our data to answer questiions around our data such as
 
  1. Total Numbers of customers from each region
  2. Most Popular Customer subscription
  3. Customers who cancelled their subscrription within 6 months
  4. Average subscription duration of all Customers
  5. Customers with subscription longer than 12 Months
  6. Total Revenue by subsccription type
  7. Top3 Regions by subscription cancellation
  8. Total number of active and canceled subscription

### Data Analysis
---
The basic lines of codes, querries and DAX expression used during this analysis
```SQL
SELECT * From  table SalesData
GROUP By Region
ORDER BY Sales DESC
```
```Excel
=SUMIF(D2:D2233, K2: K2233)
```
---
## Excel Analysis

This is an analytical spread sheet used for budgetting especially storing and analyzing large
amouunt of Data for financial analysis
![Customer Data Excel](https://github.com/user-attachments/assets/fce124a6-2f53-4a63-9e0e-7b1816![Pivot Excel CD](https://github.com/user-attachments/assets/a41ef71c-3814-48ed-82b4-1f2421e852c8)
63b4c2)

![Chart Customer Data](https://github.com/user-attachments/assets/1dc81322-df9a-42f6-997a-e9e7bf862b36)



#### Analysis of Customer Data using Pivot Table to find subscription patterns 
The various customer Data Are shown below
![Uploading Pivot Customer Data.JPG…]()



#### The Total Revenue
This is the total amount generated from different subscriptiion type which stood as  N 67,540,175 

#### Calculation of average subscription duratipon
This is the average number of days taken for customer to subscribe which is 164.5876667 
Approximately 165 days
![Average Sub Period](https://github.com/user-attachments/assets/c01d0359-a93a-4c36-8cb6-21f3fadc82e6)


#### other analysis created 
![Uploading Chart Customer Data.JPG…]()


## SQL Analysis
---
Due to large volume of thhe file, the Data used for this analysis was converteed to csv delimiter / Flat File to accomodate the data set (Previously in Excel Format i.e .Xlsl)

All basic activities carrried out in the customer segmentation for subsription Service were kept on the Database using SQl.
The following inferences were made using the Schema below:
|Customer ID|CustomerName|Region|SubscriptionType|SuscriptionStart|SubscriptionEnd|Canceled|
|-----------|------------| -----|----------------|----------------|---------------|--------| 
|    204    |   Maria    | West |    Standard    |   30-4-2022    |   30-4-2023   |  FALSE | 


### Total Numbers of customers from each region
Here we want to know the total numbers of customers from Nort,East, South and west.
```SQL
Select Region,Count(CustomerId) as NoOfCustomers from [dbo].[Customer Capstone] Group by Region
```
![Customers by Region](https://github.com/user-attachments/assets/e6281ffe-b18e-4aff-aacb-4dbbc0066d53)
#### Conclusion
There are 8488 Customers from the East. Which may be attributable to the Lifestyle of the people leaving in the geographical Location 

### Most Popular Customer subscription
The package which majority of the customers Subscribe to is the Basic package with 1,692 Subscribers.
```SQL
Select SubscriptionType, COUNT(CustomerId) as MostPopularsubscription from [dbo].[Customer Capstone] Group by SubscriptionType 
Order by MostPopularsubscription Desc
```
![MostPopular Sub](https://github.com/user-attachments/assets/31593dcc-d756-4aa9-bba2-c39cc3bad689)
#### Conclusion
The Basic sbscription has most of the subscribers because its the cheapest among the packages.

### Customers who cancelled their subscrription within 6 months

### Average subscription duration of all Customers

### Customers with subscription longer than 12 Months

### Total Revenue by subsccription type
we want to know how much each Package is Generating inthe period under review
```SQL
Select SubscriptionType, Sum(Revenue) as TotalRevenue from [dbo].[Customer Capstone]
Group by SubscriptionType Order by TotalRevenue Desc
```
![Revenue by Sub type](https://github.com/user-attachments/assets/122103bd-ac8d-4631-ba2f-00d3f50379a9)
#### Conclusion
A total sum of N33,776,735 is being Generated from Basic Subscription Type 
This infers that Majority of the Customer enjoy the value they derived from the Package.

### Top3 Regions by subscription cancellation
WE want to know the first to third regions that are performing well in terms of sales which regions 
```SQL
Select Top 3 Region As Top3Region, COUNT(Canceled) as CanceledSubscription from [dbo].[Customer Capstone] Group by region
Order by CanceledSubscription Desc
```
![Top3 by Cancelation](https://github.com/user-attachments/assets/f811759c-6ce4-4ba8-bbff-127db02b849e)

#### Conclusion
The order of Cancelattion is East South and North with number of cancelattion to be 8,488 , 8,466 and 8,433 respectively


### Total number of active and canceled subscription
Not all orders are paid for! we want to know why some are cancellled
```SQL
Select Canceled,Count(CustomerId) as NoOfCustomers from [dbo].[Customer Capstone] Group by Canceled
```
![Uploading active and Passive.JPG…]()
#### Conclusion
A larger percentage of all boookings are cancelled at the end of the day with 18,612 orders cancelled and 15,175 orders active. Cancellation might be as a result of bad network in the Location which reverse transactions made making sbscription to be Cancelled


## Power BI Analysis 
---
This analysis was carried out with the use of a key tool called Slicer for interactive activities

#### Power BI Dashboard
Below is the Dashboard of the of the Customer Data
![Uploading Customer Data Power BI.JPG…]()


#### Key Customer Segment

#### Cancelation

#### Susription Trend




