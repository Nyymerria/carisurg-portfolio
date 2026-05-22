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

# Day 3 — Clinical Visualisation & Exploratory Analysis

## Overview

The third stage of the project focused on exploratory clinical data analysis and visualisation using cleaned emergency department vital sign data.

The objective was to transform cleaned physiological variables into clinically interpretable visualisations that could reveal:
- physiological relationships
- abnormal patient patterns
- compensatory responses
- clinically significant thresholds

The visualisations were designed to combine:
- statistical analysis
- emergency medicine reasoning
- clinical storytelling
- publication-style presentation

---

# General Approach

The analysis workflow included:

- Selection of clinically relevant variables
- Creation of scatter plots and histograms
- Use of physiological reference ranges
- Addition of clinical threshold lines and shaded risk zones
- Interpretation of relationships between vital signs
- Export of high-quality figures using Matplotlib

---



# Figure 1 — FiO₂ Distribution Histogram

## Objective

To analyse oxygen therapy requirements across the emergency department population.

---

## Clinical Background

FiO₂ (Fraction of Inspired Oxygen) reflects the amount of oxygen delivered to patients.

Reference points included:
- 21% FiO₂ → room air
- >60% FiO₂ → high-flow oxygen therapy

Higher FiO₂ values may indicate:
- respiratory failure
- severe infection
- critical illness
- need for advanced respiratory support

---

# Figure 2 — Heart Rate vs Mean Arterial Pressure

## Objective

To explore cardiovascular compensation patterns in patients with reduced perfusion pressure.

---

## Clinical Background

Low MAP may trigger sympathetic nervous system activation, causing an increase in heart rate to maintain circulation.

The figure included:
- shock threshold line (MAP < 65 mmHg)
- tachycardia threshold (>100 bpm)
- bradycardia threshold (<60 bpm)

---

## Clinical Question

> Do patients with low blood pressure (MAP) compensate with a higher heart rate in the ED?

---

# Figure 3 — Systolic Blood Pressure vs Mean Arterial Pressure

## Objective

To investigate the relationship between systolic blood pressure (SBP) and mean arterial pressure (MAP).

---

## Clinical Background

MAP is an important indicator of organ perfusion and circulatory stability.

An expected physiological relationship line was included:

\[
MAP \approx 0.73 \times SBP
\]

This visualisation explored whether SBP could potentially act as a simplified estimate of MAP in settings where advanced monitoring may not be available.

---

## Clinical Question

> Does systolic blood pressure predict mean arterial pressure in ED patients?

---




# Figure 4 — Temperature Distribution Histogram

## Objective

To explore the distribution of body temperatures within the emergency department population.

---

## Clinical Zones Included

Shaded clinical regions were added to improve interpretability:

- Hypothermia (<35°C)
- Normal temperature (35–37.5°C)
- Fever (37.5–39°C)
- Hyperpyrexia (>39°C)

---

## Clinical Importance

The histogram helps identify:
- frequency of febrile presentations
- severe temperature abnormalities
- potential infectious disease burden
- prevalence of critically abnormal temperatures

---

# Figure 5 — Respiratory Rate vs Body Temperature

## Objective

To investigate whether increasing body temperature is associated with increased respiratory rate in emergency department patients.

---

## Clinical Background

Fever increases metabolic demand and oxygen consumption. As temperature rises, respiratory rate often increases as part of the body's physiological response.

This relationship may be particularly important in:
- sepsis
- systemic infection
- respiratory illness
- inflammatory states

---

## Visualisation Features

The scatter plot included:

- individual patient observations
- fever threshold line (37.5°C)
- hyperpyrexia threshold line (39°C)
- tachypnoea threshold (RR > 20)
- bradypnoea threshold (RR < 12)

---

## Clinical Question

> Does increasing body temperature correlate with faster respiratory rates in emergency department patients?

---

# Key Skills Demonstrated

- Clinical data visualisation
- Exploratory data analysis (EDA)
- Emergency medicine interpretation
- Physiological reasoning
- Use of Matplotlib for publication-style figures
- Integration of statistical and clinical concepts

---

# Outcome

Day 3 successfully transformed cleaned emergency department data into clinically meaningful visualisations capable of supporting interpretation, education, and future analytical modelling.

The figures demonstrated how simple bedside physiological variables can reveal important relationships relevant to emergency medicine practice in both high- and low-resource settings.

# Conclusion
This project demonstrates a structured approach to clinical data cleaning, combining statistical methods with domain knowledge. The dataset is now significantly more reliable and suitable for further analysis or machine learning applications.


## Author
Skye Thomas
