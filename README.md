# Diamond Price Prediction – Multiple Linear Regression (Python)

An **academic implementation of Multiple Linear Regression** built **from scratch** to predict diamond prices based on physical and qualitative attributes, with a strong emphasis on **statistical rigor, preprocessing, and model validation**.

**Context:** Linear Regression Analysis – University Coursework (2024)  
**Type:** Team Project  
**Domain:** Statistical Modeling · Regression Analysis · Data Analytics

---

## Team Members

| Student ID  | Name                                     |
| ----------- | ---------------------------------------- |
| 22010038    | Ahmed Mohamed Mahmoud Mohamady           |
| 22010162    | Omar Ehab Mohamed Gneidy Hassan          |
| 22010056    | El-Hussein Yasser Ibrahim El-Sayed       |
| 22010183    | Fares Salah El-Din Abdel Fattah El-Nahas |
| 22011562    | Omar Hafez Mamoun Mohamed Hassan         |
| 22011680    | Mohamed Mahmoud Mohamed Hassanein        |
| 22011501    | **Hamza Hussein Yousef Omran**           |
| 22010182    | Fares Ahmed Abu El-Fotouh Abdel Fadil    |
| 20225926030 | Ahmed Hussein Hassan Dwedar              |
| 22010124    | Tarek Mostafa Mohamed Ezz El-Din         |
| 22010263    | Moaz Mostafa Abdelhamid Mostafa          |

---

## Project Overview

This project develops a **multiple linear regression model from first principles** to predict **diamond prices** using a real-world dataset of approximately **54,000 observations**.

Rather than relying solely on library abstractions, the project focuses on:
- Manual regression formulation
- Careful data preprocessing
- Statistical assumption validation
- Interpretability of coefficients and results

The objective is to demonstrate **solid regression fundamentals**, not black-box prediction.

---

## Dataset Description

**Dataset Size:** 53,940 diamonds  
**Target Variable:** Price (USD)

### Numerical Features
- `carat` – Diamond weight
- `depth` – Total depth percentage
- `table` – Table width relative to diamond width
- `x`, `y`, `z` – Physical dimensions (mm)

### Categorical Features
- `cut` – Fair → Ideal  
- `color` – J (worst) → D (best)  
- `clarity` – I1 (worst) → IF (best)

---

## Methodology

### 1. Data Preprocessing

#### Categorical Encoding
Ordinal encoding was applied based on domain hierarchy:

- **Cut:** Fair=1 → Ideal=5  
- **Color:** J=1 → D=7  
- **Clarity:** I1=1 → IF=8  

All mappings preserve **semantic ordering**.

#### Outlier Treatment
- Outliers detected via boxplots
- Extreme values capped using min/max non-outlier thresholds
- Prevented distortion of regression coefficients

No missing values or duplicates were found.

---

### 2. Regression Implementation (From Scratch)

Key components implemented manually:

- Design matrix construction (with intercept)
- Ordinary Least Squares (OLS) estimation
- Prediction function
- SSE, SST computation
- ANOVA table construction
- Adjusted R² calculation

This ensured full transparency of the regression mechanics.

---

### 3. Model Validation

- Train/Test split: **70% / 30%**
- Cross-validated against **scikit-learn**
- Feature relevance checked using **SelectKBest**
- Correlation analysis performed to detect multicollinearity

---

## Results

### Model Performance

| Stage | Adjusted R² |
|------|-------------|
| Baseline Model | 85.92% |
| After Encoding | Improved |
| After Outlier Treatment | **91.91%** |

### Key Findings

- **Strong predictors:** `carat`, `x`, `y`, `z`
- **Weak predictors:** `cut`, `color`, `clarity`, `depth`, `table`
- No significant multicollinearity detected
- Residuals approximately normally distributed
- F-statistic confirms overall model significance

---

## Statistical Analysis

- ANOVA tables generated for each preprocessing stage
- Residual diagnostics validated regression assumptions
- Q–Q plots confirmed residual normality
- Correlation heatmaps revealed feature relationships

---

## Visualizations

The analysis includes:

- Correlation heatmaps
- Outlier boxplots (before & after treatment)
- Feature vs. price scatter plots
- Actual vs. predicted price comparison
- Residual histograms
- Q–Q plots
- Pairplot matrix for exploratory analysis

These visuals support **interpretability and validation**.

---

## Technology Stack

- **Python**
- **NumPy** – Matrix operations
- **Pandas** – Data handling
- **Matplotlib / Seaborn** – Visualization
- **scikit-learn** – Validation & feature selection
- **statsmodels** – Statistical summaries
- **SciPy** – Statistical testing

---

## Engineering Focus

This project emphasizes:
- Statistical correctness over model complexity
- Interpretability of regression coefficients
- Proper handling of categorical data
- Robust outlier management
- Validation of linear regression assumptions

It is designed as a **statistics-first regression project**, not a machine learning benchmark.

---

## Conclusion

Through systematic preprocessing and rigorous statistical validation, model performance improved from **85.92% to 91.91% Adjusted R²**.

The final model provides:
- A reliable framework for diamond price estimation
- Clear insight into feature importance
- Verified adherence to regression assumptions

This highlights the impact of **feature engineering and data quality** on predictive performance.

---

## Future Work

- Polynomial and interaction terms
- Regularized regression (Ridge, Lasso)
- Ensemble models (Random Forest, Gradient Boosting)
- Cross-validation across multiple folds
- Interactive dashboards for business users

---

## How to Run

```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels scipy
jupyter notebook GreatTeamMakeBetterDream.ipynb
