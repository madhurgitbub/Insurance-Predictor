# 🏥 Smart Medical Insurance Premium Predictor

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org)
[![Framework](https://img.shields.io/badge/ML-Linear%20Regression-orange.svg)](https://scikit-learn.org)
[![Accuracy](https://img.shields.io/badge/R2%20Score-80.41%25-green.svg)]()

An end-to-end Machine Learning project that leverages **Exploratory Data Analysis (EDA)** and **Linear Regression** to decode health demographics and forecast individual medical insurance charges with high accuracy.

---

## 📌 Project Overview
Why do some people pay drastically higher medical insurance premiums than others? This project dives deep into a dataset of **1,338 individuals** to find the hidden patterns. By analyzing features like age, smoking habits, and BMI, we built a predictive engine that explains roughly **80% of the variance** in healthcare costs.

---

## 💡 Key Insights from EDA
During our data exploration phase, we uncovered some striking relationships:
*   🚭 **The Smoker Tax:** Smoking status (`is_smoker`) has a massive positive correlation of **~0.79** with insurance charges. It is the single largest driver of high premiums.
*   📉 **Age Factor:** Age shows a steady linear increase with premium costs (Correlation: **~0.30**).
*   ⚖️ **The Obese-Smoker Interaction:** While high BMI alone increases costs, being in the `Obese` category combined with smoking pushes charges to the absolute maximum.

---

## 🛠️ Data Pipeline & Architecture

### 1. Data Cleaning
*   Identified and removed duplicate rows to avoid data leakage.
*   Verified that the dataset contains zero missing values.

### 2. Feature Engineering & Selection
*   **Categorical Encoding:** Mapped `sex` to `is_female` and `smoker` to `is_smoker`.
*   **One-Hot Encoding:** Applied to the `region` column.
*   **Smart Binning:** Segmented continuous BMI values into distinct categories (`Underweight`, `Normal`, `Overweight`, `Obese`).
*   **Statistical Trimming:** Conducted **Pearson Correlation** and **Chi-Square Contingency Tests** (`chi2_contingency`) to mathematically drop non-impactful features, ensuring a lightweight and robust model.
*   **Feature Scaling:** Standardized continuous values using `StandardScaler`.

### 3. Model Training
*   **Algorithm:** Linear Regression
*   **Data Split:** 80% Train / 20% Test

---

## 📈 Performance Metrics

The model delivers strong baseline performance, capturing the core underlying trends perfectly:

| Metric | Score |
| :--- | :--- |
| **$R^2$ Score** | **80.41%** |
| **Adjusted $R^2$ Score** | **79.88%** |

---

## 💻 Tech Stack Used
*   **Core:** Python 3
*   **Data Wrangling:** Pandas, NumPy
*   **Visualization:** Matplotlib, Seaborn
*   **Machine Learning & Stats:** Scikit-learn, SciPy

---

## 🚀 Quick Acess

1. **the repo:**
```bash
   git  <https://github.com/madhurgitbub/Insurance-Predictor>
  
