# 🧪 Chlorhexidine Survival Analysis  
### A Full Clinical Data Science Pipeline Using Python | Kaplan–Meier • Log-Rank • Cox PH

Survival analysis of a randomized controlled trial comparing **0.12% vs 0.20% chlorhexidine** oral care for preventing **ventilator-associated pneumonia (VAP)** in intubated ICU patients, using CPIS trends, Kaplan–Meier survival curves, log-rank tests, Cox PH modelling and diagnostics.

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

## 📚 **Source Study & Data**

The dataset comes from this published randomized controlled trial:

> Vyas N, Mathur P, Jhawar S, Prabhune A, Vimal P. *Effectiveness of Oral Hygiene with Chlorhexidine Mouthwash with 0.12% and 0.2% Concentration on Incidence of Ventilator Associated Pneumonia (VAP) in Intubated Patients – A Parallel arm Double Blind Randomized Controlled Trial.* Annals of International Medical and Dental Research. 2021;7(3). [doi:10.21276/aimdr.2021.7.3.AN2](https://doi.org/10.21276/aimdr.2021.7.3.AN2)

**Data note:** `Data/Data form Chlorhexidine Trial.xlsx` holds 106 patients × 85 variables (trial arm, age, gender, APACHE II, and daily TLC, CPIS, chest X-ray, ABG, culture, oral microbial load and ulcer readings). It contains no names or patient identifiers. It is published here with permission from the trial's co-investigator, Dr. Akash Prabhune; rights to the data remain with the trial investigators.

---

## 📂 **Repository Contents**
```
📦 Survival-Analysis-of-Chlorhexidine-Trial
├── chlorhexidine_survival_analysis.ipynb   # Main analysis notebook
├── requirements.txt                        # Dependencies
├── README.md                               # Documentation
├── LICENSE                                 # MIT (code only)
└── Data/
    └── Data form Chlorhexidine Trial.xlsx  # De-identified trial dataset
```

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
git clone https://github.com/drvnv2000-lab/Survival-Analysis-of-Chlorhexidine-Trial.git
cd Survival-Analysis-of-Chlorhexidine-Trial
```

### **2. Install dependencies**
```bash
pip install -r requirements.txt
```

### **3. Run the notebook**
Open `chlorhexidine_survival_analysis.ipynb` in Jupyter, VS Code or Google Colab and run all cells from the repository root (the notebook reads `Data/Data form Chlorhexidine Trial.xlsx`).

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

The code in this project is licensed under the MIT License.
Use freely for academic, research, or professional work.
The MIT License does not cover the trial dataset; see **Source Study & Data** above.


### Author 

## Dr. Varad Vaidya
Clinical Pharmacist | Healthcare Data Analyst | Artificial Intelligence | Data Science

Specializing in hospital data modelling, survival statistics, clinical research, Artificial Intelligence and Data Science.

