# Carisurg MedTech Pathways Program — Data Cleaning Project

## Overview
This repository contains my daily assignments completed for the Carisurg MedTech Pathways Program. The focus is on data cleaning, standardisation, and preparing a clinical dataset for analysis using Python.

The dataset used contains emergency triage patient records with inconsistent, missing, and invalid entries that required systematic cleaning.

## Dataset
**File used:** `EmergencyTriageDataset_Reduced_Dirty.csv`

This dataset contains patient triage information including demographic data and vital signs such as blood pressure, temperature, and consciousness scores.


## Objective
The main objectives across the project were to:

- Load and explore raw clinical data in Google Colab  
- Identify inconsistencies and invalid values  
- Standardise categorical variables  
- Clean and validate clinical measurements using physiological ranges  
- Handle missing data using appropriate imputation methods  
- Visualise distributions to understand data behaviour  


# Day 1 — Gender Data Cleaning

## Issues Identified
- Multiple formats for the same values (e.g. Male, MALE, M, m, 1)  
- Female values also inconsistently recorded (e.g. Female, FEMALE, F, f, 0)  

## Cleaning Process
- Converted all values to lowercase  
- Removed extra whitespace  
- Mapped values into binary format:  
  - Male → 1  
  - Female → 0  
- Checked for missing or unmapped values (NaN)  

## Outcome
The Gender column was successfully standardised into a consistent binary format suitable for analysis.


# Day 2 — Vital Signs Cleaning (DBP)

## Overview
The second task focused on cleaning the **DBP (Diastolic Blood Pressure)** column as part of vital sign preprocessing.


## General Approach
The DBP variable was processed using a structured data cleaning workflow:

- Data inspection using `unique()` and `describe()`  
- Conversion to numeric using `pd.to_numeric(errors='coerce')`  
- Identification of invalid values based on clinical range  
- Replacement of out-of-range values with `NaN`  
- Visualisation using histogram (with KDE) and box plot  
- Imputation of missing values using median  



## Clinical Cleaning Logic
- **DBP:** validated using physiological blood pressure range limits to ensure realistic patient values  

## Why Median Was Used
Median imputation was selected because clinical measurements such as DBP may still contain skewed distributions and residual outliers even after cleaning. The median provides a more robust measure of central tendency compared to the mean.


## Outcome
The DBP column was successfully cleaned, standardised, and prepared for further clinical analysis.


# Summary of Work Completed
Across both days, the dataset was progressively cleaned and standardised. Key achievements include:

- Standardisation of categorical variables (Gender)  
- Cleaning and validation of vital sign columns  
- Removal of invalid and physiologically impossible values  
- Application of statistical imputation techniques  
- Use of visualisation (histograms, KDE, box plots) to understand distributions  
- Preparation of a structured and analysis-ready clinical dataset  


# Conclusion
This project demonstrates a structured approach to clinical data cleaning, combining statistical methods with domain knowledge. The dataset is now significantly more reliable and suitable for further analysis or machine learning applications.


## Author
Skye Thomas
