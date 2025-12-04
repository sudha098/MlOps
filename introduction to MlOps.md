## **1. Course Introduction**

MLOps is the combination of **Machine Learning + DevOps** practices to automate the end-to-end lifecycle of ML models — from data preparation to deployment and monitoring in production.
The goal of the course is to help you understand how ML projects move from experimentation to real-world applications with reliability, scalability, and automation.

---

## **2. GitHub Repo**

In an MLOps project, **GitHub/Git** stores:

* Source code (data processing scripts, training scripts, model code)
* Infrastructure code (IaC)
* CI/CD pipelines
* Model artifacts version references
* Experiment tracking configuration

GitHub becomes the **single source of truth** for ML pipelines and deployments, similar to GitOps in DevOps.

---

## **3. Getting Started with Machine Learning Team**

In ML teams, there are multiple roles:

| Role                    | Focus Area                                 |
| ----------------------- | ------------------------------------------ |
| Data Scientist          | Experiments, model creation                |
| ML Engineer             | Builds training + inference pipelines      |
| DevOps / MLOps Engineer | Automation, deployment, infra, scalability |
| Data Engineer           | Data ingestion + feature pipelines         |

MLOps bridges the gap between **experimentation (Data Science)** and **production (Engineering + Operations)**.

---

## **4. Introducing MLOps Engineer**

An MLOps engineer ensures that ML models:

* Move from experimentation to production seamlessly
* Run reliably at scale
* Retrain automatically when new data arrives
* Are observable and monitored

Key responsibilities:
✔ Set up CI/CD/CT pipelines
✔ Automate data workflows and retraining
✔ Deploy models (batch, real-time, A/B, canary)
✔ Integrate monitoring and alerting
✔ Manage ML artifacts, models, and metadata

---

## **5. DevOps and MLOps — A Comparison**

| Aspect     | DevOps                     | MLOps                             |
| ---------- | -------------------------- | --------------------------------- |
| Main goal  | Automate software delivery | Automate ML model lifecycle       |
| Output     | Application/service        | ML model + predictions            |
| Versioning | Code only                  | Code + Data + Model               |
| Pipelines  | CI/CD                      | CI/CD + Continuous Training       |
| Deployment | Based on code release      | Based on data + concept drift     |
| Monitoring | App metrics                | Model + Data + Prediction metrics |

⚠ Real ML systems degrade over time even if code is unchanged because **data and patterns shift** → unique challenge MLOps solves.

---

## **6. MLOps Lifecycle**

The lifecycle includes:

1️⃣ **Data Collection & Validation**
2️⃣ **Data Preparation (ETL / Feature Engineering)**
3️⃣ **Model Training & Experiment Tracking**
4️⃣ **Model Evaluation & Selection**
5️⃣ **Model Packaging & Artifact Management**
6️⃣ **Model Deployment (Batch / Online / Stream)**
7️⃣ **Monitoring (Performance + Drift)**
8️⃣ **Auto-Retraining & Feedback Loop**

It is an **iterative cycle**, not a linear one.

---

## **7. CI, CD, CT, CM in MLOps**

| Stage                           | Definition                                                                           |
| ------------------------------- | ------------------------------------------------------------------------------------ |
| **CI – Continuous Integration** | Automate testing and validation of ML code (data tests + training pipeline tests)    |
| **CD – Continuous Deployment**  | Automate deployment of model API/inference service                                   |
| **CT – Continuous Training**    | Retrain automatically when new data arrives, schedules trigger, or drift detected    |
| **CM – Continuous Monitoring**  | Track model accuracy, latency, drift, bias, data quality & trigger alerts/retraining |

CI + CD + CT + CM form the backbone of production ML systems.

---

## **8. Finding and Exploring Right Tools from DevOps for MLOps**

MLOps does **not replace DevOps tools** — it extends them.
Examples:

| Layer                  | Tools                                  |
| ---------------------- | -------------------------------------- |
| Version control        | Git, DVC                               |
| CI/CD                  | GitHub Actions, Jenkins, GitLab        |
| Workflow orchestration | Airflow, Kubeflow, Prefect             |
| Model registry         | MLflow, Sagemaker, WandB               |
| Packaging              | Docker, Conda                          |
| Deployment             | Kubernetes, KFServing, Seldon, BentoML |
| Monitoring             | Prometheus, Evidently AI               |

The core idea → **use DevOps tools for automation + add ML-specific tooling for data and model management**.

---

## **9. MLOps Architecture**

Typical production MLOps architecture includes:

```
         ┌──────────────┐
         │ Data Sources │
         └──────┬───────┘
                │
       ┌────────▼────────┐
       │ Data Pipeline   │  (Airflow / Spark / Beam)
       └────────┬────────┘
                │
      ┌─────────▼─────────┐
      │ Training Pipeline │  (Kubeflow / MLflow / SageMaker)
      └─────────┬─────────┘
                │
      ┌─────────▼─────────┐
      │ Model Registry    │  (MLflow / S3 / GCS)
      └─────────┬─────────┘
                │
      ┌─────────▼─────────┐
      │ Deployment Layer  │  (K8s / KFServing / Seldon / BentoML)
      └─────────┬─────────┘
                │
      ┌─────────▼─────────┐
      │ Monitoring Layer  │  (Evidently / Prometheus / Grafana)
      └─────────┬─────────┘
                │
      ┌─────────▼─────────┐
      │ Auto-Retraining   │ (CT + Data Triggers)
      └────────────────────┘
```

This architecture ensures:

* Automated deployment
* Scalable inference
* Continuous monitoring
* Continuous training when performance drops
