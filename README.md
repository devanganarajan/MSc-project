README for MSc Data Analysis
Overview
This repository contains data and analyses related to my MSc research project. The raw data is provided in an Excel file, and specific analyses are saved in CSV files. Each CSV file includes relevant columns for the analysis conducted.

Data Files
1. Raw Data File
File Name: MSc_data.xlsx
Description: This Excel file contains the original raw data collected for the analyses.
2. Analysis CSV Files
The following CSV files contain specific analyses based on the raw data. Each file includes the following columns:

ID: Identifier for each observation or sample.
Treatment: The treatment group assigned to each observation.
NO (Nitric Oxide - Griess): Column containing nitric oxide measurement values.
CP (Cell Proliferation - XTT): Column containing cell proliferation measurement values.
Nvalue: Rounded value of the original data points.
Value: Normalized values of data points, normalized to control vehicle values (calculation performed in the raw data file).
Fixed Effects: Two columns for fixed effects relevant to each analysis.
Day: The day of measurement or observation.
log_value: Logarithmic transformation of the Nvalue column, calculated in RStudio.

Data Processing

Normalization:

The Value column is derived from the normalization of the original data points to the control vehicle values, ensuring that the analyses are comparable across treatment groups.

Log Transformation:

The log_value column is calculated as the natural logarithm of the Nvalue column, with 1 added to prevent taking the logarithm of zero.
RStudio was used for this calculation.
