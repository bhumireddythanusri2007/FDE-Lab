EXPERIMENT NO 1
Ingesting Structured, Semi-Structured, and Unstructured Data Using Python
AIM

To ingest and explore structured, semi-structured, and unstructured datasets using Python, and to understand the characteristics of different data types by loading and printing the datasets in a Python environment.

INTRODUCTION

In data engineering, data originates from multiple sources and exists in different formats. Understanding how to ingest and interpret various data types is a fundamental skill for building reliable data pipelines.

Based on structure, data is classified into:

Structured Data – Data organized in a fixed schema, typically stored in tabular formats such as CSV files or relational databases.

Semi-Structured Data – Data that does not follow a rigid schema but contains self-describing elements, such as JSON or XML files.

Unstructured Data – Data without a predefined format or structure, such as text files.

In this experiment, the following datasets are used:

Two structured datasets (CSV and Excel)

One semi-structured dataset (JSON)

One unstructured dataset (Text file)

ALGORITHM / STEPS

Start a new Python notebook in Google Colab.

Upload the structured, semi-structured, and unstructured datasets.

Import the required Python libraries such as Pandas and JSON.

Read the structured datasets using Pandas functions.

Read the semi-structured JSON dataset and normalize it.

Read the unstructured text dataset as raw data.

Display the contents of each dataset.

Compare the characteristics of different data types.

PROGRAM
import pandas as pd
import json

# Ingesting structured data (Excel and CSV)
df_excel = pd.read_excel("/content/drive/MyDrive/FDE LAB/LAB 1/Play_tennis_dataset.xlsx")
print("\nExcel File Head:")
print(df_excel.head())

df_csv = pd.read_csv("/content/drive/MyDrive/FDE LAB/LAB 1/Housing_uncleaned (1).csv")
print("\nCSV File Head:")
print(df_csv.head())

# Ingesting unstructured text data
df_txt = pd.read_csv("/content/drive/MyDrive/FDE LAB/LAB 1/dummy_text.txt", delim_whitespace=True)
print("\nText File Head:")
print(df_txt.head())

# Ingesting semi-structured JSON data
df_json_flat = pd.read_json("/content/drive/MyDrive/FDE LAB/LAB 1/normal_json.json")
print("\nNormal JSON File Head:")
print(df_json_flat.head())

with open("/content/drive/MyDrive/FDE LAB/LAB 1/nested_json.json") as f:
    nested_data = json.load(f)

df_json_nested = pd.json_normalize(nested_data)
print("\nNested JSON File Head:")
print(df_json_nested.head())

EXPECTED OUTPUT

Displays the first few records of:

Excel dataset

CSV dataset

Text dataset

Flat JSON dataset

Nested JSON dataset

CONCLUSION

Structured data is easy to query and analyze due to its fixed schema.

Semi-structured data provides flexibility but requires parsing before analysis.

Unstructured data lacks a defined format and needs additional processing for analytics.
