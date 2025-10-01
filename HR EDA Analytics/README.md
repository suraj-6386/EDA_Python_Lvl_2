# 📘 HR Analytics Project

## 📌 Project Overview
This project performs **Exploratory Data Analysis (EDA)** and **basic modeling** on an HR dataset to uncover insights related to employee performance, engagement, attrition, and workforce trends. The dataset includes employee demographics, compensation, performance ratings, engagement survey results, and termination details.  

The project answers key HR questions such as:
- Which departments/employees have the most absences?  
- What are the top reasons for employee terminations?  
- What is the relationship between salary, performance, and engagement?  
- Predictive modeling: Can we identify employees at risk of attrition?  

---

## 📂 Dataset
**File:** `HRDataset_v14.csv`  
**Rows:** ~310  
**Columns:** 36  

### Key Columns:
- **Employee Information**: `Employee_Name`, `EmpID`, `Position`, `Department`, `ManagerName`  
- **Compensation & Performance**: `Salary`, `PerformanceScore`, `PerfScoreID`, `SpecialProjectsCount`  
- **Engagement & Absences**: `EngagementSurvey`, `EmpSatisfaction`, `Absences`, `DaysLateLast30`  
- **Termination Data**: `Termd`, `TermReason`, `TermType`  
- **Demographics**: `GenderID`, `MarriedID`, `MaritalStatusID`, `FromDiversityJobFairID`  

---

## ⚙️ Tech Stack
- **Python** (data analysis & modeling)  
- **Pandas** (data manipulation)  
- **NumPy** (numeric computations)  
- **Matplotlib / Seaborn** (visualizations)  
- **Scikit-learn** (train-test split, modeling)  
- **Jupyter Notebook** (EDA workflow)  

---

## 📊 Exploratory Data Analysis (EDA)
The notebook `2. EDA-HR Analytics.ipynb` covers:
1. **Data Cleaning**  
   - Handling missing values  
   - Fixing inconsistent formats  

2. **Descriptive Statistics**  
   - Salary distribution across positions  
   - Engagement survey scores by department  

3. **Visual Insights**  
   - Barplots for termination reasons by position  
   - Boxplots of absences by gender  
   - Correlation heatmaps  

4. **Groupby Analysis**  
   - Avg engagement per department  
   - Max salary & min days late per position  
   - Terminations by reason and position  

---

## 🤖 Modeling
- **Train-test split** applied to relevant features (e.g., `Salary`, `Absences`, `EngagementSurvey`).  
- **RandomForestClassifier** built to predict termination (`Termd`).  
- Model evaluation with **accuracy** and **classification report**.  

---

## 🚀 How to Run
1. Clone the repo and open the notebook:
   ```bash
   git clone <repo-url>
   cd HR-Analytics
   jupyter notebook "2. EDA-HR Analytics.ipynb"
   ```
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Run all cells in the notebook.  

---

## 📈 Insights
- **Most common termination reason**: Attendance & performance.  
- **Department with highest absences**: Production.  
- **Employees with higher salaries & engagement scores have fewer terminations.**  
- **Predictive model achieved >80% accuracy in classifying terminations.**  

---

## ✅ Next Steps
- Improve feature engineering (encode categorical columns like Position, TermReason).  
- Test different models (Logistic Regression, XGBoost).  
- Deploy as an **HR analytics dashboard** using Streamlit/PowerBI.  
