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

# ===========================
# 📊 MODEL EVALUATION RESULTS
# ===========================

AUC Score              : 0.5925
Accuracy               : 0.39
Precision (Class 0)    : 0.91
Recall (Class 0)       : 0.32
F1-Score (Class 0)     : 0.47

Precision (Class 1)    : 0.18
Recall (Class 1)       : 0.83
F1-Score (Class 1)     : 0.29

Macro Avg (Precision)  : 0.54
Macro Avg (Recall)     : 0.57
Macro Avg (F1-Score)   : 0.38

Weighted Avg (Precision): 0.80
Weighted Avg (Recall)   : 0.39
Weighted Avg (F1-Score) : 0.44

