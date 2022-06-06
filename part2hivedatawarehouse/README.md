# Hive Data Warehouse

After completion of [project setup in AWS](../part1projectsetupinaws), you must be familiar with connecting to AWS EC2 instance and entering different containers hosted on the instance. Now, we need to create a Hive data warehouse in Hadoop containing the data required for performing analytics. Below steps explains how to do so. Out of the 71 tables present in AdventureWorks dataset, we will concentrating on 9 tables in this project to perform our analysis. 

### 1. Load data to MySQL database in AWS
File [```01_partial_dataset_creation.sql```](/part2hivedatawarehouse/01_partial_dataset_creation.sql) contains the queries needed to create the required tables and load data into them in MySQL database. File [```02_views_creation.sql```](/part2hivedatawarehouse/02_views_creation.sql) contains the queries to create the required the views needed to perform data analysis. We need to run these SQL scripts in mysql prompt on AWS to have the data loaded. Steps below:
- Run the below command in your local terminal to copy SQL scripts from your machine to EC2 instance:
```
$ scp -r -i "hive_docker_setup.pem" 01_partial_dataset_creation.sql ec2-user@my-aws-ip-dns-hostname:/home/ec2-user/

$ scp -r -i "hive_docker_setup.pem" 02_views_creation.sql ec2-user@my-aws-ip-dns-hostname:/home/ec2-user/
```
- Copy SQL scripts from EC2 home directory to MySQL container
```
$ docker cp 01_partial_dataset_creation.sql ra_mysql:/var/lib/mysql/01_partial_dataset_creation.sql

$ docker cp 02_views_creation.sql ra_mysql:/var/lib/mysql/01_partial_dataset_creation.sql
```
- enter MySQl prompt by following the steps [here](../part1projectsetupinaws/README.md#61-accessing-mysql-and-hive-prompt) and run the below commands to create MySQL tables and views and load data into them:
```
mysql> source 01_partial_dataset_creation.sql;

mysql> source 02_views_creation.sql;
```

<br />

### 2. Transfer data from MySQL to Hadoop
This step is a data transfer from MySQL (relational database) to Hadoop (non-relational database). We will use [Apache Sqoop](https://sqoop.apache.org/) to achieve this. File [```03_sqoop_import.sql```](/part2hivedatawarehouse/03_sqoop_import.sh) contains the required commands. Enter the sqoop container on AWS and run the commands in the file one after the other.

Entering sqoop container:
```
$ docker exec -it ra_sqoop bash
```
After running the commands, we will have the data in Hadoop in target directories mentioned in the sqoop commands.

<br />

### 3. Create Hive tables on sqooped data in Hadoop
The sqooped data in [Step 2](#2-transfer-data-from-mysql-to-hadoop) is present in the form of files. We can load this to Hive tables by creating required external tables and running load data queries present in [```04_hive_tables_creation.sql```](/part2hivedatawarehouse/04_hive_tables_creation.hql) in [hive prompt](/part1projectsetupinaws/README.md#61-accessing-mysql-and-hive-prompt).