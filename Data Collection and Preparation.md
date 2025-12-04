
## **1. Data Collection and Preparation**

Data collection and preparation is the **first and most critical stage** in the MLOps lifecycle.
ML models depend on the **quality, quantity, and relevance of data**.
This stage includes:

* Identifying data sources
* Collecting raw data
* Cleaning, transforming, and validating data
* Converting data into **features** suitable for model training

📌 **80% of ML project time is spent in data preparation**.

---

## **2. Data Ingestion — ETL**

ETL = **Extract → Transform → Load**

| Step      | Meaning                                                                      |
| --------- | ---------------------------------------------------------------------------- |
| Extract   | Pull data from multiple sources (DBs, APIs, event streams, logs, files)      |
| Transform | Apply business rules — cleaning, formatting, deduplication, feature creation |
| Load      | Store processed data to a warehouse/lake for downstream ML                   |

Modern systems also use **ELT (Extract → Load → Transform)** where raw data is first stored and then transformed inside the data warehouse.

---

## **3. Idea of Data Lake**

A **Data Lake** is a centralized storage system that keeps **raw, semi-structured, and structured data** at scale.

Examples: **AWS S3, Azure Data Lake, GCP Cloud Storage**

Characteristics:

* Stores petabytes of data cheaply
* Works for **batch + real-time ingestion**
* Data is not forced into strict schema (schema-on-read)
* Supports ML, analytics, and BI use cases

Compared to a **Data Warehouse**, a Data Lake is more flexible and optimized for **ML workloads**.

---

## **4. Data Cleaning and Data Transformation**

Once raw data is available, the next step is to make it usable.

| Category            | Examples                                         |
| ------------------- | ------------------------------------------------ |
| Cleaning            | Fix missing values, remove duplicates, fix types |
| Transformation      | Scaling, normalization, encoding                 |
| Feature Engineering | Creating new predictive features                 |
| Feature Selection   | Removing irrelevant/low-impact features          |

Good data transformation leads to **faster training and better accuracy**.

---

## **5. Small to Medium Datasets — Pandas, Polars**

For small and medium datasets (usually up to a few GB), processing typically happens **locally or in a single machine**.

| Tool       | Strength                                             |
| ---------- | ---------------------------------------------------- |
| **Pandas** | Most popular, rich API for data frames               |
| **Polars** | Designed for speed, multi-threaded, memory-efficient |

Pandas = ease + maturity
Polars = performance + speed (Rust backend)

---

## **6. Large Datasets — Apache Spark (PySpark), Dask**

When the dataset **cannot fit into one machine**, distributed computing is needed.

| Tool                       | Strength                                                                                        |
| -------------------------- | ----------------------------------------------------------------------------------------------- |
| **Apache Spark (PySpark)** | Cluster-based distributed data processing, best for huge datasets                               |
| **Dask**                   | Scales Python code (including Pandas) across multiple workers, lightweight alternative to Spark |

These tools help:

* Process TB to PB data
* Run ETL in distributed mode
* Power ML training pipelines at scale

---

## **7. Streaming Datasets — Apache Kafka & Apache Flink**

For **real-time data and continuous ML pipelines**, streaming technologies are used.

| Tool             | Role                                             |
| ---------------- | ------------------------------------------------ |
| **Apache Kafka** | Real-time event/message streaming platform       |
| **Apache Flink** | Real-time stream processing and analytics engine |

These systems enable:

* Real-time fraud detection
* Live recommendation engines
* Continuous model retraining triggers

---

## **8. What is Feature Store?**

A **Feature Store** is a centralized system to store, manage, and serve **ML features** consistently across:

* Training pipeline
* Batch inference
* Real-time inference

Why it is needed:
✔ Prevents feature leakage
✔ Ensures consistency between training & production
✔ Reusable features → faster model development

Examples: **Feast, Hopsworks, Tecton, SageMaker Feature Store**

---

## **9. Data Pipeline Orchestration — Airflow, Prefect**

Data pipelines need **scheduling, automation, dependencies handling, retries, and monitoring**.

| Tool               | Description                                                            |
| ------------------ | ---------------------------------------------------------------------- |
| **Apache Airflow** | Traditional batch/workflow scheduler using DAGs                        |
| **Prefect**        | Modern orchestration with easier debugging, cloud-native, Python-first |

Orchestrators ensure:

* ETL jobs run automatically
* Retries happen on failure
* Dependencies between tasks are maintained
* Data workflows are trackable and reproducible

They are critical for **production-grade ML Data Pipelines**.

---

### ✔ Module Summary

| Focus                  | Outcome                             |
| ---------------------- | ----------------------------------- |
| Data collection        | Raw data                            |
| Data transformation    | Clean, structured ML-ready features |
| Distributed processing | Large or streaming datasets         |
| Feature storage        | Consistency across ML lifecycle     |
| Orchestration          | Continuous automated data pipelines |

---

