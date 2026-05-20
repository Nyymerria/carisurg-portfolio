# carisurg-portfolio
# Week 0 Assignment - Carisurg MedTech Pathways Program

## Overview
This repository contains my first assignment completed for Week 0 of the Carisurg MedTech Pathways Program. The assignment’s main focus involved basic data cleaning and standardizing the **Gender** column for analysis.

The dataset used contained inconsistencies in how gender values were recorded, which required cleaning before further analysis could be performed.

---

## Objective
The main objective of this task was to:
- Load and explore a raw dataset in Google Colab
- Identify inconsistencies in the Gender column
- Clean and standardize the Gender values for analysis

---

## Dataset
The dataset used was:
- EmergencyTriageDataset_Reduced_Dirty.csv

It contains emergency triage patient data with several inconsistent and messy entries.

---

## Data Cleaning Process

### Gender Column Standardization
The Gender column contained multiple formats of the same values, including:
- Male, MALE, M, m, 1
- Female, FEMALE, F, f, 0

To clean this column:
- All values were converted to lowercase
- Extra whitespace was removed
- Values were mapped into a binary format:
  - Male → 1  
  - Female → 0  

Any values that did not match the mapping were checked for missing data (NaN values).

---

## Tools Used
- Python
- Pandas
- NumPy
- Google Colab

---

## Outcome
After cleaning:
- The Gender column was successfully standardized
- Data inconsistencies were resolved
- The dataset is now prepared for further analysis

---


## Author
Skye Thomas
