# 📘 Chronic Kidney Disease (CKD) Analysis

## 📌 Project Overview
This project performs **Exploratory Data Analysis (EDA)** and builds predictive models on the **Chronic Kidney Disease (CKD)** dataset.  
The aim is to analyze patient medical records, identify important risk factors, and classify patients into CKD vs Non-CKD.  

Key objectives:
- Explore patient demographics, lab results, and symptoms.  
- Identify correlations between features like blood pressure, blood urea, serum creatinine, and CKD.  
- Build machine learning models to classify CKD vs non-CKD.  

---

## 📂 Dataset
**File:** `kidney_disease.csv`  
**Rows:** 400 (patients)  
**Columns:** 26  

### Key Columns:
- **Demographics**: `age`, `bp` (blood pressure)  
- **Urine Tests**: `sg` (specific gravity), `al` (albumin), `su` (sugar), `rbc` (red blood cells), `pc` (pus cell), `pcc` (pus cell clumps), `ba` (bacteria)  
- **Biochemistry**: `bgr` (blood glucose random), `bu` (blood urea), `sc` (serum creatinine), `sod` (sodium), `pot` (potassium), `hemo` (hemoglobin)  
- **Counts**: `pcv` (packed cell volume), `wc` (white blood cell count), `rc` (red blood cell count)  
- **Medical History**: `htn` (hypertension), `dm` (diabetes mellitus), `cad` (coronary artery disease)  
- **Symptoms**: `appet` (appetite), `pe` (pedal edema), `ane` (anemia)  
- **Target**: `classification` (CKD / not CKD)  

---

## ⚙️ Tech Stack
- **Python** (data analysis & ML)  
- **Pandas / NumPy** (data wrangling)  
- **Matplotlib / Seaborn** (visualizations)  
- **Scikit-learn** (train-test split, Random Forest model)  
- **Jupyter Notebook** (EDA workflow)  

---

## 📊 Exploratory Data Analysis (EDA)
The notebook `EDA-Chronic data.ipynb` covers:
1. **Data Cleaning**  
   - Handling missing values (`NaN`)  
   - Converting categorical values (`yes/no`, `normal/abnormal`) into numeric  
   - Fixing inconsistent entries  

2. **Statistical Analysis**  
   - Distribution of age, blood pressure, serum creatinine  
   - CKD vs non-CKD comparison  

3. **Visual Insights**  
   - Boxplots for `age`, `bp`, `hemo`  
   - Countplots for `hypertension`, `diabetes`, `anemia`  
   - Correlation heatmaps  

---

## 🤖 Modeling
- **Features**: All medical attributes except `id`.  
- **Target**: `classification` (CKD = 1, Not CKD = 0).  
- **Train-Test Split**: 70% training, 30% testing.  
- **Model**: RandomForestClassifier.  
- **Evaluation**: Accuracy, Precision, Recall, F1-score.  

---

## 🚀 How to Run
1. Clone the repo and open the notebook:
   ```bash
   git clone <repo-url>
   cd Chronic-Kidney-Disease
   jupyter notebook "EDA-Chronic data.ipynb"
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Run all cells in the notebook.  

---

## 📈 Insights
- **High blood pressure, high blood urea, and low hemoglobin are strong CKD indicators.**  
- **Hypertension and diabetes are major risk factors.**  
- **Random Forest achieved >90% accuracy** in predicting CKD.  

---

## ✅ Next Steps
- Tune hyperparameters for RandomForest & try XGBoost.  
- Handle class imbalance with SMOTE.  
- Build a **Streamlit dashboard** for medical professionals.  
