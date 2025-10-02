# ✈️ Flight Price Prediction - Exploratory Data Analysis (EDA)

## 📖 Overview
This project performs **Exploratory Data Analysis (EDA)** on a flight dataset (`flight_price.xlsx`).  
The main goal is to **understand factors affecting flight prices** and prepare the data for predictive modeling.  

The notebook (`6. EDA-Flight Price data.ipynb`) contains step-by-step analysis including:
- Data cleaning & preprocessing
- Univariate, Bivariate & Multivariate analysis
- Feature engineering (`Duration` split into hours/minutes → `Total_Duration_Hours`)
- Train-test split & scaling

---

## 📂 Dataset Information
The dataset consists of flight booking details with the following key features:

- `Airline` – Name of the airline (IndiGo, Air India, Jet Airways, etc.)  
- `Date_of_Journey` – Date when the journey is scheduled  
- `Source` – Source city of the flight  
- `Destination` – Destination city of the flight  
- `Route` – Full route taken by the flight  
- `Dep_Time` – Departure time of the flight  
- `Arrival_Time` – Arrival time of the flight  
- `Duration` – Total flight duration (later split into `duration_hours`, `duration_minutes`, `Total_Duration_Hours`)  
- `Total_Stops` – Number of stops (non-stop, 1 stop, 2 stops, etc.)  
- `Additional_Info` – Extra details about the flight (in-flight meal, baggage, etc.)  
- `Price` – Flight ticket price (Target Variable)

---

## 🔎 Analysis Performed

### 1. Data Cleaning & Preprocessing
- Converted `Date_of_Journey`, `Dep_Time`, and `Arrival_Time` into datetime features.  
- Split `Duration` into `duration_hours` and `duration_minutes`.  
- Created a new column `Total_Duration_Hours`.  
- Handled missing values & categorical encoding.  

### 2. Univariate Analysis (Individual features)
- Distribution of `Price` (right-skewed distribution).  
- Most frequent airlines (IndiGo, Jet Airways dominate).  
- Flight counts by `Source` and `Destination`.  
- Distribution of `Total_Duration_Hours`.  

### 3. Bivariate Analysis (Feature vs Price)
- **Price vs Destination** → Spread & averages across cities.  
- **Price vs Airline** → Certain airlines (Jet Airways, Air India) charge higher prices.  
- **Price vs Source** → Flights from Delhi/Bangalore generally cost more.  
- **Price vs Total Stops** → More stops → lower average ticket prices.  
- **Price vs Duration** → Longer flights tend to cost more.  

### 4. Multivariate Analysis
- **Correlation Heatmap** → Numerical features correlations with `Price`.  
- **Duration vs Stops vs Price** (scatterplot with hue).  
- **Source vs Destination vs Price** (barplot).  
- **Pairplots** for Price, Duration, Stops.  

### 5. Train-Test Split & Scaling
- Separated features (`X`) and target (`y`).  
- Train-test split with 80-20 ratio.  
- StandardScaler applied to numerical features.  

---

## 📊 Key Insights
- Jet Airways and Air India have the highest flight prices.  
- Non-stop flights cost significantly more than those with multiple stops.  
- Flights from major metro cities (Delhi, Bangalore) are costlier.  
- Longer flight durations usually result in higher prices.  
- Ticket price distribution is highly skewed (few very high-value flights).  

---

## ⚙️ How to Run This Project

### 1. Clone the repository
```bash
git clone https://github.com/your-username/Flight-Price-EDA.git
cd Flight-Price-EDA
```

### 2. Install dependencies
Make sure you have **Python 3.x** installed. Then run:
```bash
pip install -r requirements.txt
```

### 3. Run Jupyter Notebook
```bash
jupyter notebook "6. EDA-Flight Price data.ipynb"
```

---

## 📦 Requirements
```
pandas
numpy
matplotlib
seaborn
scikit-learn
jupyter
```

---

## 📌 Project Structure
```
📂 Flight-Price-EDA
 ┣ 📜 6. EDA-Flight Price data.ipynb   # Jupyter Notebook with EDA
 ┣ 📜 flight_price.xlsx                # Dataset
 ┣ 📜 README.md                        # Project documentation
 ┗ 📜 requirements.txt                 # Dependencies
```

---

## 🚀 Future Work
- Apply ML models (Linear Regression, Random Forest, XGBoost) for price prediction.  
- Hyperparameter tuning for best accuracy.  
- Build a web-app to predict flight prices.  

---

## 👨‍💻 Author
- **Your Name (replace this)**  
  🎓 Data Enthusiast | 📊 Aspiring Data Analyst  
