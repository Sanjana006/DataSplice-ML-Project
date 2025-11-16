# Rheumatoid Arthritis Prediction – Final Project Report

## 📘 Course Information  
**Course:** DS605 – Foundations of Machine Learning (FOML)  
**Instructor:** Dr. Arpit Rana  
**Project Type:** Machine Learning – Classification  
**Team Members:**  
- Sanjana Nathani (202518002)  
- Urvi Kava (202518006)  
- Rudra Pandit (202518040)  
- Divya Mashruwala (202518042)

---

## 🔍 Problem Statement  
Rheumatoid Arthritis (RA) is a chronic inflammatory disorder that affects joints and can lead to severe long‑term complications if not diagnosed early.  
The goal of this project was to **build a machine learning model that predicts the likelihood of a patient having Rheumatoid Arthritis** based on lifestyle, dietary habits, and demographic features.

Because the RA class was highly imbalanced (~6%), the challenge was to design models that prioritize **recall for class 1 (RA detected)** while maintaining stability in overall performance.

---

## 🧪 Methodology Overview  
### **1. EDA (Common Work Across All Members)**  
All team members collaborated to analyze:
- Distribution of features  
- Correlation heatmaps  
- Missing value patterns  
- Outliers & categorical distributions  
- Target imbalance analysis  

### **2. Data Preprocessing**
- Converted categorical values to string‑type for model compatibility  
- Standardized numeric features  
- Applied **SMOTENC** for minority class oversampling  
- Removed weakly correlated nutritional columns  

---

## 👥 Individual Contributions  

### **🔹 Sanjana Nathani**
Applied and optimized:
- Logistic Regression  
- XGBoost  
- LightGBM  
- CatBoost  

### **🔹 Urvi Kava**
Implemented:
- Logistic Regression  
- Linear SVC  
- Random Forest  

### **🔹 Divya Mashruwala**
Implemented:
- Logistic Regression  
- Linear SVC  
- XGBoost  
- Decision Tree  

### **🔹 Rudra Pandit**
Implemented:
- Logistic Regression  
- Decision Tree  
- XGBoost  

---

## 📊 Model Comparison Summary  
All four team members evaluated multiple models.  
The final consolidated test‑set performance (recall-focused) was:

| Model | Recall (Class 1) | AUC‑ROC |
|-------|------------------|---------|
| **Logistic Regression** | 0.699 | 0.769 |
| **Linear SVC** | **0.715** | 0.770 |
| CatBoost | 0.680 | 0.769 |
| XGBoost | 0.639 | 0.762 |

### **📌 Final Best Model: Linear SVC**  
Linear SVC performed best in terms of:
- Minority‑class **recall (71.5%)**  
- Stable AUC (0.77)  
- Less overfitting compared to boosted models  
- Ideal for a dataset with **linear‑ish structure**, limited rows, and many categorical variables

---

## 🧠 Conclusion  
Although tree‑based models such as XGBoost and CatBoost are often strong on tabular data, our dataset showed **more linear behavior** and performed better with **linear models like Logistic Regression & Linear SVC**.

Among all models:
- **Linear SVC with threshold tuning** delivered the best recall and overall balance.
- Boosting models added complexity but did not significantly outperform linear methods due to dataset size and structure.

**Final selected model for RA prediction: _Linear SVC_.**

---

## 📄 Summary  
This project demonstrated how:
- Imbalance handling  
- Feature preprocessing  
- Proper model selection  
- Threshold optimization  

all play crucial roles in medical prediction tasks where recall is a priority.

The collaborative effort across all team members ensured a complete understanding of the data and strong evaluation of multiple ML algorithms.

---

## 📎 End of Report  
