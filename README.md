# Survival-Analysis-of-Chlorhexidine-Trial
A high-quality clinical data science project performing survival analysis on Chlorhexidine trial data using CPIS trends, Kaplan–Meier survival curves, Log-Rank tests, Cox PH modelling, and diagnostics. 
# 🧪 Chlorhexidine Survival Analysis  
### A Full Clinical Data Science Pipeline Using Python | Kaplan–Meier • Log-Rank • Cox PH

![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![Python](https://img.shields.io/badge/Python-3.10+-blue)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange)

---

## 📌 **Project Summary**

This repository contains a complete, reproducible **survival analysis workflow** performed on a clinical dataset evaluating different concentrations of **Chlorhexidine (CHX)** in relation to **Ventilator-Associated Pneumonia (VAP)** outcomes.  

The pipeline uses a real-world hospital dataset and demonstrates:

- Data cleaning & preprocessing  
- CPIS (Clinical Pulmonary Infection Score) time-series extraction  
- Kaplan–Meier survival curves  
- Log-rank hypothesis testing  
- Cox Proportional Hazards modeling  
- PH assumption diagnostics  
- High-quality visualizations for publication-ready output  

---

## 📂 **Repository Contents**
📦 chlorhexidine-survival-analysis
│

├── chlorhexidine.ipynb # Main analysis notebook

├── README.md # Documentation

├── requirements.txt # Dependencies (recommended)

 └── /data

  └── Data form Chlorhexidine.xlsx 


---

## 🧠 **What This Project Demonstrates**

This notebook is structured into systematic sections, making it ideal for academic submission, publications, or portfolio showcasing.

### **1️⃣ Library Installation & Imports**
Installs and loads required scientific libraries:
- pandas, numpy, matplotlib, seaborn  
- lifelines (survival modelling)  
- openpyxl (Excel reading)  

---

### **2️⃣ Dataset Loading**
Loads the clinical dataset:  
✔ Reads the Excel file  
✔ Displays initial shape  
✔ Shows raw entries for verification  

---

### **3️⃣ Automatic CPIS Day Column Detection**
The notebook dynamically detects columns like:  
**CPIS Day 1, CPIS Day 2, … CPIS Day N**  
and orders them numerically.  
This makes the notebook **robust to datasets with different CPIS day counts**.

---

### **4️⃣ Data Cleaning & Processing**
- Converts text CHX concentrations into numeric categories  
- Creates binary study arms (0.12% vs 0.20%)  
- Extracts CPIS trajectories  
- Computes event status based on CPIS ≥ 6  
- Extracts *time to VAP event*

---

### **5️⃣ Constructing Survival Dataset**
Builds a clean dataframe containing:
- `time` (days until event or censoring)  
- `event` (1 = VAP, 0 = no VAP)  
- `arm_binary` (CHX concentration)  
- `age`, `gender`, `baseline CPIS`  

This forms the backbone for survival modeling.

---

### **6️⃣ Kaplan–Meier Survival Curves**
Uses `KaplanMeierFitter()` to plot:
- Survival probability over time  
- Group-wise comparison (0.12% vs 0.20% CHX)  
- 95% CI band  

This is the most widely used survival visualization in clinical research.

---

### **7️⃣ Log-Rank Test**
Compares survival curves between two CHX arms:

- Tests statistical significance  
- Returns p-value, test score, and significance level  

This is typically included in clinical papers & thesis work.

---

### **8️⃣ Cox Proportional Hazards Model**
Fits a multivariable Cox model with parameters:

- CHX concentration  
- Age  
- Gender  
- Initial CPIS score  

Outputs:
- Hazard ratios (HR)  
- Confidence intervals  
- p-values  
- Model summary table  

This section is directly publication-ready.

---

### **9️⃣ PH Assumption Diagnostics**
Assesses proportional hazards using Schoenfeld residuals:

- Detects violations  
- Auto-generates diagnostic plots  
- Helps validate model reliability  

---

## 🛠️ **Tech Stack**

| Category | Tools |
|---------|--------|
| Programming | Python 3.10+ |
| Data Handling | pandas, numpy |
| Visualization | matplotlib, seaborn |
| Survival Analysis | lifelines |
| File I/O | openpyxl |
| Notebook | Jupyter |

---

## ▶️ **How to Run This Project**

### **1. Clone the repository**
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```
### **📈 Results Generated** 

## **This notebook produces:**
1. Kaplan–Meier survival curves
2. Log-rank test output tables
3. Cox PH model summary
4. Hazard ratio visualizations
5. PH assumption plots
6. Cleaned and structured survival dataset


---

## Requirements.txt
```
pandas
numpy
matplotlib
seaborn
lifelines
openpyxl
```

## License:

This project is licensed under the MIT License.
Use freely for academic, research, or professional work.


### Author 

## Dr. Varad Vaidya
Clinical Pharmacist | Healthcare Data Analyst | Artificial Intelligence | Data Science

Specializing in hospital data modelling, survival statistics, clinical research, Artificial Intelligence and Data Science.

