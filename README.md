# Freddie Mac Mortgage Early Delinquency Risk Model

## Overview

This project develops an origination-stage mortgage risk framework using Freddie Mac loan-level data to predict whether a newly originated mortgage will become **90+ days delinquent within 12 months of first payment**.

The project is designed as a **business-facing analytics and risk strategy deliverable** rather than only a technical machine learning exercise. It covers the full workflow from raw data ingestion and target construction to exploratory analysis, model development, challenger-model comparison, threshold testing, risk segmentation, and policy recommendation design.

## Business Problem

Mortgage lenders need to identify higher-risk loans as early as possible so they can:
- prioritize underwriting review
- apply more structured exception handling
- segment the portfolio by early delinquency risk
- improve risk monitoring and decision support

This project answers the question:

**Can a lender identify, at origination, which loans are more likely to become seriously delinquent within the first 12 months?**

## Data Source

This project uses the **Freddie Mac Single-Family Loan-Level Dataset** sample files for vintages **2019–2023**.

The full raw data is **not included** in this repository because of file size and source-access considerations. See `data/README.md` for details on the data source and reproduction process.

## Project Workflow

The analysis is organized into the following stages:

1. **Data ingestion and validation**  
   Load Freddie Mac sample files, validate schemas, correct parsing issues, and create clean multi-year datasets.

2. **Target construction**  
   Build a loan-level target indicating whether a mortgage becomes **90+ days delinquent within 12 months**.

3. **EDA and feature preparation**  
   Review missingness, validate target behavior, and analyze key underwriting dimensions such as credit score, LTV, DTI, and vintage year.

4. **Baseline modeling**  
   Train a logistic regression benchmark on origination-stage variables and evaluate it using a time-aware holdout set.

5. **Challenger modeling and threshold analysis**  
   Train a gradient-boosting challenger model, compare it with the baseline, and evaluate threshold tradeoffs and risk capture behavior.

6. **Model interpretation and policy recommendations**  
   Translate the model into business-facing outputs such as feature importance, risk bands, threshold tables, and underwriting-style policy actions.

## Key Results

- Built a **12-month serious delinquency target** from Freddie Mac servicing history
- Validated meaningful risk patterns across **credit score, LTV, DTI, and origination vintage**
- Developed both a **baseline logistic regression** and a **stronger challenger model**
- Showed that the **challenger materially outperformed the baseline** on the 2023 holdout cohort
- Converted model outputs into:
  - threshold tradeoff tables
  - risk bands
  - bad-loan capture estimates
  - policy-oriented underwriting actions

## Repository Structure

- `notebooks/` — end-to-end notebook workflow
- `data/` — dataset notes and reproduction guidance
- `outputs/tables/` — selected analytical outputs
- `reports/` — final business-facing report

## Main Deliverables

This repository includes:
- the full notebook-based analytical workflow
- selected output tables used in the analysis
- a final business-facing report summarizing the project findings and recommendations

## How to Use This Repository

- Review the notebooks in numerical order to follow the end-to-end workflow
- Use the files in `outputs/tables/` to inspect the main analytical results
- Read the final report in `reports/` for the consulting-style summary of insights and recommendations

## Reproducibility

To reproduce the project:
1. Obtain the Freddie Mac sample files for 2019–2023
2. Place them in the folder structure referenced in the notebooks
3. Run the notebooks in order beginning with `01_data_ingestion.ipynb`

## Final Note

This project is positioned as an **analytics and credit risk decision-support framework**, not as a production software deployment. Its value lies in the target-construction methodology, model comparison, risk-band framework, and underwriting-policy interpretation.