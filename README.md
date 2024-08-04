# **MSc Brain Sciences Project Data Analysis**

## **Overview**

This repository contains data and analyses codes related to my MSc Brain Sciences research project. The raw data is provided in an Excel file, and specific analyses are saved in CSV files. Each CSV file includes relevant columns for the analysis conducted.

## **Data**

### **1. Raw Data File**
- **File Name:** `MSc_data.xlsx`
- **Description:** This Excel file contains the original raw data collected and prelimiary normalization calculation used for the analyses.

### **2. Griess Data CSV File**
The Griess analysis CSV files contain the following columns:

- **ID:** Identifier for each observation or sample.
- **Treatment:** The treatment group assigned to each observation.
- **NO (Nitric Oxide):** Column containing nitric oxide measurement values (original data points).
- **Nvalue:** Rounded value of the original data points.
- **Value:** Normalized values of data points, normalized to control vehicle values (calculation performed in the raw data file).
- **Fixed Effect 1:** First fixed effect relevant to the specific Griess analysis.
- **Fixed Effect 2:** Second fixed effect relevant to the specific Griess analysis.
- **Day:** The day of measurement or observation.
- **log_value:** Logarithmic transformation of the `Nvalue` column (calculated in RStudio).

### **Example of Griess CSV Structure**
| ID  | Treatment  | NO   | Nvalue | Value | Fixed Effect 1 | Fixed Effect 2 | Day | log_value |
|-----|------------|------|--------|-------|----------------|----------------|-----|-----------|
| 1   | Control    | 25.0 | 30     | 0.8   | Effect 1 Value | Effect 2 Value | 1   | 3.4012    |
| 2   | Treatment A| 34.0 | 35     | 1.0   | Effect 1 Value | Effect 2 Value | 1   | 3.5553    |
| ... | ...        | ...  | ...    | ...   | ...            | ...            | ... | ...       |


### **3. XTT Data CSV File**
The XTT analysis CSV files contain the following columns:

- **ID:** Identifier for each observation or sample.
- **Treatment:** The treatment group assigned to each observation.
- **CP (Cell Proliferation):** Column containing cell proliferation measurement values (original data points).
- **Cvalue:** Rounded value of the original data points for cell proliferation.
- **Value:** Normalized values of data points, normalized to control vehicle values (calculation performed in the raw data file).
- **Fixed Effect 1:** First fixed effect relevant to the XTT analysis.
- **Fixed Effect 2:** Second fixed effect relevant to the XTT analysis.
- **Day:** The day of measurement or observation.
- **log_value:** Logarithmic transformation of the `Cvalue` column (calculated in RStudio).

### **Example of XTT CSV Structure**
| ID  | Treatment  | CP   | Cvalue | Value | Fixed Effect 1 | Fixed Effect 2 | Day | log_value |
|-----|------------|------|--------|-------|----------------|----------------|-----|-----------|
| 1   | Control    | 1.2  | 30     | 0.8   | Effect 1 Value | Effect 2 Value | 1   | 3.4012    |
| 2   | Treatment A| 1.5  | 35     | 1.0   | Effect 1 Value | Effect 2 Value | 1   | 3.5553    |
| ... | ...        | ...  | ...    | ...   | ...            | ...            | ... | ...       |


## **Data Processing**

1. **Normalization:**
   - The `Value` column in the Griess data is derived from the normalization of the original NO data points to the control vehicle values, ensuring that the analyses are comparable across treatment groups.
   - The `Value` column in the XTT data is similarly derived from normalization of the original CP data points.

2.  **Log Transformation:** 
   - For Griess data, the `log_value` column is calculated as the natural logarithm of the `Nvalue` column, with 1 added to specifically some analyses as to prevent taking the logarithm of those data points having a value of '0'.
   - For XTT data, the `log_value` column is calculated as the natural logarithm of the `Cvalue` column.

## **R Code for Analyses**

All R codes used for the analyses is contained in the `MScProjectR.Rmd` file. This R Markdown file includes the data processing, statistical analyses, and visualizations performed as part of this project.
