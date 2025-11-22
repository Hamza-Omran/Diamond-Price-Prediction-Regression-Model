# Diamond Price Prediction using Multiple Linear Regression - 2024

## Academic Context
This project was developed as part of the "Linear Regression Analysis" course (2024).

## Team Members

| Student ID  | Name                                     |
| ----------- | ---------------------------------------- |
| 22010038    | Ahmed Mohamed Mahmoud Mohamady           |
| 22010162    | Omar Ehab Mohamed Gneidy Hassan          |
| 22010056    | El-Hussein Yasser Ibrahim El-Sayed       |
| 22010183    | Fares Salah El-Din Abdel Fattah El-Nahas |
| 22011562    | Omar Hafez Mamoun Mohamed Hassan         |
| 22011680    | Mohamed Mahmoud Mohamed Hassanein        |
| 22011501    | Hamza Hussein Yousef Omran               |
| 22010182    | Fares Ahmed Abu El-Fotouh Abdel Fadil    |
| 20225926030 | Ahmed Hussein Hassan Dwedar              |
| 22010124    | Tarek Mostafa Mohamed Ezz El-Din         |
| 22010263    | Moaz Mostafa Abdelhamid Mostafa          |

## Project Overview

This project implements a multiple linear regression model from scratch to predict diamond prices based on various attributes. The analysis includes comprehensive data preprocessing, outlier handling, and model evaluation using a dataset of approximately 54,000 diamonds.

## Dataset Description

The dataset contains 53,940 diamonds with the following features:

### Numerical Features
- **carat**: Weight of the diamond
- **depth**: Total depth percentage
- **table**: Width of top of diamond relative to widest point
- **x**: Length in mm
- **y**: Width in mm
- **z**: Depth in mm
- **price**: Price in US dollars (target variable)

### Categorical Features
- **cut**: Quality of the cut (Fair, Good, Very Good, Premium, Ideal)
- **color**: Diamond color (J worst to D best)
- **clarity**: Clarity grade (I1 worst to IF best)

## Methodology

### 1. Data Preprocessing

#### Phase 1: Encoding Categorical Data
- Converted categorical features (cut, color, clarity) to numerical values
- Mapping scheme:
  - Cut: Fair=1, Good=2, Very Good=3, Premium=4, Ideal=5
  - Color: J=1, I=2, H=3, G=4, F=5, E=6, D=7
  - Clarity: I1=1, SI1=2, SI2=3, VS1=4, VS2=5, VVS1=6, VVS2=7, IF=8
- Verified no duplicates or null values in the dataset

#### Phase 2: Outlier Treatment
- Identified outliers using boxplot visualization
- Replaced lower outliers with minimum non-outlier values
- Replaced upper outliers with maximum non-outlier values
- Applied threshold-based capping for extreme values

### 2. Implementation Details

Custom implementations of key regression functions:
- Design matrix construction with intercept term
- Beta coefficient estimation using Ordinary Least Squares (OLS)
- Sum of Squared Errors (SSE) calculation
- Sum of Squared Total (SST) calculation
- ANOVA table generation
- Adjusted R-squared computation
- Prediction generation

### 3. Model Validation

- Split data into training (70%) and testing (30%) sets
- Cross-validated results with scikit-learn implementation
- Performed feature selection analysis using SelectKBest
- Conducted correlation analysis to check for multicollinearity

## Results

### Model Performance

| Phase | Accuracy (Adjusted R²) |
|-------|------------------------|
| Before Preprocessing | 85.92% |
| After Phase 1 (Encoding) | Improved |
| After Phase 2 (Outlier Treatment) | 91.91% |

### Key Findings

1. **Strong Predictors**: The variables x, y, z, and carat exhibit strong correlation with diamond price
2. **Weak Predictors**: Cut, color, clarity, table, and depth show weaker correlation with price
3. **No Multicollinearity**: Features are independent (orthogonal) with no significant multicollinearity
4. **Normal Residuals**: Model residuals follow approximately normal distribution, indicating good fit

### Statistical Analysis

- Generated comprehensive ANOVA tables for each preprocessing phase
- F-statistic confirms overall model significance
- Residual analysis validates model assumptions
- Probability plots confirm normal distribution of residuals

## Visualization Highlights

- Correlation heatmap showing feature relationships
- Boxplots for outlier detection before and after treatment
- Scatter plots demonstrating feature-price relationships
- Actual vs. predicted values scatter plot with regression line
- Residual distribution histogram
- Q-Q plot for normality assessment
- Pairplot matrix for comprehensive variable analysis

## Technologies Used

- **Python 3.x**
- **NumPy**: Numerical computations and matrix operations
- **Pandas**: Data manipulation and analysis
- **Matplotlib**: Data visualization
- **Seaborn**: Statistical graphics
- **scikit-learn**: Model validation and feature selection
- **statsmodels**: Statistical analysis and model summaries
- **SciPy**: Statistical tests

## Project Structure

project/
├── diamonds.csv # Dataset
├── GreatTeamMakeBetterDream.ipynb # Main notebook
├── lecture (2).ipynb # Additional analysis
├── lecture (3).ipynb # Additional analysis
└── README.md # Project documentation


## How to Run

1. Install required dependencies:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn statsmodels scipy
```

2. Place the diamonds.csv file in the project directory

3. Open and run the Jupyter notebook:

```bash
jupyter notebook GreatTeamMakeBetterDream.ipynb
```
Here is your content rewritten in **clean, organized, professional Markdown**, with proper headings, spacing, and bullet formatting:

---

## Model Functions

### **Core Functions**

**`get_design_matrix(X)`**
Adds an intercept column to the feature matrix.

**`get_best_model(X, y)`**
Computes beta coefficients using the Ordinary Least Squares (OLS) method.

**`get_predictions(model, X)`**
Generates model predictions based on the estimated coefficients.

**`get_SSE(X, y, model)`**
Calculates the **Sum of Squared Errors (SSE)**.

**`get_SST(y)`**
Computes the **Total Sum of Squares (SST)**.

**`build_anova(X, SSE, SST)`**
Constructs an ANOVA table for model evaluation.

**`get_R2adj(SSE, SST, n, p)`**
Calculates the **Adjusted R-squared** value.

---

### **Preprocessing Functions**

**`remove_outliers(df, threshold)`**
Removes outliers using the Z-score method based on a given threshold.

**`max_non_outliers(df)`**
Identifies maximum values within non-outlier boundaries.

**`min_non_outliers(df)`**
Identifies minimum values within non-outlier boundaries.

---

## Conclusion

Through iterative refinement of the multiple linear regression model, prediction accuracy improved from **85.92%** to **91.91%**.

The final model provides a **robust and interpretable framework** for predicting diamond prices, supported by:

### **Key Strengths**

* A reliable methodology for **accurate diamond price prediction**
* Valuable insights into the **pricing dynamics** of the diamond market
* **Evidence-based rankings** of important predictive features
* Validation of essential **statistical assumptions**

These results emphasize the importance of feature engineering and careful outlier management. The findings equip stakeholders in the diamond industry with data-driven tools to make informed decisions regarding pricing strategies, inventory management, and market forecasting.

---

## Future Work

* Explore non-linear relationships using polynomial features
* Investigate ensemble models (Random Forest, Gradient Boosting, etc.)
* Apply cross-validation for more reliable evaluation
* Analyze temporal trends in diamond pricing
* Build an interactive visualization dashboard

---

## License

This project was completed as part of a college course assignment for **Regression Analysis**.

---

## Acknowledgments

Special thanks to the course instructors and team members who contributed to this comprehensive analysis of diamond pricing dynamics.
