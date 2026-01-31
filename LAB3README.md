EXPERIMENT NO 3
Implement ETL and ELT Pipelines using Python and Apache Spark

AIM
The aim of this experiment is to understand and implement data engineering pipelines using both ETL (Extract–Transform–Load) and ELT (Extract–Load–Transform) approaches on a customer dataset. The experiment focuses on data extraction, cleaning, transformation, feature engineering, aggregation, and storage using Python and Apache Spark.

OBJECTIVES

Extract raw customer data from a CSV file using Python (Pandas) and Apache Spark

Perform data cleaning such as duplicate removal, missing value handling, and text standardization

Apply feature engineering by creating a spend_category column

Generate analytics-ready datasets using aggregation operations

Store processed data using CSV and Parquet formats

Understand the practical differences between ETL and ELT pipelines

INTRODUCTION
ETL and ELT are two important data engineering paradigms used to prepare raw data for analytics. In ETL, data is transformed before loading into the target system, ensuring clean and structured storage. In ELT, raw data is loaded first and transformations are performed inside a scalable processing engine such as Apache Spark. This experiment demonstrates both approaches using a real-world customer dataset. Python (Pandas) is used for ETL, while Apache Spark is used for both ETL and ELT to highlight scalability and performance benefits.

DATASET
The dataset used is a customer CSV file containing customer_id, customer_name, city, and annual_spend.

ALGORITHM / STEPS

Part A: ETL Pipeline using Python (Pandas)

Extract
Load the raw customer dataset from a CSV file into a Pandas DataFrame and display its contents.

Transform
Remove duplicate records
Handle missing values in the city column by replacing them with "Unknown"
Convert customer names to uppercase
Create a new column called spend_category based on annual_spend
Group data by city and spend_category
Calculate total customers and average annual spend

Load
Store the transformed analytics-ready data into a CSV file named etl_analytics_ready.csv.

Part B: ETL using Apache Spark

Initialize Spark Session
Load the CSV dataset into a Spark DataFrame
Remove duplicates and handle missing values
Standardize text fields
Create spend_category column
Perform aggregation
Store the analytics-ready data in Parquet format

Part C: ELT using Apache Spark

Extract and Load
Load raw CSV data into Spark and store it directly as Parquet without transformation

Transform
Read the raw Parquet data
Apply data cleaning, feature engineering, and aggregation inside Spark

Store
Save the final transformed data in Parquet format

PROGRAM
The complete implementation for Python ETL, Spark ETL, and Spark ELT is provided in the experiment notebook file.

OBSERVATION
ETL applies transformations before loading data
ELT loads raw data first and transforms it later
Feature engineering improves data usability
Spark-based ELT pipelines are suitable for large-scale data processing

CONCLUSION
This experiment demonstrates the implementation of ETL and ELT pipelines using Python and Apache Spark. By performing data cleaning, feature engineering, and aggregation, raw customer data is transformed into analytics-ready datasets. The experiment highlights the differences between ETL and ELT approaches and their importance in modern data engineering workflows.

SCREENSHORTS

<img width="748" height="726" alt="Screenshot 2026-01-31 145841" src="https://github.com/user-attachments/assets/2b0bffdf-e3f9-4dde-8302-ec94122d2ebd" />

<img width="694" height="682" alt="Screenshot 2026-01-31 145858" src="https://github.com/user-attachments/assets/da17835d-bae9-4140-bf49-5b713afa3f9b" />

<img width="703" height="680" alt="Screenshot 2026-01-31 145918" src="https://github.com/user-attachments/assets/933c7371-b349-49c4-a09d-5038de5aa4bb" />

<img width="641" height="677" alt="Screenshot 2026-01-31 145932" src="https://github.com/user-attachments/assets/79fa5b6b-e856-4526-a359-c178ba75cf8e" />

<img width="668" height="740" alt="Screenshot 2026-01-31 145946" src="https://github.com/user-attachments/assets/2fd2303e-0212-4c1b-b8db-ae62ceab377d" />

<img width="768" height="556" alt="Screenshot 2026-01-31 150008" src="https://github.com/user-attachments/assets/45df2434-c837-4aab-9d6f-da18dada7b67" />

<img width="676" height="750" alt="Screenshot 2026-01-31 150038" src="https://github.com/user-attachments/assets/464c17e2-0459-436e-b33f-f42bdd65e91b" />

<img width="709" height="741" alt="Screenshot 2026-01-31 150053" src="https://github.com/user-attachments/assets/193b998d-63d4-4479-8110-7df6138d5d1b" />
