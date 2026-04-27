# Data Engineering & Python Developer Portfolio

End-to-end projects built with real industry tools — ETL pipelines, workflow 
orchestration, CI/CD, cloud deployment, and data applications. Every project 
was built from scratch, not from tutorials.

---

## 🗂️ Projects Index

### Data Engineering & ETL Pipelines

| # | Project | Tech Stack | Highlight |
|---|---------|------------|-----------|
| 1 | [ecommerce-analytics-platform](https://github.com/SharathReddyKottam/ecommerce-analytics-platform) | Snowflake · PostgreSQL · FastAPI · Streamlit · Docker Compose · AWS EC2 | 541,909 real rows · £8.8M revenue dashboard |
| 2 | [airflow-weather-pipeline](https://github.com/SharathReddyKottam/airflow-weather-pipeline) | Airflow · BeautifulSoup · PostgreSQL · Docker Compose | Hourly DAG · 3-task orchestration · live data |
| 3 | [nyc-taxi-analytics](https://github.com/SharathReddyKottam/nyc-taxi-analytics) | Python · Pandas · PostgreSQL | NYC TLC dataset · batch analytics |
| 4 | [customer-analytics-pipeline](https://github.com/SharathReddyKottam/customer-analytics-pipeline) | Snowflake · PostgreSQL · FastAPI · SQLAlchemy · GitHub Actions | Snowflake → PostgreSQL ETL · churn detection |

### CI/CD & Cloud Deployment

| # | Project | Tech Stack | Highlight |
|---|---------|------------|-----------|
| 5 | [flask-aws-cicd](https://github.com/SharathReddyKottam/flask-aws-cicd) | Flask · Jenkins on EC2 · Docker · GitHub Webhooks | Jenkins on cloud server · no ngrok needed |
| 6 | [flask-github-actions](https://github.com/SharathReddyKottam/flask-github-actions) | Flask · GitHub Actions · Docker Hub · AWS EC2 | Push → test → build → deploy, fully automated |
| 7 | [python-data-pipeline](https://github.com/SharathReddyKottam/python-data-pipeline) | Python · Pandas · Jenkins · Docker · ngrok | Jenkins CI/CD built from scratch · 4-stage pipeline |

### Data Applications

| # | Project | Tech Stack | Highlight |
|---|---------|------------|-----------|
| 8 | [ledgerlens](https://github.com/SharathReddyKottam/ledgerlens) | Python · Streamlit · Pandas | Multi-bank statement parser · analytics dashboard |
| 9 | [split-it](https://github.com/SharathReddyKottam/split-it) | Python · Streamlit · Pandas | Bill splitter · spending tracker · debt settlement |

### Academic

| # | Project | Tech Stack | Highlight |
|---|---------|------------|-----------|
| 10 | [survey-app](https://github.com/SharathReddyKottam/survey-app) | Flask · Docker · Kubernetes · Jenkins · AWS RDS | GMU SWE 645 · deployed on GKE + Rancher |

---

## 📈 Project Evolution

How each project builds on the previous one:

| Feature | P1 | P2 | P3 | P4 | P5 | P6 |
|---------|----|----|----|----|----|----|
| CI/CD | Jenkins local | GitHub Actions | Jenkins EC2 | GitHub Actions | GitHub Actions | GitHub Actions |
| Database | — | — | — | Snowflake + PG | Snowflake + PG | PostgreSQL |
| API | — | Flask | Flask | FastAPI | FastAPI | — |
| Dashboard | — | — | — | — | Streamlit | — |
| Orchestration | — | — | — | — | — | Airflow DAG |
| Deployment | Local | EC2 auto | EC2 auto | Local | EC2 Docker | Local |
| Data Size | 10 rows | — | — | 15 rows | 541K rows | Live scrape |
| Docker Compose | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ |

---

## 🛠️ Complete Tech Stack

**Languages**
Python · SQL · YAML · Groovy (Jenkinsfile)

**Data Engineering**
Apache Airflow · Pandas · Snowflake · PostgreSQL · SQLite · ETL Pipelines

**APIs & Dashboards**
FastAPI · Flask · Streamlit · Plotly · Swagger UI · REST API Design

**CI/CD & DevOps**
Jenkins · GitHub Actions · Docker · Docker Compose · Docker Hub · ngrok · GitHub Webhooks

**Cloud**
AWS EC2 · AWS RDS · Snowflake Cloud · GCP GKE

**Testing**
pytest · Unit Testing · GitHub Actions CI

**Other**
SQLAlchemy · python-dotenv · BeautifulSoup · Requests · Multi-platform Docker (ARM64 + AMD64)

---

## 🔍 Project Deep Dives

### 🛒 E-Commerce Analytics Platform
The most complete project — mirrors what a junior data engineer would actually build at a company.

- **541,909 real UK transactions** (2010–2011 Kaggle dataset) loaded to Snowflake RAW layer
- ETL removes returns, nulls, duplicates → **392,692 clean rows** remain
- FastAPI exposes 6 endpoints: revenue, top products, top customers, sales by country
- Streamlit dashboard with 4 KPI cards, monthly revenue chart, product bar chart, country pie chart
- **Multi-platform Docker build** (ARM64 for Mac M1 + AMD64 for EC2) via `docker buildx`
- Full Docker Compose stack: Postgres + FastAPI + Streamlit, one command startup

→ [github.com/SharathReddyKottam/ecommerce-analytics-platform](https://github.com/SharathReddyKottam/ecommerce-analytics-platform)

---

### 🌦️ Airflow Weather Pipeline
Built specifically to get real hands-on Airflow experience — the #1 orchestration tool in DE job postings.

- **3-task DAG**: `scrape_weather → transform_data → load_to_postgres`
- Hourly schedule scrapes live weather for NYC, Chicago, Hyderabad, Bangalore
- XCom used for inter-task data passing
- Airflow webserver + scheduler + Postgres all run via Docker Compose
- GitHub Actions validates DAG syntax on every push

→ [github.com/SharathReddyKottam/airflow-weather-pipeline](https://github.com/SharathReddyKottam/airflow-weather-pipeline)

---

### ❄️ Customer Analytics Pipeline
Demonstrates the two-database pattern used at companies like Instagram and Spotify.

- Extracts from **Snowflake** (cloud data warehouse), transforms with Pandas, loads to **PostgreSQL** (app DB)
- Adds derived columns: `days_since_order`, `is_churned` flag
- FastAPI exposes churned customers, summary stats, and a pipeline trigger endpoint
- Swagger UI auto-generated at `/docs`
- 4 pytest unit tests run on every push via GitHub Actions

→ [github.com/SharathReddyKottam/customer-analytics-pipeline](https://github.com/SharathReddyKottam/customer-analytics-pipeline)

---

### 🚕 NYC Taxi Analytics
Batch analytics pipeline on the NYC TLC taxi dataset — one of the most common DE interview datasets.

→ [github.com/SharathReddyKottam/nyc-taxi-analytics](https://github.com/SharathReddyKottam/nyc-taxi-analytics)

---

### ⚙️ CI/CD Projects (Flask × Jenkins × GitHub Actions)
Three projects that explore CI/CD from different angles — local Jenkins with ngrok tunneling, GitHub Actions with Docker Hub registry, and Jenkins deployed directly on EC2 with a real public IP.

| | flask-github-actions | flask-aws-cicd | python-data-pipeline |
|---|---|---|---|
| CI/CD tool | GitHub Actions | Jenkins on EC2 | Jenkins local |
| Trigger | Push to main | GitHub Webhook | GitHub Webhook + ngrok |
| Registry | Docker Hub | Local | Local |
| Deploy target | AWS EC2 | AWS EC2 | Local container |

→ [flask-github-actions](https://github.com/SharathReddyKottam/flask-github-actions) · [flask-aws-cicd](https://github.com/SharathReddyKottam/flask-aws-cicd) · [python-data-pipeline](https://github.com/SharathReddyKottam/python-data-pipeline)

---

### 🏦 LedgerLens
Multi-bank financial statement parser that normalizes CSV exports from different banks into a unified format and renders an analytics dashboard.

- Parses statements from multiple bank formats with different column structures
- Built with Python + Streamlit + Pandas
- Shows ability to handle real-world messy data from different sources

→ [github.com/SharathReddyKottam/ledgerlens](https://github.com/SharathReddyKottam/ledgerlens)

---

### 💸 Split-It
Bill splitting and expense tracking app — solves a real daily problem.

- Split bills, track group spending, settle debts
- Built with Python + Streamlit + Pandas
- Clean UI, deployable as a standalone app

→ [github.com/SharathReddyKottam/split-it](https://github.com/SharathReddyKottam/split-it)

---

### 🎓 Survey App (GMU SWE 645)
Academic group project — Student Survey web app with a full production-grade CI/CD and Kubernetes deployment pipeline.

- Flask/Django REST backend · Docker · Kubernetes (GKE + Rancher) · Jenkins · AWS RDS MySQL
- Personal contribution: Jenkins CI/CD pipeline setup, GitHub integration, deployment testing, monitoring scripts, Jenkinsfile documentation
- Deployed live on GKE and Rancher/K8s cluster

→ [github.com/SharathReddyKottam/survey-app](https://github.com/SharathReddyKottam/survey-app)

---

## 🎓 Education

**MS Information Systems** — George Mason University (May 2025, GPA 3.20)
Analytics & Big Data · Database Systems · Interpretable Machine Learning · Information Systems Analysis & Design · Component-Based Software Development · Cyber Security

**BS Computer Science** — JNTU Hyderabad (2019–2023)

---

## 📫 Connect

[![GitHub](https://img.shields.io/badge/GitHub-SharathReddyKottam-181717?style=flat&logo=github)](https://github.com/SharathReddyKottam)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/sharathreddyk/)
