# Datanest : A Real Estate Pipeline in the Cloud (End to End)
This project leverages Amazon Web Services (AWS) to build a comprehensive real estate data pipeline and analytics service. The solution integrates various components of data engineering, data analysis, and data science, offering a robust and scalable architecture to process, analyze, and derive insights from real estate data. The entire project is implemented on AWS Cloud.

# Project Goals
1. Data Ingestion - Create a data ingestion pipeline to extract new incoming data into the AWS data lake.
2. Data Lake - Create a centralized repository to store data from multiple sources and of different formats.
3. Data ETL Jobs - Create Extract, Transform, and Load jobs to preprocess raw data into usable proper versions.
4. Data Analysis - Create SQL queries to analyze data to create key insights about the product.
5. Data Reporting/Analytics - Create dashboards to answer questions and communicate insights to the Stakeholders.

# Dataset Used 
The dataset used is the Zillow Data taken from RapidAPI and contains the real estate data from the United States and Canada where we can search millions of for-sale and rental listings by address, neighborhood, city, or ZIP code, compare their Zestimate home values. Through this data we can also get agents details and their listings. Now offering data retrieval in JSON, CSV, and XLS formats.

Dataset link: https://zillow56.p.rapidapi.com/

# Amazon Web Services used in this project
1. **AWS S3**: Amazon Simple Storage Service (Amazon S3) is a storage service that offers high scalability, data availability, security, and performance. It stores the data as objects within buckets and is readily available for integration with thousands of applications. An object is a file and any metadata that describes the file. A bucket is a container for objects. <br />
2. **AWS IAM**: Amazon Identity and Access Management is a service to securely control access to AWS Services. It is used to manage permissions for different roles under various scenarios. IAM is used to control who is authenticated (signed in) and authorized (has permissions) to use resources.<br />
3. **AWS EC2**: It is a cloud-based service provided by Amazon Web Services (AWS) that offers scalable virtual servers for hosting applications, websites, databases, and more.<br />
4. **Apache Airflow**: It is an open-source platform to programmatically author, schedule, and monitor workflows. It is designed to handle complex workflows in a scalable and efficient way, making it a popular choice for data engineering, machine learning pipelines, and other automation needs.<br />
5. **AWS Lambda**: It is a compute service that provides a runtime environment letting you run code without provisioning or managing servers. The code is written in Lambda functions and is set to trigger as per the use case and is scaled as per the demand.<br />
6. **AWS Redshift**: It is a query service that allows easy analysis of data stored directly in Amazon S3 using standard SQL.Redshift is designed for online analytical processing (OLAP), making it ideal for business intelligence, reporting, and big data workloads.
7. **AWS QuickSight**: It is a cloud-based Business Intelligence service that can be used to deliver easy-to-use insights and answer questions to the stakeholders. There are a lot of data integration options wherein a single data dashboard, QuickSight can include AWS data, third-party data, big data, spreadsheet data, SaaS data, B2B data, and more.

# Implementation

* **Step 1** - Download Zillow Data from API and connect data from API to VS Code in a remote SSH server (through EC2 instance).

* **Step 2** - Exporting data from API to Apache Airflow through AWS EC2 instance.

* **Step 3** - Create DAG's in a Python file in VS Code and tasks to connect on Apache Airflow.
  
* **Step 4** - Trigger tasks in Apache Airflow to orchestrate ETL jobs to load it into an S3 bucket (the first one).
 
* **Step 5** - Create a AWS Lambda function that processes any new incoming data and is triggered by the first S3 bucket and then loaded into a second S3 bucket.
  
* **Step 6** - Create a second AWS Lambda function that is triggered by the second S3 bucket and then the transformed data is now in the third S3 bucket.

* **Step 7** - Connect transformed data to AWS Redshift to query and filter out necessary information.
  
* **Step 8** - Create a dashboard in AWS Quickshift to visualize and answer questions according to business requirements or perform data analytics.
