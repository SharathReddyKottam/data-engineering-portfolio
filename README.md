# Data Engineering & Python Developer Portfolio

A collection of end-to-end projects built to demonstrate hands-on skills in data engineering, ETL pipelines, CI/CD, cloud deployment, and workflow orchestration. Each project was built from scratch using real industry tools.

---

## Projects Index

### Data Engineering & ETL

| # | Project | Tech Stack | Key Concept |
|---|---------|------------|-------------|
| 6 | [airflow-weather-pipeline](https://github.com/SharathReddyKottam/airflow-weather-pipeline) | Airflow, BeautifulSoup, PostgreSQL, Docker Compose | DAG orchestration, scheduled batch ETL |
| 5 | [ecommerce-analytics-platform](https://github.com/SharathReddyKottam/ecommerce-analytics-platform) | Snowflake, FastAPI, Streamlit, Docker Compose, AWS EC2 | Full-stack DE platform, 541K rows, multi-platform Docker |
| 4 | [customer-analytics-pipeline](https://github.com/SharathReddyKottam/customer-analytics-pipeline) | Snowflake, PostgreSQL, FastAPI, SQLAlchemy, GitHub Actions | Snowflake → PostgreSQL ETL, REST API on top |
| 1 | [python-data-pipeline](https://github.com/SharathReddyKottam/python-data-pipeline) | Python, Pandas, Jenkins, Docker, ngrok | CSV cleaning pipeline, Jenkins CI/CD from scratch |

### CI/CD & Cloud Deployment

| # | Project | Tech Stack | Key Concept |
|---|---------|------------|-------------|
| 3 | [flask-aws-cicd](https://github.com/SharathReddyKottam/flask-aws-cicd) | Flask, Jenkins on EC2, Docker, GitHub Webhooks | Production-grade CI/CD, Jenkins on cloud server |
| 2 | [flask-github-actions](https://github.com/SharathReddyKottam/flask-github-actions) | Flask, GitHub Actions, Docker Hub, AWS EC2 | GitHub Actions vs Jenkins, multi-machine deployment |

---

## Project Evolution

Each project builds on the previous — adding new tools while reinforcing earlier skills.

| Feature | Project 1 | Project 2 | Project 3 | Project 4 | Project 5 | Project 6 |
|---------|-----------|-----------|-----------|-----------|-----------|-----------|
| CI/CD | Jenkins local | GitHub Actions | Jenkins on EC2 | GitHub Actions | GitHub Actions | GitHub Actions |
| Deployment | Local Docker | AWS EC2 auto | AWS EC2 auto | Local | AWS EC2 Docker | Local Docker |
| Database | — | — | — | Snowflake + Postgres | Snowflake + Postgres | PostgreSQL |
| API | — | Flask | Flask | FastAPI | FastAPI | — |
| Dashboard | — | — | — | — | Streamlit | — |
| Orchestration | — | — | — | — | — | Airflow DAG |
| Data Size | 10 rows CSV | — | — | 15 rows sample | 541,909 real rows | Live API scrape |
| Docker Compose | No | No | No | No | Yes | Yes |

---

## Complete Tech Stack

### Languages & Scripting
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=flat)
![Groovy](https://img.shields.io/badge/Groovy-4298B8?style=flat&logo=apachegroovy&logoColor=white)

### Data Engineering & Databases
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake-29B5E8?style=flat&logo=snowflake&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-316192?style=flat&logo=postgresql&logoColor=white)
![Apache Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat&logo=apacheairflow&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-D71F00?style=flat)

### APIs & Dashboards
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat&logo=flask&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat&logo=streamlit&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?style=flat&logo=plotly&logoColor=white)

### CI/CD & DevOps
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Docker Compose](https://img.shields.io/badge/Docker_Compose-2496ED?style=flat&logo=docker&logoColor=white)

### Cloud
![AWS EC2](https://img.shields.io/badge/AWS_EC2-FF9900?style=flat&logo=amazonaws&logoColor=white)
![Snowflake](https://img.shields.io/badge/Snowflake_Cloud-29B5E8?style=flat&logo=snowflake&logoColor=white)

### Testing
![pytest](https://img.shields.io/badge/pytest-0A9EDC?style=flat&logo=pytest&logoColor=white)

---

## Project Highlights

### 🌦️ Airflow Weather Pipeline
Batch ETL pipeline that scrapes live weather data for NYC, Chicago, Hyderabad, and Bangalore on an hourly schedule. Built to get real hands-on experience with Airflow DAGs — the key orchestration tool in modern data engineering stacks.

- Wrote a 3-task DAG: `scrape_weather → transform_data → load_to_postgres`
- Used XCom for inter-task data passing
- All services (Airflow webserver, scheduler, Postgres) run via Docker Compose
- GitHub Actions validates DAG syntax on every push

→ [View repo](https://github.com/SharathReddyKottam/airflow-weather-pipeline)

---

### 🛒 E-Commerce Analytics Platform
The most complete project — processes 541,909 real UK e-commerce transactions end to end. Mirrors what a junior data engineer would build at a company.

- Raw data loaded to Snowflake (permanent source of truth, RAW layer never modified)
- ETL removes returns, nulls, duplicates → 392,692 clean rows remain
- FastAPI exposes 6 endpoints (£8.8M revenue, 4,338 customers, top products, top countries)
- Streamlit dashboard with KPI cards, revenue charts, and product tables
- Multi-platform Docker build (ARM64 + AMD64) for Mac M1 → EC2 deployment

→ [View repo](https://github.com/SharathReddyKottam/ecommerce-analytics-platform)

---

### ❄️ Customer Analytics Pipeline
ETL pipeline connecting Snowflake (cloud data warehouse) to PostgreSQL (app database) via FastAPI. Demonstrates the two-database pattern used at companies like Instagram and Spotify.

- Extracts from Snowflake, transforms with Pandas, loads to PostgreSQL via SQLAlchemy
- FastAPI exposes churned customers, summary stats, and pipeline trigger endpoint
- Swagger UI auto-generated at `/docs`
- 4 pytest unit tests run automatically via GitHub Actions

→ [View repo](https://github.com/SharathReddyKottam/customer-analytics-pipeline)

---

### ⚙️ Flask AWS CI/CD (Jenkins + GitHub Actions)
Two separate projects exploring CI/CD from different angles — Jenkins on a local machine with ngrok tunneling, vs Jenkins deployed directly on EC2 with a real public IP.

- Project 2: GitHub Actions → Docker Hub → SSH into EC2 → pull and run (no server needed)
- Project 3: Jenkins on EC2 with permanent public IP, GitHub webhooks connect directly

→ [flask-github-actions](https://github.com/SharathReddyKottam/flask-github-actions) | [flask-aws-cicd](https://github.com/SharathReddyKottam/flask-aws-cicd)

---

### 🔧 Python Data Pipeline
First project — intentionally simple CSV cleaning pipeline used as a vehicle to learn Jenkins CI/CD from scratch. Keeps focus on the pipeline, not the app.

- 4-stage Jenkinsfile: install → test → build → run
- pytest unit tests on fake data verify ETL logic
- ngrok tunnels localhost Jenkins to GitHub for webhooks

→ [View repo](https://github.com/SharathReddyKottam/python-data-pipeline)

---

## Education

**MS Information Systems** — George Mason University, Fairfax VA (May 2025)
Relevant coursework: Analytics Big Data to Info, Database Systems, Interpretable Machine Learning, Information Systems Analysis & Design, Component-Based Software Development

**BS Computer Science** — JNTU Hyderabad (2019–2023)

---

## Connect

[![GitHub](https://img.shields.io/badge/GitHub-SharathReddyKottam-181717?style=flat&logo=github)](https://github.com/SharathReddyKottam)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/sharathreddyk/)# data-engineering-portfolio
