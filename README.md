# ⚡ Predictive Power Modeling for Telecom Base Stations

**Team:** AI_KON  
**Members:** Jeyadev K, Amrutha A G, Abhishek Reddy, Vansham Aggarwal  

***

## 📘 Project Overview & Problem Statement

Telecommunication companies face **significant operational costs** due to the power required to run their extensive network of base stations.

The goal of this project is to **accurately predict the average monthly power consumption** of a base station based on its **operational characteristics**, such as:
- Location
- Network technology
- Data traffic

By developing a **robust machine learning model**, this project enables reliable power consumption forecasts — driving better **financial planning**, **energy optimization**, and **operational efficiency**.

***

## 💼 Use Case & Business Impact

### 🎯 Primary Use Case
**Predictive Analytics for Telecom Infrastructure Management**

### 💡 Business Impact
- **🔋 OpEx Reduction & Budgeting:** Provides accurate energy forecasts to design precise budgets and avoid unexpected overages.
- **🏗️ CapEx Optimization:** Helps correctly size power infrastructure (e.g., solar panels) for new sites, reducing unnecessary expenditure.
- **⚙️ Proactive Maintenance:** Flags base stations consuming more power than predicted, serving as an early warning for potential equipment faults.
- **🌱 Data-Driven Sustainability:** Quantifies the energy efficiency and savings achieved through renewable sources, supporting ESG (Environmental, Social, and Governance) goals.

***

## ⚙️ Installation

Follow these steps to set up the project locally:

### 1️⃣ Clone the Repository
```bash
git clone [Your-GitLab-Repo-URL]
cd AI_KON
```

### 2️⃣ Create a Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate # On Windows, use: venv\Scripts\activate
```

### 3️⃣ Install Dependencies
```bash
pip install -r requirements.txt
```

***

## 🚀 How to Use the Project

You can use the project in two ways — by training the model yourself or using the pre-trained version.
### 🧠 Option 1: Run the Full Training Notebook
To view the complete end-to-end pipeline (data analysis → model training → evaluation):
```bash
jupyter notebook notebooks/Predicting BTS Power Consumption.ipynb
```
This notebook:
- Performs data preprocessing and feature engineering.
- Runs multi-model GridSearchCV for hyperparameter optimization.
- Conducts error analysisSaves the trained model automatically in the models/ directory.

### ⚡ Option 2: Use the Pre-Trained Model for Predictions
If you prefer instant predictions, use the pre-trained model:Example Python Script

```python
import joblib
import pandas as pd

# Load the pre-trained model
loaded_model = joblib.load('models/bts_champion_model.joblib')

# Create new input data
input_data = {
    'Power_Source': 'Solar',
    'Site_Category': 'Urban',
    'Network_Technology': '5G',
    'Downlink': 2100.5,
    'Uplink': 950.2
}

# Convert to DataFrame
input_df = pd.DataFrame([input_data])

# Add derived features
input_df['Total_Traffic'] = input_df['Downlink'] + input_df['Uplink']

# Predict average power consumption
predicted_power = loaded_model.predict(input_df)

print(f"Predicted Average Power Consumption: {predicted_power[0]:.2f} Watts")

```

***

## 📊 Model Performance
The champion model, selected using GridSearchCV, demonstrates excellent predictive accuracy and strong generalization.

| Metric | Score | Description |
| :--- | :--- | :--- |
| R² (Coefficient of Determination) | 0.9892 | Indicates an extremely strong statistical fit |
| Mean Absolute Error (MAE) | ≈ 79 | WattsAverage prediction error |
| Custom Accuracy (±10%) | 84% | 84% of predictions fall within tolerance range |

🔍__Key Insight:__ Error analysis revealed that larger deviations occur primarily with 5G sites, suggesting the need for more 5G-specific data — not a model flaw, but a data distribution challenge.
***

## 🧩 Project Highlights
- ✅ Multi-model evaluation using GridSearchCV
- ✅ Robust data preprocessing and feature engineering pipeline
- ✅ Supports scalable model deployment
- ✅ Designed for real-world telecom energy optimization

***
## 🌐 Future Scope
- Integrate real-time data streams for live power forecasting
- Incorporate weather and temperature variables for greater accuracy
- Deploy as a REST API or cloud-based monitoring dashboard
***

## 🏁 Conclusion

This project demonstrates how AI-driven predictive modeling can revolutionize telecom infrastructure management by reducing operational costs, improving sustainability, and enabling data-driven decision-making.

_Predict. Optimize. Sustain._

***
### 👨‍💻 Developed by Team AI_KON
Jeyadev K | Amrutha A G | Abhishek Reddy | Vansham Aggarwal
