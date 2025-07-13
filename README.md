# Causal Inference Assignment - Mosquito Nets and Dengue Risk

as.

## Research Question
What is the causal impact of mosquito net usage on dengue risk among households?

## Files
- Impact_Assignment1.Rmd: Main R Markdown document with complete analysis
- analysis.R: Clean R script version of the analysis
- dengue_nets.csv: Dataset (stored locally)

## Methods Implemented

### Identification Strategies
- Naive OLS: Baseline regression without controls
- DAG Analysis**: Causal graph construction using `ggdag` and `dagitty`
- Controlled Regression**: Multiple regression with identified confounders
- Matching Methods**:
 - Mahalanobis distance matching
- Propensity score matching  
- Inverse Probability Weighting (IPW)
- **Instrumental Variables**: Using program eligibility as instrument
- *Causal Forest**: Machine learning approach for heterogeneous effects

### Key Variables
- `dengue_risk`: Outcome variable (dengue risk score)
- `net_num`: Treatment variable (mosquito net usage, binary)
- `income`, `health`, `temperature`: Main confounders
- `eligible`: Instrument for IV analysis
- `household`: Additional covariate

## Results Summary

| Method | ATE Estimate |
|--------|-------------|
| Naive OLS | -16.00 |
| Controlled Regression | -10.44 |
| Mahalanobis Matching | -12.00 |
| Propensity Score Matching | -13.00 |
| IPW | -10.29 |
| IV (Eligibility) | -15.00 |

 Required Packages
```r
library(tidyverse)
library(ggdag)
library(dagitty)
library(broom)
library(MatchIt)
library(AER)
library(grf)
library(lmtest)
```

Usage
1. Install required R packages
2. Place dataset in project directory
3. Update file path in script
4. Run analysis or knit R Markdown document


