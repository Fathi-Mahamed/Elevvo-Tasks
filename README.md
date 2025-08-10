# Student Exam Score Prediction

## 📌 Project Overview
This project predicts students’ **exam scores** based on multiple performance factors such as study hours, attendance, previous scores, and lifestyle habits.  
It uses **regression models** to estimate the final score, with the goal of identifying key factors that influence academic performance.

The dataset used is the **Student Performance Factors** dataset from Kaggle.

---

## 📂 Dataset
**Source:** [Kaggle - Student Performance Factors](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors)  
**Rows:** ~6,600  
**Columns:** 20  
**Target Variable:** `Exam_Score`  

### Feature Examples
- **Numeric:** `Hours_Studied`, `Attendance`, `Previous_Scores`, `Sleep_Hours`, `Tutoring_Sessions`
- **Categorical:** `Parental_Involvement`, `Access_to_Resources`, `Motivation_Level`, `Teacher_Quality`

---

## 🛠 Tools & Libraries
- **Python**
- **Pandas**, **NumPy** (data processing)
- **Matplotlib**, **Seaborn** (visualization)
- **Scikit-learn** (modeling & evaluation)

---

## 🔍 Approach
1. **Data Cleaning**
   - Handle missing values (median for numeric, `"Unknown"` for categorical).
   - Remove rows with missing target (`Exam_Score`).
   
2. **Exploratory Data Analysis (EDA)**
   - Pairplots to visualize relationships between numeric features and `Exam_Score`.
   - Correlation heatmap for numeric features.
   - Count plots for key categorical variables.
   
3. **Feature Engineering**
   - One-hot encoding for categorical variables.
   - Scaling for numeric variables where required.

4. **Modeling**
   - **Baseline:** Linear Regression using only `Hours_Studied`.
   - **Extended Linear Regression:** Added more numeric features.
   - **Full Model:** All numeric + categorical features (encoded).
   - **Polynomial Regression** (degree 2 & 3) on `Hours_Studied`.
   
5. **Evaluation**
   - Metrics: **Mean Absolute Error (MAE)**, **Root Mean Squared Error (RMSE)**, **R² Score**
   - Visuals: Actual vs Predicted scatter plots, residual histograms.

---

## 📊 Results
| Model                              | R²     | MAE   | RMSE  |
|------------------------------------|--------|-------|-------|
| Hours_Studied only                 | 0.231987    | 2.447569    | 3.294833    |
| Extended numeric                   | 0.641639    | 1.265856    | 2.250657    |
| Full features (encoded) **[BEST]** | 0.769928    | 0.449950    | 1.803353    |
| Polynomial (deg 2)                 | 0.232760    | 2.444780    | 3.293173    |
| Polynomial (deg 3)                 | 0.232842    | 2.444512    | 3.292998    |

📌 **Best Model:** Full features (encoded) — highest R² and lowest RMSE.

---

## 🚀 How to Run
1. Open the notebook in **Google Colab**.
2. Upload `StudentPerformanceFactors.csv`.
3. Run all cells from top to bottom.
4. Review the final **Best Model Summary** for results.

---

## 📈 Key Insights
- Study hours are strongly correlated with exam scores, but **previous performance, attendance, and resource access** are also major contributors.
- Adding lifestyle factors (sleep, physical activity) slightly improves accuracy.
- Polynomial regression offered minimal improvement compared to adding relevant features.

---

## 📌 Next Steps
- Try **regularized regression** (Ridge, Lasso) for better generalization.
- Test **tree-based models** (Random Forest, XGBoost).
- Deploy the best model as an API for real-time predictions.
