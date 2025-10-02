# ✈️ Travel Data Analysis (EDA Project)

## 📖 Overview
This project performs **Exploratory Data Analysis (EDA)** on a travel dataset (`Travel.csv`).  
The goal of this analysis is to **understand customer behavior, travel preferences, and insights** that may help a travel company design better marketing strategies and improve customer targeting.  

The Jupyter Notebook (`4. EDA-Travel.ipynb`) contains step-by-step data exploration, cleaning, visualization, and business insights.

---

## 📂 Dataset Information
The dataset contains **customer travel and sales-related attributes**. Some of the key features include:

- `Age` – Age of the customer  
- `TypeOfContact` – How the customer was contacted (Company Invited / Self Enquiry)  
- `CityTier` – Customer’s city tier (1, 2, or 3)  
- `Occupation` – Type of occupation (Salaried, Small Business, Free Lancer, etc.)  
- `Gender` – Male / Female  
- `ProductPitched` – Travel package pitched to the customer  
- `PreferredPropertyStar` – Preferred hotel star rating (3, 4, 5, etc.)  
- `MaritalStatus` – Customer’s marital status (Single, Married, Divorced)  
- `NumberOfTrips` – Trips taken in a year  
- `Passport` – Whether customer has a passport (1 = Yes, 0 = No)  
- `PitchSatisfactionScore` – Satisfaction score of the sales pitch  
- `MonthlyIncome` – Customer’s monthly income  

Target column:
- `ProdTaken` – Whether the customer purchased the travel package (1 = Yes, 0 = No)

---

## 🔎 Analysis Performed
The following analyses were carried out in the notebook:

1. **Data Cleaning & Preprocessing**
   - Handled missing values  
   - Converted categorical features into proper data types  
   - Removed irrelevant or redundant information  

2. **Univariate Analysis**
   - Age distribution (30-40 age group travels more)  
   - Distribution of categorical variables (Occupation, Marital Status, Gender, etc.)  

3. **Bivariate Analysis**
   - Relationship between age groups and product purchase  
   - Impact of income, occupation, and marital status on product adoption  
   - Customer preferences for property star ratings and package type  

4. **Business Insights**
   - Middle-aged customers (30–40) are more likely to purchase packages  
   - Salaried employees and small business owners are strong target groups  
   - Customers with passports and higher income are more inclined to buy travel packages  
   - Satisfaction with sales pitch positively influences product adoption  

---

## 📊 Key Insights
- ✅ **30–40 age group** shows the highest travel activity.  
- ✅ **Salaried professionals** are more likely to purchase packages.  
- ✅ **Customers with passports** and higher income show a stronger inclination towards travel products.  
- ✅ **Pitch satisfaction** plays a significant role in conversions.  

---

## ⚙️ How to Run This Project
Follow these steps to run the analysis on your local machine:

### 1. Clone the repository
```bash
git clone https://github.com/your-username/Travel-EDA.git
cd Travel-EDA
```

### 2. Install dependencies
Make sure you have **Python 3.x** installed. Then install the required libraries:
```bash
pip install -r requirements.txt
```

### 3. Run Jupyter Notebook
```bash
jupyter notebook "4. EDA-Travel.ipynb"
```

---

## 📦 Requirements
Create a `requirements.txt` file with the following (if not already included):

```
pandas
numpy
matplotlib
seaborn
jupyter
```

---

## 📌 Project Structure
```
📂 Travel-EDA
 ┣ 📜 4. EDA-Travel.ipynb   # Jupyter Notebook with analysis
 ┣ 📜 Travel.csv            # Dataset
 ┣ 📜 README.md             # Project documentation
 ┗ 📜 requirements.txt      # Dependencies
```

---

## 🚀 Future Work
- Perform feature engineering for predictive modeling  
- Build ML models to predict **travel package adoption (ProdTaken)**  
- Apply clustering to segment customers based on travel preferences  

---

## 👨‍💻 Author
- **Your Name (replace this)**  
  🎓 Data Enthusiast | 📊 Aspiring Data Analyst  
