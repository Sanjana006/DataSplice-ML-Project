
# 📘 **Rheumatoid Arthritis Progression Prediction**
**Course Project – DS605: Fundamentals of Machine Learning (FOML)**  
**Instructor:** Dr. Arpit Rana  
**Student:** *Sanjana Nathani (M.Sc. Data Science – 1st Year)*  

---

## 📌 **Project Overview**
This is my first hands-on Machine Learning project for DS605 (FOML).  
The goal is to **predict the risk of Rheumatoid Arthritis (RA)** using demographic, lifestyle, nutrition and anthropometric features.  
Dataset link: https://data.mendeley.com/datasets/r7dh8zwwfr/1

---

## 🎯 **Problem Statement**
Rheumatoid Arthritis is a chronic autoimmune disorder affecting joints. Early identification of individuals at risk can help with medical intervention.  
**The core aim:** *Predict whether a person is at risk of RA progression using their clinical and lifestyle attributes.*

---

## 💡 **Motivation**
I selected this healthcare problem because:
- It allows meaningful application of machine learning.
- The dataset connects body composition (e.g., BRI) with RA risk.
- It involves structured, real-world features ideal for ML experimentation.

---

## 📊 **Exploratory Data Analysis (EDA) — Key Insights**

### **1. Target Class Imbalance**
A major finding during EDA is the **severe imbalance** between RA (1) and Non‑RA (0) classes.  
This imbalance can lead models to ignore the minority class, making recall poor.  

To address this, I used **SMOTENC**, a variant of SMOTE designed for mixed numerical + categorical data.

#### Class distribution plot:
![Class Imbalance](class_imbalance_plot.png)

---

### **2. Correlation Insights**
A correlation heatmap revealed:
- Moderate positive correlation between **Age**, **BRI**, and RA.
- Strong correlations among dietary features (calories, proteins, carbs, fats).
- Dietary patterns cluster together, while RA has weaker direct feature correlations, indicating a non-linear relationship — suitable for boosting models.

#### Heatmap:
![Correlation Heatmap](correlation_heatmap.png)

---

### **3. Key Takeaways from EDA**
- Older age groups and females showed higher RA prevalence.
- Higher BRI quartiles had noticeably more RA cases.
- Missing values occurred in meaningful patterns (e.g., lifestyle responses), requiring careful imputation.
- Outliers existed in calorie and nutrient intake distributions.
- The imbalance necessitated SMOTENC for fair model learning.

---

## 🤖 **Models Used & Rationale**

### **1. Logistic Regression**
- Acts as the baseline model.
- Provides feature interpretability valuable in healthcare.
- Helps understand linear relationships.

### **2. LightGBM**
- Extremely efficient for large tabular datasets.
- Handles mixed features and missing values well.
- Good for capturing tree‑based non-linearity.

### **3. XGBoost**
- Strong generalisation ability.
- Powerful for handling imbalanced datasets (with tuned scale_pos_weight).
- Regularisation helps avoid overfitting.

### **4. CatBoost**
- Naturally supports categorical features, reducing encoding complexity.
- Performs well with non-linear feature interactions.
- Robust to data imbalance when tuned.

CatBoost and XGBoost gave the best performance in recall and F1-score after applying **SMOTENC** and threshold tuning.

---

## 🧪 **Model Evaluation**
Given class imbalance, I prioritised:
- **Recall** (sensitivity)
- **Precision**
- **F1-score**
- **ROC-AUC**

Threshold tuning improved the recall of the minority class (RA = 1), which is medically the most important.

---

## 🙏 **Acknowledgements**
I acknowledge the creators of the NHANES-based RA dataset for making it publicly accessible.

> *Sanjana Nathani*  
> MSc Data Science (Year 1)
> DS605 — Fundamentals of Machine Learning
> Dhirubhai Ambani University (DAU), Gandhinagar

