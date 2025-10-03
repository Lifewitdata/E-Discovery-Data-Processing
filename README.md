E-Discovery Data Processing and Analysis Pipeline
This project demonstrates an end-to-end simulated e-discovery workflow using Python. It covers the entire lifecycle from generating a large dataset of email records to processing, cleaning, storing, and finally analyzing the information through reports and a visual dashboard.

🎯 Project Goal
The primary goal of this project is to showcase a robust pipeline for handling Electronically Stored Information (ESI) in a legal context. It highlights best practices for data normalization, quality assurance, text preprocessing, and creating insightful analytics to aid in document review.

📜 Description
E-discovery (electronic discovery) is the process of identifying and producing electronically stored information for legal cases. This notebook simulates key stages of this process, providing a framework for managing large volumes of document metadata and text efficiently.

✨ Key Features
Synthetic Data Generation: Creates a dataset of 50,000 realistic-looking fake email records using the Faker library.

Relational Database Schema: Normalizes the data into a relational schema with Documents, Custodians, and Emails tables using an in-memory SQLite database via SQLAlchemy.

Comprehensive Data Cleaning:

Handles missing data by filling null values with sensible defaults.

Ensures data integrity by removing duplicate records.

Standardizes inconsistent date formats.

Natural Language Processing (NLP): Applies basic text preprocessing to email bodies, including lowercasing, removing punctuation, and filtering out common English stop words using NLTK.

Automated Quality Assurance: Implements a data quality check function to automatically flag records with missing metadata. These issues are logged into a dedicated Error_Log table for review and remediation.

Reporting & Visualization: Generates summary statistics and a visual dashboard using Matplotlib and Seaborn to provide quick insights into the dataset.

Data Export: Exports the final, processed data into multiple common formats (CSV, Parquet, and JSON).

⚙️ Workflow Overview
The notebook follows a logical data pipeline structure:

Setup: Imports libraries and initializes an in-memory SQLite database engine.

Data Generation: A custom function generates a Pandas DataFrame containing 50,000 fake e-discovery records.

Database & ETL: The main DataFrame is broken down into normalized DataFrames (documents, custodians, emails), and the data is loaded into the corresponding SQL tables.

Cleaning & Preprocessing: The data is cleaned to handle missing values and duplicates. The email body text is processed to create a Cleaned Body Text column for analysis.

Quality Checks: The script iterates through the data to find quality issues (e.g., missing sender/recipient IDs). All identified errors are systematically logged in the Error_Log table.

Analysis & Visualization: The database is queried to gather summary statistics. Matplotlib and Seaborn are used to plot the analytical dashboard.

Export: The final cleaned dataset is saved to disk in three different file formats for downstream use.

🗂️ Database Schema
The data is structured into four main tables to ensure normalization and efficiency:

Documents: Stores basic metadata about each document.

Document ID (Primary Key)

Document Date

File Type

Custodians: Stores a unique list of all data custodians (individuals).

Custodian ID (Primary Key)

Custodian Name

Emails: Contains the core email information, linked to documents and custodians.

Email ID (Primary Key)

Document ID (Foreign Key to Documents)

Sender ID (Foreign Key to Custodians)

Recipient ID (Foreign Key to Custodians)

Subject, Body Text, Cleaned Body Text

Error_Log: Captures all data quality issues found during the process.

Error ID (Primary Key)

Document ID

Error Type

Description

📊 Visualization Dashboard
The final analysis is presented in a 2x2 dashboard, providing a quick overview of the dataset's composition and timeline.

🛠️ Technologies Used
Python 3

Pandas: For data manipulation and analysis.

SQLAlchemy: For database interaction and object-relational mapping (ORM).

Faker: For generating synthetic data.

NLTK (Natural Language Toolkit): For text preprocessing.

Matplotlib & Seaborn: For data visualization.

🚀 How to Run
Prerequisites: Ensure you have a Python 3 environment (like Anaconda or a virtual environment) and Jupyter Notebook/JupyterLab installed.

Install Libraries: Install the required libraries using pip.

Bash

pip install pandas sqlalchemy faker nltk matplotlib seaborn
Download NLTK Data: The first time you run the script, it will need to download the stopwords and punkt packages from NLTK. This is handled automatically in the notebook.

Execute the Notebook: Launch Jupyter and open the E_Discovery_Data_Processing_and_Analysis.ipynb file. Run the cells sequentially from top to bottom.

📤 Output
Upon successful execution, the script generates the following files in the project's root directory:

processed_emails.csv: The cleaned email data in CSV format.

processed_emails.parquet: A highly efficient, columnar storage format for the cleaned data.

processed_emails.json: The cleaned email data in JSON Lines format.
