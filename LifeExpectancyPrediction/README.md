# 🧬 Life Expectancy Prediction using Linear and Ridge Regression

## 📘 Overview
This project aims to predict **Life Expectancy** using health, demographic, and economic indicators from the World Health Organization (WHO) dataset. It demonstrates the step-by-step application of Linear Regression, enhancement with Ridge Regression (L2 regularization), and the use of feature engineering techniques such as interaction terms and transformation to improve model performance.

---

## 📊 Dataset
- **📂 Source**: WHO (via Kaggle)
- **📏 Size**: ~20+ features with multiple years and countries
- **🎯 Target variable**: `Life expectancy`

### 🔑 Key Features Used:
- `Adult Mortality`, `Alcohol`, `BMI`, `HIV/AIDS`, `Status`
- `Total expenditure`, `Income composition of resources`, `Polio`, `Diphtheria`, etc.
- ➕ Engineered features like `BMI_Alcohol`, `Mortality_HIV`, `Income_Schooling`, `Polio_Diphtheria`

---

## 🧼 Data Cleaning & Preprocessing
- 🗑️ Dropped non-informative columns like `Country`, `Year`
- 🧠 Encoded categorical variable `Status` (Developed/Developing)
- 🧮 Handled missing values using column mean imputation
- 🧊 Feature scaling using `StandardScaler`
- 🚫 Removed multicollinear features using correlation threshold and VIF

---

## 🔧 Feature Engineering
To improve model performance:
- ✳️ Added **interaction terms**:
  - `BMI_Alcohol = BMI * Alcohol`
  - `Mortality_HIV = Adult Mortality * HIV/AIDS`
  - `Income_Schooling = Income * Schooling`
  - `Polio_Diphtheria = Polio * Diphtheria`
- 🔁 Created **log/sqrt transformations**:
  - `log_Population = log(1 + Population)`
  - `sqrt_Expenditure = sqrt(Total expenditure)`

---

## 🤖 Models Used
### 📐 1. Linear Regression
- Baseline model
- Evaluated using MSE and R² Score

### 🧱 2. Ridge Regression
- Applied L2 regularization to reduce multicollinearity
- Used `GridSearchCV` to tune the `alpha` parameter
- ✅ Best `alpha`: 10

---

## 📈 Evaluation Metrics
| 📊 Model              | 📉 MSE  | 📈 R² Score |
|----------------------|--------|-------------|
| Linear Regression    | 16.20  | 0.81        |
| Ridge Regression     | 15.18  | 0.82        |

- 🧾 Residuals were plotted to verify error distribution
- 🎯 Actual vs Predicted life expectancy comparison showed Ridge had a slight edge

---

## 🖼️ Visualizations
- 🔥 Correlation heatmap
- 🧩 Feature importance plot (coefficients)
- 📉 Residual plot
- 🎯 Actual vs Predicted scatter plots for both Linear and Ridge

---

## 📦 Requirements
```bash
pandas
numpy
matplotlib
seaborn
scikit-learn
```

---

## 🧠 Key Learnings
- 🔍 Importance of feature engineering and transformation in improving linear models
- 🧰 Regularization with Ridge helps control overfitting and multicollinearity
- 📊 Evaluation through visual and quantitative metrics is essential

---

## 🚀 Future Improvements
- 🧪 Try Lasso or ElasticNet Regression for feature selection
- 🌲 Use tree-based models (e.g., Random Forest, XGBoost)
- 🤖 Automate feature selection with techniques like PCA or Boruta

---

## 👨‍💻 Author
This project was completed as part of a machine learning learning journey, with the goal to apply and showcase practical regression techniques for real-world data problems.

---

## 🗂️ Repository Structure
```
life-expectancy-prediction/
|
├── data/                     # Dataset or link to source
├── notebooks/               # Jupyter notebooks with full code
├── images/                  # Visualizations
├── README.md                # Project overview
├── requirements.txt         # Dependencies
```

---

## 🔗 Links
- 📥 [Dataset on Kaggle](https://www.kaggle.com/datasets/kumarajarshi/life-expectancy-who)
- 📚 [Scikit-learn documentation](https://scikit-learn.org/stable/)

