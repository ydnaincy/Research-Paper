# Time-Aware Random Forest for Solar Power Forecasting 🌞

This repository presents a lightweight, interpretable, and highly accurate **Time-Aware Random Forest Regression (RFR)** model for **minute-ahead AC power forecasting** in Indian solar farms. Developed using synchronized power and weather datasets, this solution offers near real-time performance with sub-percent error rates while remaining deployable on low-resource edge devices.

## 📌 Key Highlights

- **Model Type**: Time-aware Random Forest Regressor
- **Use Case**: Minute-ahead AC power forecasting in Indian solar farms
- **Accuracy**:
  - RMSE: `0.00048`
  - MAPE: `0.069%`
  - R²: `0.99996`
- **Data Used**: Open-source power and weather sensor datasets from Kaggle
- **Deployment Ready**: Works on CPU-based systems, suitable for edge devices
- **Interpretability**: Feature importance scores ensure transparency

---

🧪 Dataset
Source: Kaggle - Solar Power Generation Data

Files Used:
Plant_1_Generation_Data.csv
Plant_1_Weather_Sensor_Data.csv
Total Records: 68,774 (1-minute resolution)
Time Span: 15 May – 17 June 2020

🔍 Features Used

Power Metrics: DC_POWER, AC_POWER, DAILY_YIELD, TOTAL_YIELD
Weather Features: IRRADIATION, MODULE_TEMPERATURE, AMBIENT_TEMPERATURE
Temporal Features: HOUR, DAY, MONTH, DAY_OF_WEEK
Cyclical Encoding: Hour and month values to capture periodic patterns

🛠️ Methodology

Data Merging using PLANT_ID and DATE_TIME

Feature Engineering:
Cyclical time encodings
STL (Seasonal-Trend decomposition using Loess)

Model Training:
Random Forest Regression
GridSearchCV for hyperparameter tuning

Evaluation Metrics:
RMSE, MAE, MAPE, EVS, R²

Interpretability:
Gini importance for feature contribution analysis
Residual analysis and temporal error trends

📈 Results

Configuration	MAE	RMSE	MAPE (%)
Full Model	9.07e-05	0.00048	0.069
Without Time Features	1.32e-04	0.00063	0.095
Without Weather Inputs	2.78e-04	0.00115	0.217
Without DC_POWER	3.46e-03	0.00982	3.564
Basic Only	4.92e-03	0.01234	4.981

📊 Visualizations

📉 Feature Importance: DC_POWER (83%) dominates; irradiation, module temperature follow.
🟢 Residual Distribution: Centered around zero, minimal bias.
🔍 Correlation Plot: Correlation coefficient = 0.99997 between actual and predicted values.

🚀 Getting Started
1. Clone the Repository
bash
Copy
Edit
git clone https://github.com/your-username/solar-forecast-rfr.git
cd solar-forecast-rfr
2. Install Requirements
bash
Copy
Edit
pip install -r requirements.txt
3. Run the Model Notebook


⚙️ Requirements

Python ≥ 3.7
scikit-learn
pandas
numpy
matplotlib
seaborn
statsmodels
See requirements.txt for details.

📚 Citation
If you use this model or build on it, please cite:

Khurmia S., Bhartia S., Arora V., Sharma P., Yadav N., Kumar A. "A Time-Aware Random Forest Regression Model for High-Accuracy AC Power Forecasting in Indian Solar Farms", IGDTUW, 2025.

💡 Future Work

Add spatial modeling using Graph Neural Networks (GNNs)
Fuse satellite data (cloud vectors, aerosol indices)
Develop lightweight versions for edge/IoT deployment
Explore hybrid architectures: RFR + LSTM/CNN

👩‍💻 Contributors

Simer Khurmia
Surbhi Bhartia
Vidushi Arora
Prisha Sharma
Naincy Yadav
Ashwni Kumar

📄 License
This project is licensed under the MIT License. See LICENSE for details.

---






