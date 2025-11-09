# Audio Analytics Pipeline on AWS
End-to-end audio analytics pipeline built using AWS S3, Glue, and Athena.
Performs ETL on streaming data, creates curated tables, and applies logistic regression in Python to predict listener completion.
Includes ROC, PR, and confusion matrix evaluations for performance visualization.

# Audio Analytics Pipeline on AWS
┌────────────────┐
│   Raw Audio    │
│   Data (S3)    │
└──────┬─────────┘
       │
       ▼
┌────────────────┐
│ AWS Glue Crawler│
│  - Crawls S3     │
│  - Builds schema  │
└──────┬─────────┘
       │
       ▼
┌────────────────┐
│ AWS Athena      │
│  - SQL queries   │
│  - Data analysis │
└──────┬─────────┘
       │
       ▼
┌────────────────────────┐
│ Python (Colab/Notebook)│
│  - Model: Logistic Reg.│
│  - Metrics + Graphs    │
└────────────────────────┘


# Tech Stack
AWS S3 – storage for raw and curated data
AWS Glue – crawler and ETL schema creation
AWS Athena – SQL querying layer
Python (boto3, sklearn, pandas, matplotlib) – ML training and visualization


# Machine Learning Model
A Logistic Regression classifier predicts listener completion (label = 1 if user listens fully).
Input features:

seconds_listened
duration_secs
listen_ratio
device, country, category

# Model Evaluation
## AUC and Classification Report
![EVAL](https://github.com/Kartikay77/audio-analytics-pipeline-aws/blob/main/Metric_eval.png)

## ROC Curve
![ROC](https://github.com/Kartikay77/audio-analytics-pipeline-aws/blob/main/ROC.png)
## Precision-Recall Curve
![PRC](https://github.com/Kartikay77/audio-analytics-pipeline-aws/blob/main/Precision_Recall.png)
## Confusion Matrix
![CM](https://github.com/Kartikay77/audio-analytics-pipeline-aws/blob/main/Confusion_matrix.PNG)
