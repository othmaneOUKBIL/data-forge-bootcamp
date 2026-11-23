# data-forge-bootcamp

A hands-on **Data Engineering & AI** bootcamp repository. Over **3 months (12 weeks)** we go from the everyday tools of a data engineer to production-style pipelines on Google Cloud, and finish by building an AI agent.

Everyone works in **their own branch**. This repo is where your exercises, projects, and progress live.

---

## Table of contents

1. [Goals](#goals)
2. [How we work: one branch per person](#how-we-work-one-branch-per-person)
3. [What we will learn](#what-we-will-learn)
4. [3-month plan](#3-month-plan)
5. [Tools we will use](#tools-we-will-use)
6. [Repository structure](#repository-structure)
7. [Capstone projects](#capstone-projects)
8. [Getting started](#getting-started)
9. [Rules and good practices](#rules-and-good-practices)

---

## Goals

By the end of the 3 months you will be able to:

- Design and build batch and streaming data pipelines
- Model data for analytics (Kimball) and choose between ETL and ELT
- Deploy infrastructure as code and ship with CI/CD on Google Cloud
- Transform data with SQL, dbt, and Spark
- Build a RAG system and an AI agent with Gemini and Google ADK
- Present two portfolio-ready projects and pass technical interviews

---

## How we work: one branch per person

The `main` branch is **protected and shared**: it only holds this README, templates, and common resources. **Never work directly on `main`.**

Each participant owns one long-lived branch:

```
main
├── student/<first-name>-<last-name>     e.g. student/amine-benali
├── student/<first-name>-<last-name>
└── ...
```

### Your workflow

```bash
# 1. Clone the repo
git clone https://github.com/<org>/data-forge-bootcamp.git
cd data-forge-bootcamp

# 2. Create your personal branch (once)
git checkout -b student/<first-name>-<last-name>
git push -u origin student/<first-name>-<last-name>

# 3. Work in your own folder, commit often
git add .
git commit -m "week-03: add BigQuery partitioning exercise"
git push

# 4. Pull shared updates from main when announced
git fetch origin
git merge origin/main
```

### Feature branches (optional)

For larger pieces of work, branch off your personal branch and open a pull request back into it:

```
student/amine-benali
└── student/amine-benali/feat-medallion-pipeline
```

### Commit message convention

Use a clear prefix: `week-XX: <what you did>`, or `fix:`, `docs:`, `refactor:` for maintenance.

### Reviews

- Open a **pull request from your branch to `main`** only when a deliverable is ready for review (for example, at the end of a phase).
- Review at least one classmate's pull request per phase: reading other people's code is part of the learning.

---

## What we will learn

| Area | Topics |
| --- | --- |
| **Developer foundations** | Git and GitHub, Bash, Docker, Python for data, SQL refresher |
| **Data engineering fundamentals** | ETL vs ELT, batch vs streaming, OLAP vs OLTP, data lakes and warehouses, Kimball modeling, Lambda and Kappa architectures, schema evolution, orchestration |
| **System design** | Client-server model, storage, availability and throughput, rate limiting, MapReduce, API design, pub/sub, logging and monitoring |
| **Google Cloud** | BigQuery, Cloud Storage, Cloud Run, Pub/Sub, Eventarc, Storage Transfer Service, Artifact Registry, Cloud Build, Cloud Composer, Vertex AI |
| **Infrastructure and DevOps** | Terraform, CI/CD, containerized deployments |
| **Transformation** | Advanced SQL (window functions), dbt (models, incremental, macros, tests), Apache Spark and Databricks |
| **AI engineering** | Prompt engineering, embeddings, vector databases, RAG and evaluation, MCP, agents with Google ADK, Gemini API |
| **Career prep** | SQL tests, coding interviews, GCP technical interview, portfolio |

---

## 3-month plan

Estimated effort: **10 to 12 hours per week**. Weeks marked with a deliverable should be ready for review by the end of the week.

### Month 1: Foundations and cloud basics (weeks 1 to 4)

| Week | Focus | Deliverable |
| --- | --- | --- |
| 1 | Git/GitHub, Bash, Docker, Python and SQL refresher | A dockerized Python script pulling data from a public API |
| 2 | Data engineering fundamentals: ETL/ELT, batch/streaming, OLAP/OLTP, lakes and warehouses, Kimball | Dimensional model for a sample business |
| 3 | System design: throughput, availability, rate limiting, pub/sub, MapReduce, monitoring | One-page architecture design for a data platform |
| 4 | GCP intro: Cloud Storage, BigQuery, IAM, billing alerts | Raw data landed in GCS and loaded into BigQuery |

### Month 2: Pipelines and transformation (weeks 5 to 8)

| Week | Focus | Deliverable |
| --- | --- | --- |
| 5 | Cloud Run, Pub/Sub, Eventarc, Artifact Registry, Cloud Build | An ingestion service deployed with CI/CD |
| 6 | Terraform and Airflow (local first, Cloud Composer if budget allows) | Infrastructure as code plus a working DAG |
| 7 | dbt and advanced SQL: models, materializations, incremental, macros, tests | A dbt project with staging, intermediate, and mart layers |
| 8 | Apache Spark and Databricks: DataFrame API, partitions, Spark UI | A Spark notebook processing a larger dataset |

### Month 3: Capstones, AI, and interviews (weeks 9 to 12)

| Week | Focus | Deliverable |
| --- | --- | --- |
| 9 | **Capstone 1**, part 1: medallion architecture design, ingestion, infrastructure | Bronze layer deployed with Terraform |
| 10 | **Capstone 1**, part 2: transformations, orchestration, dashboard | Silver and gold layers, Airflow DAG, Power BI or Looker Studio dashboard |
| 11 | AI engineering: LLMs, prompt engineering, embeddings, Pinecone, RAG and evaluation, MCP | **Capstone 2**: a working RAG agent built with Google ADK and Gemini |
| 12 | Interview prep and portfolio: SQL tests, coding practice, GCP interview, polish | Final project submission and cleaned-up portfolio |

> The plan is intentionally dense. If you fall behind, prioritize the two capstones and borrow time from optional practice.

---

## Tools we will use

| Category | Tools |
| --- | --- |
| **Version control and collaboration** | Git, GitHub |
| **Languages** | Python, SQL, Bash |
| **Containers** | Docker, docker-compose |
| **Cloud platform** | Google Cloud Platform: BigQuery, Cloud Storage, Cloud Run, Pub/Sub, Eventarc, Storage Transfer Service, Artifact Registry, Cloud Build, Vertex AI |
| **Infrastructure and orchestration** | Terraform, Apache Airflow, Cloud Composer |
| **Transformation and processing** | dbt, Apache Spark, Databricks |
| **Visualization** | Power BI, Looker Studio |
| **AI engineering** | Gemini API, Claude, Pinecone, Google ADK, MCP |
| **Practice platforms** | LeetCode, StrataScratch |

> **Cost tip:** set a billing budget alert on your GCP account on day one. Cloud Composer is the most expensive service, so practice Airflow locally with Docker first.

---

## Repository structure

`main` contains shared material. Your personal branch follows the same layout inside your own folder.

```
data-forge-bootcamp/
├── README.md
├── resources/                 # Shared cheat sheets, links, datasets
├── templates/                 # Project and README templates
└── workspace/                 # Your work (on your personal branch)
    ├── 01-foundations/
    ├── 02-data-engineering-fundamentals/
    ├── 03-system-design/
    ├── 04-gcp/
    ├── 05-dbt-and-sql/
    ├── 06-spark/
    ├── 07-capstone-data-engineering/
    ├── 08-ai-engineering/
    ├── 09-capstone-ai-engineering/
    └── 10-interview-prep/
```

Each folder should contain a short `README.md` describing what you built, how to run it, and what you learned.

---

## Capstone projects

### Capstone 1: Data engineering

An end-to-end pipeline using the **medallion architecture** (bronze, silver, gold) on Google Cloud:

- **Ingest:** Python or Cloud Run into Cloud Storage
- **Infrastructure:** Terraform
- **Orchestration:** Airflow
- **Transform:** dbt and SQL on BigQuery
- **Serve:** Power BI or Looker Studio dashboard

### Capstone 2: AI engineering

An end-to-end **RAG agent** built with Google ADK and the Gemini API:

- Embeddings stored in Pinecone
- Retrieval and answer generation
- A simple evaluation of answer quality

Choose a dataset or document set you care about (for example Moroccan open data or legal texts) so the project stands out in your portfolio.

---

## Getting started

### Prerequisites

- Basic programming, ideally in Python
- Some SQL
- Comfort with the command line
- A Google Cloud Platform account (the free tier is enough to start)
- Git installed, a GitHub account, and Docker Desktop

### First steps

1. Clone the repository and create your personal branch (see [How we work](#how-we-work-one-branch-per-person)).
2. Create your `workspace/` folder structure.
3. Set up your GCP project and a **billing budget alert**.
4. Start with week 1.

---

## Rules and good practices

- Work only on **your own branch**. Do not push to a classmate's branch without asking.
- Never commit secrets: no API keys, service account files, or `.env` files. Use a `.gitignore` and environment variables.
- Commit small and often, with clear messages.
- Document every project with a README and an architecture diagram.
- Shut down or destroy cloud resources when you finish (`terraform destroy`) to avoid surprise bills.
- Ask questions early and help each other: review pull requests with kindness and precision.

---

Happy building.
