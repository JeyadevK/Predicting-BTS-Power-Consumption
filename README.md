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
cd bts-power-prediction

2️⃣ **Create a Virtual Environment (Recommended)
```bash
python -m venv venv
source venv/bin/activate
# On Windows, use: venv\Scripts\activate
3️⃣ Install DependenciesBashpip install -r requirements.txt
🚀 How to Use the ProjectYou can use the project in two ways — by training the model yourself or using the pre-trained version.🧠 Option 1: Run the Full Training NotebookTo view the complete end-to-end pipeline (data analysis → model training → evaluation):Bashjupyter notebook notebooks/Predicting BTS Power Consumption.ipynb
This notebook:Performs data preprocessing and feature engineeringRuns multi-model GridSearchCV for hyperparameter optimizationConducts error analysisSaves the trained model automatically in the models/ directory⚡ Option 2: Use the Pre-Trained Model for PredictionsIf you prefer instant predictions, use the pre-trained model:Example Python ScriptPythonimport joblib
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
📊 Model PerformanceThe champion model, selected using GridSearchCV, demonstrates excellent predictive accuracy and strong generalization.MetricScoreDescriptionR² (Coefficient of Determination)0.9892Indicates an extremely strong statistical fitMean Absolute Error (MAE)≈ 79 WattsAverage prediction errorCustom Accuracy (±10%)84%84% of predictions fall within tolerance range🔍 Key Insight: Error analysis revealed that larger deviations occur primarily with 5G sites, suggesting the need for more 5G-specific data — not a model flaw, but a data distribution challenge.🧩 Project Highlights✅ Multi-model evaluation using GridSearchCV✅ Robust data preprocessing and feature engineering pipeline✅ Supports scalable model deployment✅ Designed for real-world telecom energy optimization🌐 Future ScopeIntegrate real-time data streams for live power forecastingIncorporate weather and temperature variables for greater accuracyDeploy as a REST API or cloud-based monitoring dashboard🏁 ConclusionThis project demonstrates how AI-driven predictive modeling can revolutionize telecom infrastructure management by reducing operational costs, improving sustainability, and enabling data-driven decision-making.Predict. Optimize. Sustain.👨‍💻 Developed by Team AI_KONJeyadev K | Amrutha A G | Abhishek Reddy | Vansham Aggarwal
