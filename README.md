# 📊 Customer Churn & LTV Analytics & Prediction Platform

An end-to-end full-stack analytics/prediction solution to extract, engineer, and analyze customer churn and lifetime value (LTV) using SQL, Python, and deep learning — with an interactive Streamlit dashboard and SHAP explainability.

---

## 📁 Project Structure

```
.
├── datasets/
│   ├── csv-files/                 # Raw CRM & ERP data (bronze/silver/gold layers)
│   └── DataWarehouseAnalytics.bak # Backup of MySQL data warehouse
├── scripts/
│   ├── *.sql                      # Modular SQL scripts for feature engineering
│   ├── import_gold_to_mysql.py   # Load CSVs into MySQL
│   └── python_integration.py     # Feature generation, LTV calculation
├── features_customer_churn_ltv.csv # Final ML-ready dataset
├── churn_model.pt                # Trained single-task PyTorch model
├── multitask_model.pt           # Trained multi-task PyTorch model (churn + LTV)
├── scaler.pkl                    # StandardScaler for model inputs
├── train_multitask_model.py     # Script to train multi-task model
├── test_model.py                # Test script to run predictions from CLI
├── app.py                        # Streamlit dashboard (UI + SHAP)
├── requirements.txt
└── README.md
```

---

## 🧠 Key Highlights

### ✅ SQL Feature Engineering (First Phase)
- 14+ modular SQL scripts for customer segmentation, order frequency, LTV, churn flags, and recency.
- Designed using bronze → silver → gold data warehouse structure.
- MySQL integration with automated table creation from raw CSVs.

### 🔄 ETL + Python Integration
- Automated ingestion pipeline to load CSVs → MySQL using `import_gold_to_mysql.py`.
- EDA and feature joining scripts in Python to generate final `features_customer_churn_ltv.csv`.

### 🔮 Deep Learning (Multi-Task Learning)
- Trained PyTorch model to predict both churn (classification) and LTV (regression) in a **single network**.
- Balanced dataset using upsampling; multi-task loss optimized jointly.
- Achieved significant model generalization and business value prediction.

### 🧠 SHAP Explainability
- Integrated SHAP bar plots to explain churn predictions for individual customers.
- Lightweight `ExactExplainer` used for fast explanations.

### 📊 Streamlit Dashboard (Interactive UI)
- Filters for churn status, LTV range.
- Visuals: bar charts, scatter plots, box plots via Plotly.
- Real-time churn + LTV prediction with SHAP insights.
- Borderline warnings & input validation to guide non-technical users.

---

## 🚀 Run Locally

### 1. Install Requirements
```bash
pip install -r requirements.txt
```

### 2. Train the Model
```bash
python train_multitask_model.py
```

### 3. Test the Model
```bash
python test_model.py
```

### 4. Launch Streamlit Dashboard
```bash
streamlit run app.py
```

---

## 📌 Screenshots
<img width="1916" height="1066" alt="cc" src="https://github.com/user-attachments/assets/0bc67653-39df-4fdf-903a-68c8e605b701" />
<img width="1918" height="1070" alt="cc1" src="https://github.com/user-attachments/assets/c6618498-2726-4ec0-8034-3e7a836af681" />
<img width="1910" height="1070" alt="cc2" src="https://github.com/user-attachments/assets/1a0ea685-9d29-4477-831e-1b32e2db8d9b" />
<img width="1897" height="1063" alt="cc3" src="https://github.com/user-attachments/assets/9f2aac4e-6250-4ad0-944c-7a6bddf60828" />


---

## View Live
[Streamlit](https://customer-churn-ltv-prediction-platform-prudhviraj.streamlit.app/)
