# Week 2: Data Collection, Cleaning, and Preprocessing in Logistics

## 📌 Project Overview
This project delivers the complete data collection, data cleaning, quality profiling, and feature preprocessing pipeline for an enterprise-level multi-carrier logistics network in India. 

The analysis is conducted on **25,000 shipment dispatches** across 9 major third-party logistics (3PL) carriers (**Delhivery, Blue Dart, Xpressbees, Shadowfax, DTDC, Ekart, Ecom Express, FedEx, DHL, and Amazon Logistics**), covering 6 vehicle types (including EV green fleets) and 5 primary Indian economic corridors (North, South, East, West, and Central).

---

## 📁 Repository Structure
```
week-2/
│
├── Delivery_Logistics.csv                                        # Raw dataset (25,000 shipment records)
├── Cleaned_Delivery_Logistics.csv                                # Cleaned and feature-enriched dataset (47 columns)
├── data_cleaning_and_preprocessing.ipynb                        # Interactive Jupyter Notebook (EDA, Data Cleaning & Preprocessing)
├── Week_2_Data_Collection_Cleaning_and_Preprocessing_Report.docx # Primary deliverable: Comprehensive executive Word report
├── week-2 task.txt                                               # Original task guidelines and evaluation criteria
└── README.md                                                     # Project documentation and summary
```

---

## 🎯 Key Project Objectives
1. **Simulate Logistics Data Ingestion**: Ingest multi-carrier shipment telematics and Transport Management System (TMS) data across Indian regional hubs.
2. **Conduct Data Quality Diagnostic Audit**: Screen for missingness mechanisms (MCAR/MAR/MNAR), string formatting anomalies, timestamp placeholders, and surrogate key integrity.
3. **Handle Missing Values & Sensor Failures**: Reconstruct operational transit durations and SLA variance using kinematic parameters (distance, baseline velocity, meteorological impedance, and SLA contract tiers).
4. **Outlier Detection & Anomaly Treatment**: Implement and benchmark **Tukey's IQR**, **Standardized Z-Scores ($>3\sigma$)**, **Isolation Forest (2.0% contamination)**, and **Quantile Winsorization (1st & 99th percentiles)**.
5. **Supply Chain Feature Engineering**: Construct domain-specific features including **Cost per Kilometer (CPK)**, **Cost per Kilogram**, **Effective Speed ($km/h$)**, **SLA Variance ($\Delta t$)**, **Green Fleet EV indicator**, and **Adverse Weather Risk Factor**.
6. **Feature Scaling & Power Transformations**: Benchmark **StandardScaler**, **MinMaxScaler**, and **RobustScaler**, along with **Log1p** variance stabilization.

---

## 📊 Summary of Data Preprocessing Pipeline

### 1. Data Cleaning & Entity Resolution
- **Surrogate Key Resolution**: Replaced non-unique float `delivery_id` keys (498 collisions, 1.99%) with unique surrogate UUIDs (`DEL-IND-00001` to `DEL-IND-25000`).
- **Text Normalization**: Stripped trailing whitespaces and normalized string casing across all 7 categorical drivers.
- **Sensor Timestamp Dropouts**: Reconstructed transit time telemetry from kinematic variables ($d / v_{base} \times \iota_{weather} + \epsilon_{\text{traffic}}$) and computed SLA variance ($\Delta t$).

### 2. Multi-Method Outlier Engine
- **Tukey's IQR Fences**: Identified extreme univariate values outside $[Q_1 - 1.5 \times \text{IQR}, Q_3 + 1.5 \times \text{IQR}]$.
- **Standardized Z-Score**: Filtered parametric deviations beyond $|Z| > 3.0\sigma$.
- **Isolation Forest**: Flagged 500 multivariate anomalies (2.00% contamination) across distance, weight, cost, and transit time.
- **Quantile Winsorization**: Capped extreme tails at 1st and 99th percentiles to protect gradient-based downstream models.

### 3. Supply Chain Feature Engineering (18 New Features)

| Feature Name | Mathematical Formulation | Domain Impact |
| :--- | :--- | :--- |
| **`shipment_uid`** | `DEL-IND-{index:05d}` | Primary surrogate key ensuring entity integrity across distributed databases |
| **`cost_per_km`** | $\frac{\text{Delivery Cost}}{\text{Distance (km)}}$ | Normalizes freight pricing efficiency across short-haul vs long-haul lanes |
| **`cost_per_kg`** | $\frac{\text{Delivery Cost}}{\text{Package Weight (kg)}}$ | Measures freight yield per unit weight for density and load planning |
| **`effective_speed_kmh`** | $\frac{\text{Distance}}{\text{Actual Transit Hours}}$ | Identifies congestion, transit bottlenecks, and driver idle time |
| **`sla_variance_hours`** | $\text{Actual Hours} - \text{Expected SLA Hours}$ | Quantifies delivery delay magnitude for 3PL penalty reconciliation |
| **`is_ev`** | $1 \text{ if vehicle is EV else } 0$ | Flags zero-emission dispatches for green fleet and ESG analytics |
| **`is_adverse_weather`** | $1 \text{ if weather} \in \{\text{rain, storm, fog}\} \text{ else } 0$ | Isolates environmental risks affecting delivery timelines |
| **`log_delivery_cost`** | $\log(1 + \text{Delivery Cost})$ | Stabilizes variance and normalizes right-skewed cost distributions |

### 4. Normalization & Scaler Benchmarking
- **StandardScaler ($\mu=0, \sigma=1$)**: Optimal for linear regression, ridge/lasso, and logistic regression.
- **MinMaxScaler ($[0.0, 1.0]$)**: Suitable for neural network activations and bounded optimization.
- **RobustScaler (Median & IQR)**: Resistant to extreme delay tails and rate spikes.

---

## 🚀 How to Run the Notebook
1. Ensure Python 3.10+ and the required dependencies are installed:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter scipy
   ```
2. Launch the Jupyter Notebook interface:
   ```bash
   jupyter notebook week-2/data_cleaning_and_preprocessing.ipynb
   ```
3. Run all cells sequentially to view the step-by-step profiling, anomaly detection, statistical charts, and exported datasets.

---

## 📄 Primary Submission Deliverable
The primary formal report deliverable requested by the internship guidelines is:
* **[`Week_2_Data_Collection_Cleaning_and_Preprocessing_Report.docx`](file:///d:/19.3-yuva%20internship/Logistics%20Data%20Analyst%20Intern/week-2/Week_2_Data_Collection_Cleaning_and_Preprocessing_Report.docx)** (Comprehensive 1.97 MB executive Word report with structured tables, formulas, callout boxes, code listings, and embedded high-resolution visual charts).
