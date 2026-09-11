# YUVA Internship: Logistics Data Analyst Intern

This repository contains the end-to-end deliverables, analytical models, datasets, and strategic reports developed during the **Logistics Data Analyst Internship** under the YUVA program.

---

## 📅 Project Roadmap & Structure

```
├── week-1/                                                    # Week 1: Strategic Planning and Data Exploration
│   ├── Delivery_Logistics.csv                                 # 25,000 shipment dispatch records
│   ├── README.md                                              # Detailed Week 1 documentation
│   ├── strategic_analysis.ipynb                              # Pre-executed Jupyter Notebook (EDA, KPIs & ML models)
│   ├── week 1 task.txt                                        # Task guidelines & evaluation criteria
│   └── Week_1_Strategic_Planning_and_Data_Exploration_Report.docx # Primary Executive Word Report
│
├── week-2/                                                    # Week 2: Data Collection, Cleaning, and Preprocessing
│   └── week-2 task.txt                                        # Task requirements
│
├── week-3/                                                    # Week 3: Advanced Analytics & Optimization
│   └── week-3 task.txt                                        # Task requirements
│
├── week-4/                                                    # Week 4: Final Capstone & Business Telemetry
│   └── week-4 task.txt                                        # Task requirements
│
├── .gitignore
└── README.md
```

---

## 🚀 Week 1 Highlights: Strategic Planning & Data Exploration

- **Dataset**: `Delivery_Logistics.csv` (25,000 shipment dispatches across 9 3PL partners, 6 vehicle classes, 4 delivery modes, and 5 Indian regions).
- **Core Baseline KPIs**:
  - **On-Time Delivery Rate (OTDR)**: **73.32%**
  - **Shipment Delay Rate**: **21.36%**
  - **Shipment Failure Rate (SFR)**: **5.31%**
  - **Average Delivery Cost**: **₹864.94** (Cost per KM: **₹5.75/km**)
  - **Customer Satisfaction (CSAT)**: **3.67 / 5.0 ★** (Delivered: **4.21 ★**, Delayed: **2.40 ★**, Failed: **1.31 ★**)
- **Critical Insights**:
  - **Express Fulfillment Crisis**: 73.78% delay rate and 14.42% complete failure rate in Express orders.
  - **Weather Impact**: Stormy weather pushes delay rate to 41.45%; rainy weather causes 37.35% delays.
  - **Carrier Benchmark**: Delhivery and FedEx lead the network in reliability and value; Xpressbees exhibits highest operational risk.
  - **Fleet Electrification**: EV bikes and EV vans match combustion vehicles with equal reliability and cost efficiency.
- **Machine Learning Models Built**:
  - **Random Forest Delay Classifier**: ROC-AUC = **0.9644**, Accuracy = **89.62%**.
  - **Cost Regressor (OLS)**: $R^2 = \mathbf{0.9999}$, RMSE = **₹4.67**.
  - **Carrier K-Means Clustering**: Partitions carriers into 3 performance clusters.

---

## 🛠️ Tech Stack & Tools
- **Language**: Python 3.10+
- **Data Analysis & Modeling**: `pandas`, `numpy`, `scikit-learn`
- **Data Visualization**: `matplotlib`, `seaborn`
- **Environment**: Jupyter Notebook (`.ipynb`)
- **Reporting**: Microsoft Word (`python-docx`)
