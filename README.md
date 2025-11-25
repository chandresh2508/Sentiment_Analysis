Sentiment Analysis Project

End-to-End Text Processing Using Azure, Python & Power BI

Authors:


Chandresh Patel (200595392)

Nancy Jangwal (200591978)

📌 Project Overview

This project performs end-to-end sentiment analysis on text data collected from multiple online sources. It integrates Python scripts, Azure Cloud services, and Power BI to create a comprehensive machine-learning and data engineering workflow — spanning from raw data preprocessing to final dashboard visualization.

The core workflow includes:

Data Preprocessing: Using Python for cleaning, tokenization, and sentiment scoring.

Cloud Storage: Uploading processed data to Azure Blob Storage.

ETL Pipeline: Creating an Azure Data Factory (ADF) pipeline to orchestrate data movement.

Warehousing: Loading data into Azure SQL Database.

Visualization: Importing SQL data into Power BI for reporting.

📂 Repository Structure
Plaintext

Sentiment_Analysis/

│

├── sentimentanalysis.ipynb     # Main Jupyter Notebook (Preprocessing + Modeling)

├── data/

│   └── sentiment.csv           # Processed dataset ready for upload

├── README.md                   # Project documentation

└── assets/                     # Visual assets and screenshots


Component,Technology

    Programming,    "Python (NLTK, TextBlob, Pandas)"
    Cloud Storage,    Azure Blob Storage
    Data Pipeline,    Azure Data Factory (ADF)
    Database,    Azure SQL Database
    Visualization,    Power BI
    Version Control,    GitHub

Step-by-Step Workflow

1️⃣ Data Preprocessing (Python Notebook)

Performed within the Jupyter Notebook (sentimentanalysis.ipynb):

Load Data: Ingest raw text data.

Cleaning: Remove HTML tags, stopwords, and punctuation.

Scoring: Apply sentiment analysis using TextBlob to generate polarity scores.

Export: Create the final structured sentiment.csv.

2️⃣ Azure Blob Storage Upload

Created a Storage Account and a specific Container.

Uploaded the cleaned sentiment.csv file.

Generated a Blob SAS URL for secure access within the pipeline.

3️⃣ Azure Data Factory (ADF) Pipeline

We constructed a pipeline to automate the data flow:

Source: Azure Blob Storage (linked via SAS).

Sink: Azure SQL Database (Destination table).

Activity: Copy Data Activity to map CSV columns to SQL columns.

Outcome: The flat CSV data is successfully transformed and loaded into a relational database.

4️⃣ Azure SQL Database

Provisioned a SQL Database instance.

Executed the following schema creation script:

SQL

CREATE TABLE sentiment_table (
    id INT IDENTITY(1,1),
    text NVARCHAR(MAX),
    text_clean NVARCHAR(MAX),
    sentiment_label NVARCHAR(50),
    sentiment_score FLOAT
);

5️⃣ Power BI Visualization
Connected Power BI to the Azure SQL Database to generate insights:

📊 Bar Chart: Visualizing Sentiment Distribution (Positive/Neutral/Negative).

🥧 Pie Chart: Percentage breakdown of overall sentiment.

📄 Table View: Comparison of original raw text vs. cleaned text.

📉 Score Tracker: Analysis of sentiment intensity.

Key Insights:

The majority of the analyzed articles displayed Positive sentiment.

Text cleaning significantly improved the accuracy of the sentiment scoring algorithm.

🚀 How to Run This Project

Prerequisites
Python 3.9+

Active Azure Subscription

Power BI Desktop

Git installed

Steps
Clone the repository:

Bash

git clone 
Install dependencies:

Bash

pip install pandas textblob nltk azure-storage-blob
Run the Notebook:

Bash

jupyter notebook sentimentanalysis.ipynb





