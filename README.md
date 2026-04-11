#  Youth Substance Use Analysis (NSDUH 2023)

##  Overview

This project explores how demographic and household factors are associated with youth substance use using data from the National Survey on Drug Use and Health (NSDUH 2023).

Tree-based machine learning methods are used to analyze patterns in:

- Alcohol use (binary classification)
- Marijuana use frequency (multi-class classification)
- Cigarette use frequency (regression)

---

##  Research Question

How do demographic and household factors influence youth substance use and its frequency?

---

##  Dataset

- Source: NSDUH 2023 Public Use File  
- Includes youth respondents under age 18  
- Variables include:
  - Demographics (sex, race, income, poverty)
  - School information (grade level, attendance)
  - Household structure (parental presence)
  - Substance use measures  

 The dataset contains special coded values (e.g., 91 = never used), which were cleaned before modeling.

---

##  Data Cleaning

Key preprocessing steps:

- Converted categorical variables to factors  
- Re-coded invalid values (e.g., 91, 93 → 0 or NA)  
- Created numeric version of cigarette frequency  
- Removed missing observations  

---

##  Models Used

###  Decision Tree
- Recursive binary splitting using `tree()`

###  Pruned Tree
- Cross-validation using `cv.tree()`

###  Bagging
- Implemented with `randomForest(mtry = number of predictors)`

###  Random Forest
- Uses random subset of predictors (`mtry < p`)
- Includes variable importance analysis

---

##  Problem Types

| Task | Variable | Type |
|------|----------|------|
| Alcohol use | ALCFLAG | Binary classification |
| Marijuana use frequency | MRJYDAYS | Multi-class classification |
| Cigarette use frequency | IRCIGFM | Regression |

---

##  Key Findings

- School grade level is the strongest predictor of substance use  
- Substance use increases with age (grade level)  
- Socioeconomic variables (income, poverty) are also important  
- Demographics alone have limited predictive power  
- Random forest improves performance over single trees  

---

##  Limitations

- Strong class imbalance (most youth report no use)  
- Demographics alone cannot fully explain behavior  
- Models show correlation, not causation  

---

##  Ethical Considerations

- Results should not be used to stereotype individuals  
- Findings reflect social patterns, not personal traits  
- Responsible interpretation is required for sensitive data  

---
