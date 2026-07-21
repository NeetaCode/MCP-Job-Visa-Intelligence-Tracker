# MCP-Job-Visa-Intelligence-Tracker

# 🚀 MCP Job & Visa Intelligence Tracker

> An MCP-powered platform that automatically discovers job opportunities, verifies visa-related information, evaluates job quality, and maintains a continuously updated job tracking dashboard.

---

# Overview

Searching for jobs is time-consuming. Every day, candidates spend hours:

* Searching multiple job boards
* Checking if companies sponsor H-1B or OPT candidates
* Determining whether jobs are still active
* Identifying potential ghost jobs
* Updating spreadsheets manually
* Tracking applications and follow-ups

This project automates that workflow using **Model Context Protocol (MCP)**, machine learning, and cloud-native MLOps.

---

# Goal

Build an end-to-end intelligent job discovery platform that:

* Finds approximately **80 new jobs daily**
* Verifies visa sponsorship signals
* Detects possible ghost-job indicators
* Ranks opportunities
* Automatically updates Google Sheets
* Provides evidence behind every recommendation

---

# High-Level Architecture

```text
Job Boards & Company Career Pages
                │
                ▼
      MCP Job Discovery Server
                │
                ▼
 Data Cleaning & Duplicate Detection
                │
                ▼
 Visa & Company Verification Servers
                │
                ▼
 Ghost Job Analysis Server
                │
                ▼
 Machine Learning Scoring Engine
                │
                ▼
 Google Sheets + Web Dashboard
```

---

# Features

## 🔍 Automated Job Discovery

Collect jobs from:

* Company Career Pages
* Greenhouse
* Lever
* Ashby
* Workday
* Other supported public job sources

---

## 🛂 Visa Intelligence

Verify:

* Historical H-1B sponsorship
* Current sponsorship language
* OPT support
* STEM OPT support
* Current E-Verify enrollment

Sources include:

* USCIS H-1B Employer Data Hub
* MyVisaJobs
* Official company job descriptions
* Official E-Verify search

---

## 👻 Ghost Job Detection

Analyze signals including:

* Posting age
* Reposted jobs
* Duplicate listings
* Salary transparency
* Job description quality
* Official company listing
* Company hiring activity

The platform reports a **Ghost Job Risk Score** rather than declaring a posting fake.

---

## 🤖 AI Job Ranking

Each job receives an overall Opportunity Score based on signals such as:

* Sponsorship history
* Current sponsorship language
* E-Verify status
* Ghost-job indicators
* Posting freshness
* Salary availability
* Company hiring patterns

Example:

```text
Opportunity Score: 87/100

Recommendation:
✅ Strong Opportunity
```

---

## 📊 Google Sheets Integration

Every day the application automatically updates a tracking sheet containing:

* Company
* Role
* Location
* Job URL
* Date Posted
* Posting Age
* H-1B History
* Sponsorship Language
* OPT/STEM OPT Status
* E-Verify Status
* Ghost Job Risk
* Opportunity Score
* Recommendation
* Application Status
* Verification Date

---

# MCP Servers

The application is organized into independent MCP servers.

## Job Discovery Server

Responsible for:

* Finding jobs
* Reading job details
* Checking official career pages
* Removing duplicates

---

## Visa Intelligence Server

Responsible for:

* USCIS verification
* MyVisaJobs lookup
* Sponsorship extraction
* E-Verify lookup

---

## Ghost Job Analysis Server

Responsible for:

* Posting analysis
* Duplicate detection
* Ghost-job scoring
* Evidence collection

---

## Machine Learning Server

Responsible for:

* Job scoring
* Sponsorship prediction
* Opportunity ranking
* Forecasting trends

---

## Google Sheets Server

Responsible for:

* Adding new jobs
* Updating existing jobs
* Daily synchronization
* Status updates

---

# Machine Learning

The project uses machine learning to prioritize opportunities rather than replacing user decisions.

## Models

* XGBoost
* Scikit-learn

Predictions include:

* Opportunity Score
* Sponsorship Likelihood
* Ghost Job Risk
* Ranking Score

---

# MLOps

The project follows an end-to-end MLOps workflow.

## MLflow

Used for:

* Experiment tracking
* Model comparison
* Metrics
* Model Registry

---

## SageMaker Pipelines

Automates:

```text
Collect Data
      ↓
Validate
      ↓
Feature Engineering
      ↓
Train
      ↓
Evaluate
      ↓
Register
      ↓
Deploy
```

---

## SageMaker Feature Store

Stores reusable features including:

* Posting age
* Sponsorship history
* Salary availability
* Reposting frequency
* Company hiring activity
* E-Verify status

---

# Data Sources

The platform combines information from multiple sources.

### Jobs

* Company Career Pages
* Greenhouse
* Lever
* Ashby
* Workday

### Visa

* USCIS H-1B Employer Data Hub
* MyVisaJobs
* Official Company Pages

### Company

* Official company websites
* Public hiring information

### User Data

* Google Sheets
* PostgreSQL

---

# AI-Assisted Development

Development is accelerated using:

* GitHub Copilot
* Cursor
* Claude Code
* Gemini

Every generated artifact is reviewed before acceptance.

An AI Review Log records:

* Tool used
* Generated artifact
* Human modifications
* Tests performed
* Approval status

---

# Tech Stack

## Backend

* Python
* Django
* Django REST Framework

## MCP

* Python MCP SDK

## Machine Learning

* XGBoost
* Scikit-learn

## MLOps

* MLflow
* AWS SageMaker
* SageMaker Pipelines
* SageMaker Feature Store

## Database

* PostgreSQL
* Snowflake (Analytics)

## Cloud

* AWS

## Deployment

* Docker
* GitHub Actions

## Integrations

* Google Sheets API

---

# Future Enhancements

* Personalized job recommendations
* Interview probability prediction
* Salary prediction
* Resume-to-job matching
* Recruiter outreach tracking
* Email integration
* Browser extension
* Slack or Teams notifications
* Multi-user support
* Career analytics dashboard

---

# Sample Output

```text
Company:
OpenAI

Role:
Machine Learning Engineer

Historical H-1B Sponsorship:
Yes

Current Sponsorship Language:
Supports Sponsorship

Current E-Verify Status:
Yes

Ghost Job Risk:
Low

Opportunity Score:
91/100

Recommendation:
✅ Strong Opportunity

Last Verified:
July 21, 2026
```

---

# Project Vision

The goal is to build an intelligent job search assistant that reduces repetitive research, improves decision-making with evidence-backed insights, and helps job seekers focus on high-quality opportunities instead of spending hours manually verifying job postings.
