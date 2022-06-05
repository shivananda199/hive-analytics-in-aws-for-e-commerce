# e-commerce-data-warehouse-in-hive

## Prerequisites
Few things you need to have before starting the project:
- Basic understanding of AWS services and creation of an EC2 instance on AWS
- Good knowledge of Hive, Spark, SQL, shell scripting and working knowledge of Docker
- Strong understanding of databases, relational modeling and a zeal to learn :)  

<br />

## Motivation
The main motive behind the project is to understand performing Hive analysis in Docker containers hosted on an AWS EC2 instance.  

<br />

## Dataset
To run any sort of analytics, we need **data**. The dataset that we will be using to perform Hive analysis in this project is [AdventureWorks](https://dataedo.com/samples/html/AdventureWorks/doc/AdventureWorks_2/home.html) dataset. AdventureWorks database supports standard online transaction processing scenarios for a fictitious bicycle manufacturer - Adventure Works Cycles. Various components of the database include Manufacturing, Sales, Purchasing, Product Management, Contact Management, and Human Resources.
The complete schema of the database can be found [here](dataset/AdvWorksOLTP_DB_Diagram.png).  

<br />

## Problem Statement
Perform data analysis on AdventureWorks dataset in Hive and help business understand the following:
- find the upper and lower discount limits offered for any product
- find the top 10 customers with highest contribution to sales
- purchase pattern of customers based on gender, education, and salary
- identify high performing stores to plan the allocation of goods
- identify the age group of customers contributing to more sales
- identify the top performing territory based on sales
- find the territory-wise sales and their adherence to the sales quota

<br />

