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
│   ├── Delivery_Logistics.csv                                 # Multi-carrier shipment telematics
│   ├── README.md                                              # Detailed Week 2 documentation
│   ├── data_cleaning_and_preprocessing.ipynb                  # Preprocessing & cleaning Jupyter Notebook
│   ├── week-2 task.txt                                        # Task guidelines & evaluation criteria
│   └── Week_2_Data_Collection_Cleaning_and_Preprocessing_Report.docx # Primary Executive Word Report
│
├── week-3/                                                    # Week 3: Advanced Data Analysis and Visualization
│   ├── Delivery_Logistics.csv                                 # Indian Logistics Operations Dataset (25,000 records)
│   ├── README.md                                              # Detailed Week 3 documentation & visual justifications
│   ├── advanced_data_analysis_and_visualization.ipynb         # Fully executed Jupyter Notebook (EDA & 9 Visualizations)
│   ├── week-3 task.txt                                        # Task guidelines & evaluation criteria
│   └── Week_3_Advanced_Data_Analysis_and_Visualization_Report.docx # Primary Executive Word Report (3.26 MB)
│
├── week-4/                                                    # Week 4: Final Capstone & Business Telemetry
│   └── week-4 task.txt                                        # Task requirements
│
├── .gitignore
└── README.md
```

---

## 🚀 Week 3 Highlights: Advanced Data Analysis & Visualization

- **Dataset**: `Delivery_Logistics.csv` (25,000 dispatches across 9 Indian 3PL carriers, 6 vehicle classes, 4 delivery modes, and 5 Indian regions).
- **Core Statistical Findings**:
  - Distance: Mean = 150.39 km, Median = 151.00 km, Skew = +0.002.
  - Package Weight: Mean = 25.15 kg, Median = 25.15 kg, Skew = -0.003.
  - Delivery Cost: Mean = ₹864.94, Median = ₹867.54, Skew = +0.001.
  - Cost per KM: Median = ₹5.74/km, Mean = ₹7.04/km (Skew = +6.383 due to short-haul base pricing).
  - Distance vs Cost Correlation: Pearson $r = 0.991, p < 0.001$.
- **9 Methodologically Justified Visualizations**:
  1. *Univariate Density & Skewness*: Histograms + KDE + Boxplots for distance, weight, and cost.
  2. *Multivariate Correlation Matrix*: Triangular heatmap capturing pairwise linear associations.
  3. *3PL Carrier Benchmark*: 4D Bubble chart (Delay % vs CSAT vs Avg Cost vs Failure %).
  4. *Faceted Mode Vulnerability*: Regional catplot isolating Express failure across Indian corridors.
  5. *Meteorological Shocks*: Dual-panel delay bar chart + split violin plot of CSAT dispersion.
  6. *Transportation Cost Function*: OLS regression with 95% CI band and residual error diagnostics.
  7. *Vehicle Fleet Efficiency*: Paired comparison of EV green fleets vs ICE combustion fleets.
  8. *Regional Density Heatmap*: Cross-tabulation matrix of shipment volume across Indian regions and carriers.
  9. *Customer Satisfaction Degradation*: 100% stacked bar chart + error-bar rating collapse curves.

---

## 🛠️ Tech Stack & Tools
- **Language**: Python 3.10+
- **Data Analysis & Modeling**: `pandas`, `numpy`, `scipy`, `scikit-learn`
- **Data Visualization**: `matplotlib`, `seaborn`
- **Environment**: Jupyter Notebook (`.ipynb`)
- **Reporting**: Microsoft Word (`python-docx`)
