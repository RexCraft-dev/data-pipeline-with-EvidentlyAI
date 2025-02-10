# Financial Data Drift Analysis with Evidently AI & Logistic Regression
This project uses Evidently AI and Logistic Regression to monitor financial data quality, detect drift, and track model performance over time. The model is trained on Google (GOOG) stock data from 2011 to 2024, using yearly batch processing.

## 📌 Features
- 📊 Fetches GOOG stock data from yfinance
- 🔍 Detects data quality issues using Evidently AI
- ⚖️ Trains a Logistic Regression model to predict stock movement (up/down)
- 📈 Monitors drift in financial indicators across years
- 📑 Logs Evidently AI reports for:
  - Data Quality
  - Feature Drift
  - Target Drift
  
## 📌 Installation
1️⃣ Clone the Repository
```git clone https://github.com/yourusername/yourrepo.git
cd yourrepo

2️⃣ Install Required Dependencies
```pip install -r requirements.txt
OR manually install:
```pip install evidently yfinance pandas numpy scikit-learn matplotlib

## 📌 How It Works
1️⃣ Data Collection & Preprocessing
- Downloads Google stock data from 2011 to 2024 via yfinance
- Splits data into yearly batches
- Calculates VWAP (Volume Weighted Average Price)
- Randomly injects missing values for data quality testing
- Standardizes numerical features (Open, High, Low, Close, Volume, VWAP)
2️⃣ Model Training & Prediction
- Uses past 2 years of data as reference training data
- Trains a Logistic Regression model to predict price direction
- Tests the model on the next year’s data
- Stores yearly accuracy scores
3️⃣ Evidently AI Reports for Monitoring
- The following reports are generated per year and stored in lists:

🛠 Data Quality Report (`quality_reports`)
📊 Feature Drift Report (`drift_reports`)
🎯 Target Drift Report (`target_drift_reports`)

This will: ✅ Train & evaluate the model across yearly batches
✅ Generate Evidently AI reports for each year
✅ Print accuracy scores per year

📌 Example Output
```Processing Year: 2020...
Accuracy for Year 2020: 0.5521
Processing Year: 2021...
Accuracy for Year 2021: 0.5634
Processing Year: 2022...
Accuracy for Year 2022: 0.4792
Processing Year: 2023...
Accuracy for Year 2023: 0.3910  <-- Significant drop, drift detected!

## 📌 Next Steps
🔹 Visualize Predictions: Compare actual vs. predicted values over time
🔹 Log Evidently AI reports in a structured workspace for ongoing monitoring
🔹 Explore additional features (momentum indicators, news sentiment, etc.)
