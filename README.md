
# 📘 **Rheumatoid Arthritis Progression Prediction**
**Course Project – DS605: Fundamentals of Machine Learning (FOML)**  
**Instructor:** Dr. Arpit Rana  
**Name:** *Sanjana Nathani (M.Sc. Data Science – 1st Year)*  

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
A major finding during EDA is the severe imbalance between RA (1) and Non-RA (0) classes.
Such imbalance can cause models to overwhelmingly predict the majority class, resulting in **poor recall for the minority RA group.**

Although I did not apply SMOTE or SMOTENC in this project, I handled this imbalance through different strategies across models:
- **Logistic Regression**: I used class weights, which give higher importance to the minority class so the model does not ignore RA cases.
- **Boosting Models (LightGBM, XGBoost, CatBoost)**: These models inherently handle imbalance better through their tree-based learning process, and I further improved minority-class performance through **threshold tuning**.
  
These techniques helped the models pay more attention to the minority “at-risk” class without artificially generating new samples.

#### Class distribution plot:
![Class Imbalance](/Images/imbalance.png)

---

### **2. Correlation Insights**
A correlation heatmap revealed:
- The highest correlation with RA is around 0.22 (with Age), which is very weak.
- BRI correlates with RA at roughly 0.13, also weak.
- All other dietary features (Calories, Protein, Carbohydrates, Fat, Fiber, Caffeine) show extremely small correlations with RA — generally between 0.00 and 0.07.

#### Heatmap:
![Correlation Heatmap](/Images/heatmap.png)

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
- Serves as a strong baseline model with interpretable coefficients.
- Achieved Recall = 0.765, the highest among all models.
- Precision is low (0.143), but high recall makes it valuable in healthcare contexts where missing a positive RA case is worse than false alarms.

### **2. LightGBM**
- Efficient and powerful for tabular data.
- Achieved the highest F1-Score = 0.246, making it the best overall balanced performer.
- Precision = 0.153, Recall = 0.633.

### **3. XGBoost**
- Strong generalisation and good control over overfitting.
- Achieved the highest precision = 0.171, meaning fewer false positives.
- Lower recall (0.428) suggests it misses more RA cases.

### **4. CatBoost**
- Excellent for handling categorical features.
- Achieved Recall = 0.723, the second-highest after Logistic Regression.
- Precision = 0.137, F1-Score = 0.230.

Overall, **CatBoost** is the best overall model when considering both high recall and strong performance on complex non-linear tabular data, while still maintaining competitive precision and F1-score.

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

