# Week 1: Strategic Planning and Data Exploration in Logistics

## 📌 Project Overview
This project simulates the strategic planning, data exploration, and analytical roadmap phase of an enterprise-level logistics data analysis project for a multi-carrier last-mile and regional delivery network. 

The analysis is conducted on **25,000 shipment dispatches** across 9 major third-party logistics (3PL) partners, 6 vehicle categories, 4 delivery service modes, and 5 geographic regions in India.

---

## 📁 Repository Structure
```
week-1/
│
├── Delivery_Logistics.csv                                     # Complete dataset (25,000 shipment records)
├── strategic_analysis.ipynb                                  # Interactive Jupyter Notebook (EDA, KPIs & ML models)
├── Week_1_Strategic_Planning_and_Data_Exploration_Report.docx # Primary deliverable: Comprehensive executive Word report
├── week 1 task.txt                                            # Original task guidelines and evaluation criteria
└── README.md                                                  # Project documentation and summary
```

---

## 🎯 Key Project Objectives
1. **Define a Realistic Logistics Scenario**: An omni-channel e-commerce fulfillment network managing regional hubs and last-mile deliveries across North, South, East, West, and Central India.
2. **Identify & Benchmark Core KPIs**: Establish mathematical formulations and empirical baselines for fulfillment reliability, cost efficiency, and customer satisfaction.
3. **Data Science Methodology Research**: Outline how Supervised Classification, Regression, Unsupervised Clustering, and Operations Research apply to supply chain challenges.
4. **End-to-End Strategic Roadmap**: Detail a 5-stage lifecycle from data ingestion to live telemetry and executive BI dashboarding.
5. **Machine Learning Prototyping & Code Illustration**: Build functional predictive models for shipment delay prediction, freight cost estimation, and carrier tier segmentation.

---

## 📊 Core Logistics KPIs (Empirical Baseline)

Benchmarked against the 25,000 shipment records in `Delivery_Logistics.csv`:

| Key Performance Indicator | Mathematical Formula | Baseline Value | Industry Benchmark | Strategic Target |
| :--- | :--- | :---: | :---: | :---: |
| **On-Time Delivery Rate (OTDR)** | $\left(\frac{\text{Orders Delivered On-Time}}{\text{Total Orders}}\right) \times 100$ | **73.32%** | $\ge 95.0\%$ | $\ge 88.0\%$ |
| **Overall Delay Rate** | $\left(\frac{\text{Delayed Orders}}{\text{Total Orders}}\right) \times 100$ | **21.36%** | $< 4.0\%$ | $< 10.0\%$ |
| **Shipment Failure Rate (SFR)** | $\left(\frac{\text{Failed / Undeliverable Orders}}{\text{Total Orders}}\right) \times 100$ | **5.31%** | $< 1.5\%$ | $< 2.0\%$ |
| **Average Delivery Cost** | $\frac{\sum \text{Delivery Costs}}{\text{Total Orders}}$ | **₹864.94** | ₹750.00 | ₹800.00 |
| **Cost per Kilometer (CPK)** | $\frac{\sum \text{Delivery Costs}}{\sum \text{Distance (km)}}$ | **₹5.75 / km** | ₹5.20 / km | ₹5.40 / km |
| **Customer Satisfaction (CSAT)** | $\frac{\sum \text{Customer Star Ratings}}{\text{Total Rated Orders}}$ | **3.67 / 5.0** | $\ge 4.40$ | $\ge 4.20$ |

### Fulfillment Breakdown
- **Delivered On-Time**: 18,331 orders (73.32%) $\rightarrow$ Average Rating: **4.21 ★**
- **Delayed**: 5,341 orders (21.36%) $\rightarrow$ Average Rating: **2.40 ★**
- **Failed Completely**: 1,328 orders (5.31%) $\rightarrow$ Average Rating: **1.31 ★**

---

## 🔍 Key Analytical Findings

### 1. Delivery Service Mode Vulnerability
- **Express Delivery Crisis**: Dispatches under "Express" contracts experience a **73.78% delay rate** and a **14.42% complete failure rate**, causing customer satisfaction to plunge to **2.72 ★**.
- **Same Day**: Exhibits a **32.54% delay rate** and a **6.75% failure rate**.
- **Two Day & Standard**: Highly stable with delay rates of **0.43%** and **0.00%** respectively.

### 2. Meteorological Shocks
- **Stormy Weather**: Elevates delay rates to **41.45%** and failures to **8.91%** (CSAT: 3.35 ★).
- **Rainy Weather**: Causes a **37.35% delay rate** (CSAT: 3.47 ★).
- **Clear / Mild Conditions**: Maintain stable baseline delays between **16.0% and 17.4%** (CSAT: ~3.85 ★).

### 3. 3PL Carrier Benchmarking
- **Top Tier (High Reliability & Value)**:
  - **Delhivery**: 24.80% delay rate, 4.99% failure rate, ₹848.11 average cost, 3.69 ★ rating.
  - **FedEx**: 25.16% delay rate, 4.76% failure rate, ₹857.36 average cost, 3.70 ★ rating.
- **Lagging Tier**:
  - **Xpressbees**: 28.27% delay rate, 5.91% failure rate, ₹868.17 average cost, 3.61 ★ rating.

### 4. Fleet Electrification Viability
- Electric vehicles (**EV Bikes** and **EV Vans**) account for 33.3% of dispatches (8,334 orders).
- EV delivery reliability (EV Bike: **26.43% delay**, EV Van: **26.63% delay**) matches combustion vehicles with identical freight economics (**₹5.75/km**), confirming that fleet greening can proceed without SLA penalty.

---

## 🤖 Machine Learning Prototyping (In `strategic_analysis.ipynb`)

1. **Supervised Delay Risk Classification (Random Forest)**:
   - Predicts whether a shipment will be delayed prior to dispatch.
   - Validation Performance: **ROC-AUC = 0.9644**, **Accuracy = 89.62%**.
   - Primary Predictors: Delivery Mode (`standard`, `two day`, `same day`), Transit Distance (`distance_km`), and Prevailing Weather (`stormy`, `rainy`).
2. **Supervised Delivery Cost Regression (OLS Linear Regression)**:
   - Models freight charges against transit distance and vehicle class.
   - Validation Performance: **$R^2 = 0.9999$**, **RMSE = ₹4.67**.
3. **Unsupervised Carrier Segmentation (K-Means Clustering)**:
   - Segments 9 3PL partners into 3 performance clusters (Top Tier, Balanced Mid Tier, High Risk Tier) to drive volume allocation.

---

## 🚀 How to Run the Notebook
1. Ensure Python 3.10+ and the required dependencies are installed:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn jupyter
   ```
2. Launch the Jupyter Notebook interface:
   ```bash
   jupyter notebook week-1/strategic_analysis.ipynb
   ```
3. Run all cells sequentially to view the step-by-step data analysis, statistical tables, and embedded high-resolution charts.

---

## 📄 Primary Submission Deliverable
The primary formal report deliverable requested by the internship guidelines is:
* **[`Week_1_Strategic_Planning_and_Data_Exploration_Report.docx`](file:///d:/19.3-yuva%20internship/Logistics%20Data%20Analyst%20Intern/week-1/Week_1_Strategic_Planning_and_Data_Exploration_Report.docx)** (1.66 MB Word document with complete executive formatting, styled KPI tables, callout boxes, and embedded charts).
