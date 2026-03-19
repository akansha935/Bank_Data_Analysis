Banking Term Deposit Predictor: Spark ML & Streaming Pipeline
 Project Overview
This project implements an end-to-end Big Data solution to predict customer subscriptions for bank term deposits. Using a dataset of 45,000+ records, we developed a distributed machine learning pipeline to identify high-potential leads, improving marketing efficiency and ROI.

 Core Objectives
Data Management: Migrated raw CSV data into Apache Parquet for optimized distributed storage and retrieval.

Distributed EDA: Uncovered key business drivers, identifying Call Duration and Month as the primary predictors of success.

Predictive Modeling: Built a Gradient-Boosted Tree (GBT) classifier, optimizing the PR-AUC to 0.483 through class balancing and feature selection.

Real-Time Analysis: Developed a Spark Structured Streaming service to provide instant predictions on live customer data.

Data Parallelism: Leveraged Spark ML Pipelines to ensure the model scales seamlessly across a distributed cluster.

 Tech Stack
Language: Python

Engine: Apache Spark (PySpark)

Storage: Parquet, Hadoop/Hive (Simulated)

ML Library: Spark MLlib (GBT, Pipelines, StringIndexer)

Visualization: Matplotlib, Seaborn, Pandas

 Model Performance
To handle the high class imbalance (only ~11% "Yes" subscribers), we prioritized Precision-Recall AUC over standard accuracy.

Baseline PR-AUC: 0.450

Optimized PR-AUC: 0.483

Key Features: Call Duration (23.9%), Month (20.1%), Job Category (12.8%).

 How to Run
Prepare Environment: Ensure PySpark and Java are installed.

Data Ingestion: Run the initial cells to convert bank.csv to bank_data_managed.parquet.

Training: Execute the GBT Pipeline cells to train the optimized model.

Streaming: * Start the streaming query cell.

Drop a CSV file into the /bank_stream_input/ folder.

View real-time predictions in the console output.

 Business Recommendations
Call Duration: The bank should prioritize training agents on engagement techniques, as duration is the #1 indicator of intent.

Temporal Strategy: Marketing campaigns should be scheduled based on the "Month" importance scores to maximize conversion rates.

Lead Scoring: Use the model's probability output to rank leads, allowing the sales team to focus on the top 10% of high-probability customers.
