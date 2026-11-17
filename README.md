# 🏃 Body Performance Analytics & Classification

End-to-end machine learning project that predicts a person's **physical performance class (A–D)** from body measurements and fitness test results. It covers data cleaning, exploratory data analysis, feature engineering, and a comparison of classification and regression models.

## 📌 Project Pipeline

```
Load Data → Understand → Clean → EDA → Feature Engineering → Train Models → Evaluate
```

## 📂 Dataset

- **13,393 records** × 12 columns: age, gender, height, weight, body fat %, blood pressure (diastolic and systolic), grip force, sit-and-bend, sit-ups and broad jump
- **Target:** performance class A (best) → D (lowest), with balanced classes (~3,350 each)

## 🧹 Data Preparation

- Removed exact duplicates and physically impossible values (for example, blood pressure = 0 mmHg)
- Capped extreme outliers at the 99th percentile
- Encoded categorical features and scaled features inside a pipeline, so there is no data leakage
- Engineered features: **BMI**, **pulse pressure** and **strength-to-fat ratio**

## 🤖 Models & Results

**Classification (80/20 split):**

| Model | Accuracy | F1 Score |
|---|---|---|
| **Neural Network (MLP)** | **74.3%** | **0.741** |
| SVM (RBF) | 71.6% | 0.715 |
| Decision Tree | 69.5% | 0.695 |
| KNN (k = 25) | 66.0% | 0.662 |
| SVM (Linear) | 63.3% | 0.631 |

The model rankings held across 80/20, 70/30 and 50/50 splits and in 10-fold cross-validation.

**Regression (predicting broad jump, with no leakage):** the best model is an MLP Regressor, with **R² = 0.787** and RMSE = 18.1 cm.

## 💡 Key Insights

1. Strength and endurance features (grip force, sit-ups, broad jump) predict the class best, better than age or blood pressure.
2. Gender splits the data into two distinct groups: the bimodal grip-force and height distributions show it.
3. Classes A and D are the easiest to classify. Most errors are between B and C, which have similar fitness profiles.
4. Blood pressure has almost no correlation with the class. Resting cardiovascular measurements alone don't predict fitness.

## 🛠️ Tech Stack

Python · Pandas · NumPy · scikit-learn · Matplotlib · Seaborn · Jupyter Notebook

## 📁 Files

| File | Description |
|---|---|
| `Ai_Final_Project.ipynb` | Full notebook: EDA, feature engineering, modeling and evaluation |
| `Body_Performance_Analytics_Report.docx` | Written project report |
| `BodyPerformance_Updated.pptx` | Project presentation |

---

👩‍💻 **Aisha Alsadani**: [LinkedIn](https://www.linkedin.com/in/aisha-alsadani/) · [GitHub](https://github.com/aishaalsadani)
