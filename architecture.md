# Banking Data Engineering Project

## 1. Project Objective
Build an end-to-end banking data engineering platform
using batch and real-time streaming pipelines on GCP.

## 2. Data Source
Generate synthetic banking transactions using Python.

Transaction types:
- UPI
- ATM
- NEFT
- IMPS
- Deposits
- Withdrawals

## 3. Batch Architecture
Python Synthetic Data Generator
        |
        v
CSV / JSON Files
        |
        v
Google Cloud Storage
        |
        v
PySpark Batch Processing
        |
        v
BigQuery Raw
        |
        v
BigQuery Staging
        |
        v
BigQuery Curated

## 4. Streaming Architecture
Python Streaming Producer
        |
        v
Google Cloud Pub/Sub
        |
        v
Apache Beam
        |
        v
Google Cloud Dataflow
        |
        v
BigQuery Raw
        |
        v
BigQuery Staging
        |
        v
BigQuery Curated

Invalid records will be routed to a Dead Letter Queue.

## 5. BigQuery Data Layers

Raw:
Stores source transaction data.

Staging:
Stores validated, standardized and deduplicated transactions.

Curated:
Stores business-ready transactions and analytical summaries.

DLQ:
Stores rejected records and rejection reasons.

## 6. Technologies
- Python
- Git and GitHub
- Google Cloud Storage
- Google Cloud Pub/Sub
- Apache Beam
- Google Cloud Dataflow
- PySpark
- BigQuery
- SQL
- Airflow / Cloud Composer

## 7. Batch Use Cases
- Daily transaction file processing
- Historical data loads
- Data cleansing
- Account-level reconciliation
- Daily branch-level summaries

## 8. Streaming Use Cases
- Real-time transaction ingestion
- Transaction validation
- Duplicate detection
- Failed transaction monitoring
- Real-time channel-level summaries

## 9. Data Quality
- Transaction ID should not be null.
- Transaction amount must be greater than zero.
- Transaction type must be valid.
- Account ID should be populated.
- Invalid data should be sent to DLQ.
- Duplicate transactions should be handled.

## 10. Security
Use only synthetic data.
Use GCP IAM and service accounts.
Never commit credentials or service account keys to GitHub.

## 11. Final Goal
Build, deploy, test and monitor batch and streaming
banking data pipelines on GCP.