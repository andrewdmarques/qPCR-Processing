qPCR Analysis

## Description
This project is an analysis of qPCR data, focusing on comparing Ct values and estimating copy numbers for different samples under varying conditions. The data includes both standard dilutions and experimental samples. The analysis generates a standard curve through linear regression, calculates copy numbers for each sample based on this curve, and performs ANOVA to test for significant differences between conditions for each sample.

## Data
The main data file used for this analysis is `2024-09-11_data_v2.csv`. This file contains the following columns:
- `sample`: The sample identifier.
- `condition`: The condition under which the sample was tested.
- `replicate`: The biological replicate of the sample.
- `replicate_qpcr`: The technical replicate for qPCR.
- `ct`: The Ct (cycle threshold) value for qPCR.
- `standard_quantity`: The quantity of the standard.
- `dilution_factor`: The dilution factor for the standard.

## Steps
1. **Data Loading and Preparation**: The data is loaded from a CSV file and manipulated to create a unique identifier (`sample_id`) for each sample by combining the `sample`, `condition`, and `replicate` columns.
   
2. **Averaging Replicates**: The qPCR technical replicates are averaged for each sample, retaining only one entry per unique sample.

3. **Standard Curve Calculation**: A linear regression is performed on the standard samples, plotting Ct values against the log10 of the copy numbers to generate a standard curve.

4. **Copy Number Calculation**: Based on the standard curve, the copy number for each experimental sample is calculated by solving the regression equation.

5. **Data Visualization**: Box plots are generated to visualize the distribution of Ct values and copy numbers across samples and conditions.

6. **ANOVA**: An ANOVA is conducted to test for significant differences in copy numbers between conditions for each sample.
