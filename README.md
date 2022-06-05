# hive-analytics-on-aws-for-e-commerce

## Prerequisites
Few things you need to have before starting the project:
- Basic understanding of AWS services and creation of an EC2 instance on AWS
- Good knowledge of Hive, Spark, SQL, shell scripting and working knowledge of Docker
- Strong understanding of databases, relational modeling and a zeal to learn :)  

<br />

## Project Motivation
The main motive behind the project is to understand performing Hive analysis in Docker containers running on an AWS EC2 instance. In process of doing so, you will learn about how to create an AWS EC2 instance, setting up docker containers on that instance, loading data from a local file to AWS using CLI, data transfer between relational databases and Hadoop HDFS using Sqoop, creating Hive data warehouse and performing data analysis using Hive queries.


<br />

## Dataset
To run any sort of analytics, we need **data**. The dataset that we will be using to perform Hive analysis in this project is [AdventureWorks](https://dataedo.com/samples/html/AdventureWorks/doc/AdventureWorks_2/home.html) dataset. AdventureWorks database supports standard online transaction processing scenarios for a fictitious bicycle manufacturer - Adventure Works Cycles. Various components of the database include Manufacturing, Sales, Purchasing, Product Management, Contact Management, and Human Resources.
The complete schema of the database can be found [here](part0dataset/AdvWorksOLTP_DB_Diagram.png).
We will be concentrating mainly on AdventureWorks Sales and Customer Demographics data in this project.

<br />

## Problem Statement
Perform data analysis on AdventureWorks Sales and Customer Demographics data in Hive and answer the following:
- find the upper and lower discount limits offered for any product
- find the top 10 customers with highest contribution to sales
- purchase pattern of customers based on gender, education, and salary
- identify high performing stores to plan the allocation of goods
- identify the age group of customers contributing to more sales
- identify the top performing territory based on sales
- find the territory-wise sales and their adherence to the sales quota

<br />

## Project Work
Below steps document the work done in order to solve the problem statement.
- Project Setup on AWS - Refer [here](part1projectsetuponaws/README.md)
- Creating Hive data warehouse - Refer [here](part2hivedatawarehouse/README.md)
- Performing Hive Analytics - Refer [here](part3hiveanalytics/README.md)