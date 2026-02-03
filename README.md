Restaurant Wait Time Prediction System

End-to-End ML + Flask API + Streamlit Web Application
=======================================================

1. Machine Learning Pipeline
==============================
• Synthetic dataset generation with nulls, duplicates, and outliers/nulls
• Data inspection using head(), info(), describe()
• Preprocessing: missing values, duplicate removal, IQR-based outlier treatment
• Feature engineering: is_peak_hour, load_per_staff
• Model: Random Forest Regressor with GridSearchCV
• Evaluation: R², MAE, RMSE
• Model persistence using joblib (.pkl)

2. Flask Backend API
========================
• Flask exposes trained ML model as REST API
• /predict endpoint accepts JSON or form input
• Applies same feature engineering similar to ML pipeline /model.py
• Returns predicted waiting time
• Ensures training-serving consistency

3. Streamlit Frontend Application
===================================
• Interactive web UI for restaurant managers
• Green-themed responsive design
• Tabbed input layout (Time, Capacity, Operations)
• Sends input to Flask API using POST requests
• Displays real-time prediction with error handling


Deployment Architecture Flow
=============================

┌──────────────┐
│  Streamlit   │
│  Web App UI  │
└──────┬───────┘
       │  (JSON via POST)
       ↓
┌──────────────┐
│  Flask API   │
│  /predict    │
└──────┬───────┘
       │
       ↓
┌──────────────┐
│ ML Model     │
│ best_model   │
│ (.pkl file)  │
└──────────────┘


How to test this project :
=========================

Two ways
1. we can test directly using flaskapi
Please check run_instruction_api_htmlform_directly.txt

2. we can test via streamlit app
Please check run_instruction_streamlit_app.txt
