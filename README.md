# Datanest : A Real Estate Pipeline in the Cloud (End to End)
This project aims to leverage Amazon Web Services (AWS) to create a real estate data pipeline and analytics service. The project contains an ensemble of different data engineering, data analysis, and data science sections. The entire project is implemented on AWS Cloud.

# Project Goals
1. Data Ingestion - Create a data ingestion pipeline to extract new incoming data into the AWS data lake.
2. Data Lake - Create a centralized repository to store data from multiple sources and of different formats.
3. Data ETL Jobs - Create Extract, Transform, and Load jobs to preprocess raw data into usable proper versions.
4. Data Analysis - Create SQL queries to analyze data to create key insights about the product.
5. Data Reporting/Analytics - Create dashboards to answer questions and communicate insights to the Stakeholders.

# Dataset Used 
The dataset contains daily statistics for trending YouTube videos with up to 200 trending videos per day. It includes several months of data on daily trending YouTube videos. Major nations covered in this dataset are US, GB, DE, CA, JP, IN, and FR regions (USA, Great Britain, Germany, Canada, Japan, India, and France, respectively). 
* There are two parts to this dataset:
  1. Each region’s trending video data is in a separate .csv file. Data includes both numerical and categorical columns and some of them are the video title, channel title, publish time, tags, views, likes and dislikes, description, and comment count.
  2. Each video is also associated with its video category which is stored in a separate .json file that varies between regions.

Dataset link: https://zillow56.p.rapidapi.com/

<p align="center">
  <img width="200" height="250" src="https://github.com/chayansraj/Youtube-data-analytics-using-AWS/assets/22219089/f9d19a32-77a0-486b-aa9e-c88cfb046051">
  <h6 align = "center" > Source: google </h6>
</p>

# Amazon Web Services used in this project
1. **AWS S3**: Amazon Simple Storage Service (Amazon S3) is a storage service that offers high scalability, data availability, security, and performance. It stores the data as objects within buckets and is readily available for integration with thousands of applications. An object is a file and any metadata that describes the file. A bucket is a container for objects. <br />
2. **AWS IAM**: Amazon Identity and Access Management is a service to securely control access to AWS Services. It is used to manage permissions for different roles under various scenarios. IAM is used to control who is authenticated (signed in) and authorized (has permissions) to use resources.<br />
3. **AWS EC2**: It is a cloud-based service provided by Amazon Web Services (AWS) that offers scalable virtual servers for hosting applications, websites, databases, and more.<br />
4. **Apache Airflow**: It is an open-source platform to programmatically author, schedule, and monitor workflows. It is designed to handle complex workflows in a scalable and efficient way, making it a popular choice for data engineering, machine learning pipelines, and other automation needs.<br />
5. **AWS Lambda**: It is a compute service that provides a runtime environment letting you run code without provisioning or managing servers. The code is written in Lambda functions and is set to trigger as per the use case and is scaled as per the demand.<br />
6. **AWS Redshift**: It is a query service that allows easy analysis of data stored directly in Amazon S3 using standard SQL. Amazon Athena also makes it easy to interactively run data analytics using Apache Spark without having to plan for, configure, or manage resources.
7. **AWS QuickSight**: It is a cloud-based Business Intelligence service that can be used to deliver easy-to-use insights and answer questions to the stakeholders. There are a lot of data integration options wherein a single data dashboard, QuickSight can include AWS data, third-party data, big data, spreadsheet data, SaaS data, B2B data, and more.

# Implementation

* **Step 1** - Download Zillow Data from API and connect data from API to VS Code in a remote SSH server (through EC2 instance).

* **Step 2** - Exporting data from API to Apache Airflow through AWS EC2 instance.

* **Step 3** - Create DAG and tasks to connect on Apache Airflow.
  
* **Step 4** - Create ETL jobs to extract data to load it into an S3 bucket (the first one).
 
* **Step 5** - Create a AWS Lambda function that processes any new incoming data and is triggered by the first S3 bucket and then loaded into a second S3 bucket.
  
* **Step 6** - Create a second AWS Lambda function that is triggered by the second S3 bucket and then the transformed data is now in the third S3 bucket.

  <p align="center">
  <img width="550" height="350" src="https://github.com/chayansraj/Youtube-video-data-analytics-using-AWS/assets/22219089/28aaf2c7-b85c-47e6-93b5-e9516f1889ce">
  </p>
  
* **Step 7** - Connect transformed data to AWS Redshift to query and filter out necessary information.
  
* **Step 8** - Create a dashboard in AWS Quickshift to visualize and answer questions according to business requirements or perform data analytics.
