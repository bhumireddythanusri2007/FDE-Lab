# Experiment No. 2

## Data Lake, Data Warehouse, and Lakehouse (Conceptual & Free)



## Aim

To understand and demonstrate the concepts of **Data Lake**, **Data Warehouse**, and **Lakehouse** using cloud-style storage organization and analytics, without incurring any cost.



## Overview

Modern data systems store and analyze large volumes of data using different architectures:

* **Data Lake**: Stores raw data in any format.
* **Data Warehouse**: Stores cleaned, structured data for fast analytics.
* **Lakehouse**: Combines flexibility of data lakes with performance of data warehouses.

This experiment demonstrates these ideas using simple storage organization and SQL-style queries.



## Key Concepts (Simple)

* **Data Lake**: Raw files (CSV, logs, images). Cheap and flexible.
* **Data Warehouse**: Structured tables (rows/columns). Fast reporting.
* **Lakehouse**: One system that supports both raw storage and analytics.
* **ETL**: Extract data → Transform (clean) → Load into warehouse.
* **Logical Table**: Schema defined on files without moving data.



## Architecture Mapping

* **S3 (conceptual)** → Data Lake
* **Athena (conceptual)** → Serverless query on files
* **Redshift (conceptual)** → Data Warehouse
* **Local folders / DuckDB (free alternative)** → Lakehouse-style demo



## Steps (High Level)

1. Store raw CSV files in object storage (Data Lake).
2. Define a logical table on top of files.
3. Run SQL queries directly on the files.
4. Perform ETL to load clean data into a warehouse.
5. Verify data using SQL queries.



## Program (Conceptual SQL)

### Create Database and External Table


CREATE DATABASE demo_db;

CREATE EXTERNAL TABLE demo_db.customers (
  customer_id INT,
  customer_name STRING,
  city STRING
)
ROW FORMAT SERDE 'org.apache.hadoop.hive.serde2.OpenCSVSerde'
WITH SERDEPROPERTIES (
  "separatorChar" = ",",
  "quoteChar" = "\""
)
LOCATION 's3://your-bucket-name/customers/';


### Query Data Lake


SELECT * FROM demo_db.customers;

SELECT city, COUNT(*) AS total_customers
FROM demo_db.customers
GROUP BY city;


### Load into Data Warehouse (ETL)


CREATE TABLE customers_dw (
  customer_id INT,
  customer_name VARCHAR(50),
  city VARCHAR(50)
);

COPY customers_dw
FROM 's3://your-bucket-name/customers/customer.csv'
IAM_ROLE 'arn:aws:iam::account-id:role/RedshiftRole'
CSV
IGNOREHEADER 1;




## Expected Output

* Object storage bucket created (Data Lake).
* Logical table created and queried.
* Data loaded into warehouse and verified.



## Observations

* Object storage scales easily for raw data.
* Serverless queries analyze files without databases.
* Logical tables avoid data duplication.
* ETL improves performance for analytics.



## Conclusion

This experiment demonstrates how raw data is stored in a data lake, queried directly using serverless analytics, and then transformed and loaded into a data warehouse. The workflow reflects real-world data engineering practices and highlights the role of lakehouse architectures.

Screenshorts
<img width="1126" height="540" alt="Screenshot 2026-01-26 105819" src="https://github.com/user-attachments/assets/feeae66d-b91a-4bef-8473-676d88e8ce60" />
<img width="1071" height="577" alt="Screenshot 2026-01-26 105831" src="https://github.com/user-attachments/assets/2f8b3817-d1cd-4882-bf52-53bc8a34d3c1" />



