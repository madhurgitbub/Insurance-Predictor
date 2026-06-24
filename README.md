# 🏥 Medical Insurance Premium Prediction

An end-to-end Machine Learning project utilizing **Exploratory Data Analysis (EDA)** and **Linear Regression** to analyze demographic and health data, and accurately predict individual medical insurance charges.

---

## 📊 Dataset Overview
The dataset contains historical information of 1,338 individuals with the following features:
*   `age`: Age of the primary beneficiary.
*   `sex`: Gender of the insurance contractor (encoded as `is_female`).
*   `bmi`: Body Mass Index ($kg/m^2$), objective index of body weight.
*   `children`: Number of children/dependents covered by health insurance.
*   `smoker`: Smoking status (encoded as `is_smoker`).
*   `region`: The beneficiary's residential area in the US (One-Hot Encoded).
*   `charges`: Individual medical costs billed by health insurance (**Target Variable**).

---

## 🛠️ Key Steps & Workflow

### 1. Exploratory Data Analysis (EDA) & Cleaning
*   Checked data shapes, missing values (`isnull().sum()`), and verified basic statistics using `.describe()`.
*   Handled duplicate records to ensure data integrity.
*   Visualized data distributions using Seaborn `histplot` and checked for outliers using `boxplot`.

### 2. Feature Engineering & Preprocessing
*   **Categorical Encoding:** Mapped `sex` to `is_female` (0/1) and `smoker` to `is_smoker` (0/1).
*   **Binning:** Created a custom `bmi_category` feature (Underweight, Normal, Overweight, Obese) to capture non-linear impacts.
*   **Feature Scaling:** Standardized numerical columns (`age`, `bmi`, `children`) using `StandardScaler` for optimal linear model performance.

### 3. Feature Selection
*   Utilized **Pearson Correlation** to measure continuous linear relationships with `charges` (where `is_smoker` showed the highest correlation of `~0.79`).
*   Applied **Chi-Square Contingency Tests** (`chi2_contingency`) against binned charges to drop statistically insignificant features, keeping only the most impactful variables (`age`, `is_female`, `bmi`, `children`, `is_smoker`, `region_southeast`, `bmi_category_Obese`).

### 4. Model Training & Evaluation
*   Split data into training and testing sets ($80:20$ split).
*   Trained a **Linear Regression** model to predict final insurance costs.

---

## 📈 Model Performance

The model performs exceptionally well for a linear baseline, capturing roughly 80% of the variance in medical costs:

*   **$R^2$ Score:** `80.41%`
*   **Adjusted $R^2$ Score:** `79.88%`

---

## 💻 Tech Stack Used
*   **Language:** Python 3
*   **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, SciPy

---

## 🚀 How to Run Locally
1. Clone the repository:
```bash
   git clone <your-repository-url>
