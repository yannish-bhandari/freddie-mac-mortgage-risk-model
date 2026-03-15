# Data

This project uses the **Freddie Mac Single-Family Loan-Level Dataset** sample files for origination vintages **2019, 2020, 2021, 2022, and 2023**.

## Why the raw data is not included

The raw dataset files are not included in this repository because:
- the files are too large for a clean GitHub repository
- the project is intended to remain lightweight and reproducible
- the data should be obtained directly from the original source

## Source

Freddie Mac Single-Family Loan-Level Dataset  
Available through Freddie Mac Clarity Data Intelligence

## Reproduction Notes

To reproduce the analysis in this repository:

1. Sign in to the Freddie Mac data portal
2. Download the sample loan-level files for vintages 2019–2023
3. Place the raw files in the folder structure referenced by the notebooks
4. Run the notebooks in numerical order starting from `01_data_ingestion.ipynb`

## Important Note

This repository contains the full notebook workflow, selected output tables, and final report, but not the full raw mortgage files or large intermediate datasets.