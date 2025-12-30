# card-fraud-detection-system-unsupervised-
💳 Unsupervised Fraud Detection System for Banking Transactions
📌 Project Summary

This project implements an unsupervised fraud detection system for bank transactions using anomaly detection techniques. The system identifies suspicious transactions without relying on labeled fraud data, making it suitable for real-world banking scenarios where fraud patterns constantly evolve.

📂 Dataset Description

Dataset: Credit Card Transactions Dataset

Source: UCI / Kaggle (European cardholders dataset)

File: creditcard.csv

Size: 284,807 transactions

Fraud cases: 492 (≈0.17%)

Features:

V1–V28: PCA-transformed, anonymized transaction features

Amount: Transaction amount

Time: Seconds elapsed between transactions

Class: Fraud label (used only for evaluation)

🔗 Dataset link: https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

🎯 Problem Statement & Business Significance

Fraud detection is a highly imbalanced, high-risk problem where false negatives cause financial loss and false positives increase investigation cost.

Traditional supervised models fail when:

Fraud labels are delayed or unavailable

Fraud patterns change over time

💡 Solution

Use unsupervised anomaly detection to flag rare and abnormal transactions, allowing banks to:

Detect previously unseen fraud patterns

Reduce dependence on labeled data

Prioritize human investigation efficiently

🔁 Project Pipeline (End-to-End)

Data Ingestion & Validation

Preprocessing

Feature scaling

Log transformation of transaction amount

Train-test split (labels hidden during training)

Exploratory Data Analysis (EDA)

Class imbalance analysis

Amount & time distribution

PCA & t-SNE visualizations

Unsupervised Modeling

Isolation Forest

Local Outlier Factor (LOF)

One-Class SVM

Autoencoder (Neural Network)

Model Evaluation

ROC-AUC

Average Precision (PR-AUC)

Precision@K (business-critical)

Model Comparison & Selection

Deployment

Streamlit interactive dashboard

Docker containerization

📊 Quick Results Summary (Test Set)
Model	ROC-AUC	PR-AUC	Precision@100
Isolation Forest	0.88	0.65	0.60
LOF	0.84	0.52	0.48
One-Class SVM	0.81	0.41	0.39
Autoencoder	0.90	0.69	0.64

📌 Isolation Forest and Autoencoder performed best for real-world banking constraints.

🧠 Why Accuracy Is Not Used

Due to extreme class imbalance (99.83% normal), a naïve model achieves 99.8% accuracy by predicting “not fraud” always.

Instead, this project focuses on:

Precision@K → Cost-effective investigations

Recall → Fraud coverage

PR-AUC → Robust under imbalance
