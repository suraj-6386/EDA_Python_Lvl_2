# Student Performance EDA Project

## 📌 Project Overview
This project focuses on **Exploratory Data Analysis (EDA)** of a **Student Performance dataset**.  
The dataset contains **649 rows and 1 columns**, covering demographic, social, and academic information about students.  
The primary goal is to uncover insights that explain factors influencing students' academic performance and grades.

## 📂 Files
- **Notebook:** `5. EDA-Student Performance.ipynb` → Complete code and step-by-step EDA.
- **Dataset:** `student-por.csv` → Raw dataset containing student information.

## 🎯 Objectives / Questions Explored
1. How do demographic factors (gender, age, parental education) influence student performance?
2. Is there a relationship between study time, absences, and final grades?
3. How do family and social factors (family support, romantic relationships, alcohol consumption) affect grades?
4. What are the strongest predictors of student success in exams?
5. Are there correlations among different grade scores (G1, G2, G3)?

## 🛠️ Steps in Analysis
1. **Data Loading & Inspection**  
   - Loaded the dataset using pandas  
   - Checked dataset shape and first few rows  
   - Examined data types and missing values  

2. **Data Cleaning & Preprocessing**  
   - Handled categorical variables (gender, school, family support, etc.)  
   - Converted numeric columns to appropriate types  
   - Dealt with missing or inconsistent values  

3. **Exploratory Data Analysis (EDA)**  
   - **Univariate analysis**: distribution of grades, age, study time, absences  
   - **Bivariate analysis**: relation between grades and categorical features  
   - **Correlation analysis**: heatmap of numeric features (grades, study time, absences)  

4. **Visualizations**  
   - Histograms & KDE plots for grade distributions  
   - Bar plots for categorical comparisons (gender vs grades, study time vs performance)  
   - Boxplots showing grade spread across categories  
   - Correlation heatmap for identifying key relationships  

5. **Insights & Findings**  
   - Study time and parental support strongly correlate with higher grades  
   - Excessive alcohol consumption shows negative impact on performance  
   - Absences significantly reduce academic scores  
   - Female students tend to perform slightly better in some subjects  
   - Final grade (G3) is highly correlated with G1 and G2 (previous scores)  

## 📊 Key Columns in Dataset
Some important features include:  
- **school** – Student’s school (GP or MS)  
- **sex** – Gender (F/M)  
- **age** – Age of student  
- **studytime** – Weekly study time  
- **failures** – Number of past class failures  
- **famrel** – Quality of family relationships  
- **goout** – Going out with friends  
- **Dalc/Walc** – Alcohol consumption (weekday/weekend)  
- **health** – Current health status  
- **absences** – Number of school absences  
- **G1, G2, G3** – First, second, and final grades  

## 🚀 Outcomes & Recommendations
- Students with consistent study time and fewer absences perform significantly better.  
- Family and social environment play a crucial role in academic success.  
- Schools can improve results by focusing on students with high absences and low study time.  
- Predictive modeling using features like study time, failures, absences, and G1/G2 can accurately forecast final grade (G3).  

## ▶️ How to Run
1. Clone this repository or download the files.  
2. Open the notebook `5. EDA-Student Performance.ipynb` in Jupyter Notebook or JupyterLab.  
3. Install dependencies if needed:  
   ```bash
   pip install pandas numpy matplotlib seaborn plotly
   ```
4. Run all cells to reproduce analysis and visualizations.  

## 📌 Next Steps
- Extend analysis with predictive models (Linear Regression, Random Forest) to forecast final grades.  
- Deploy an interactive dashboard (Streamlit/Plotly Dash) for real-time student performance insights.  
- Compare results with other student performance datasets for cross-validation.  

---
📊 This project is a **major data analysis case study** that highlights skills in **data cleaning, EDA, visualization, and insights generation**.  
Perfect to showcase in your **GitHub portfolio or resume** for Data Analyst / Data Science roles.
