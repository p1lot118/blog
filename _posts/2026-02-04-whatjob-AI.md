# WhatJob.Ai

The goal of this project is to build a system that scrapes job boards daily, stores the data and predicts skill demand trends and identifies "anomalous" job postings.

# Structured Roadmap (Phased Approach)

<br>

## Phase 1: Automated Ingestion
* Tooling: Python (Scrapy or Selenium), GitHub Actions.
* Task: Build a scraper that targets 1–2 job boards (e.g., Indeed, LinkedIn, or niche tech boards like WeWorkRemotely).
* Requirement: Use GitHub Actions to trigger the script automatically once every 24 hours. 

<br>

## Phase 2: Data Engineering & Storage
* Tooling: SQL (PostgreSQL or SQLite), Pandas.
* Task: Clean the raw HTML/JSON. Parse out "Skills" (Python, SQL, AWS, etc.) from long job descriptions using Regex or simple NLP.
* Requirement: Design a relational schema.

<br>

## Phase 3: Predictive Modeling (The "Prediction" part)
* Tooling: Prophet (by Meta) or Statsmodels (ARIMA).
* Task: Forecast the "Volume of Postings" for specific keywords over the next 3 months.
* Requirement: Calculate the Year-over-Year (YoY) growth of specific skills. For example: "Is the demand for 'PyTorch' growing faster than 'TensorFlow'?"

<br>

## Phase 4: The Cyber Security
* Task: Build a simple Anomaly Detection model.
* The Logic: Scams/Ghost jobs often have weird features (e.g., extremely high salary for "Entry Level," repetitive descriptions, or suspicious domains).

<br>

# Tools

> these tools are the key tools that be used in this project.

### Layer : Tool

**Scraper** : BeautifulSoup + Requests

**Database** : PostgreSQL

**Orchestration** : GitHub Actions 

**NLP/Text** : SpaCy or NLTK

**Forecasting** : Prophet

**Frontend** : Streamlit
