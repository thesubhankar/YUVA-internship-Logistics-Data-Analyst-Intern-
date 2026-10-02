# Week 3: Advanced Data Analysis and Visualization in Logistics

## 📌 Project Overview
This project delivers the complete advanced data exploration, statistical profiling, and methodological visualization suite for an enterprise-scale multi-carrier logistics distribution network in India. 

The analysis is conducted on an authentic **Indian Logistics Operations Dataset** (`Delivery_Logistics.csv`, 25,000 shipment records) across 9 prominent third-party logistics (3PL) carriers (**Delhivery, Blue Dart, Xpressbees, Shadowfax, DHL, Ekart, Ecom Express, FedEx, and Amazon Logistics**), covering 6 vehicle types (including EV green fleets), 4 service modes, and 5 primary Indian economic corridors (**North, South, East, West, Central**).

---

## 📁 Repository Structure
```
week-3/
│
├── Delivery_Logistics.csv                                        # Complete dataset (25,000 shipment records)
├── advanced_data_analysis_and_visualization.ipynb               # Fully executed Jupyter Notebook (EDA & 9 Visualizations)
├── Week_3_Advanced_Data_Analysis_and_Visualization_Report.docx  # Primary deliverable: Comprehensive executive Word report
├── week-3 task.txt                                               # Original task guidelines and evaluation criteria
└── README.md                                                     # Project documentation and summary
```

---

## 🎯 Key Project Objectives
1. **Hypothetical & Empirical Logistics Telematics**: Ingest and structure 25,000 multi-carrier shipment telematics across Indian regional corridors.
2. **Comprehensive Exploratory Data Analysis (EDA)**: Calculate central tendencies (Mean, Median, Mode, 5% Trimmed Mean), dispersion (Std Dev, Variance, IQR, Range), and distribution shapes (Skewness, Kurtosis).
3. **Advanced Visualizations with Methodological Justifications**: Produce 9 publication-grade visualizations, each paired with theoretical reasoning justifying the specific plot choice.
4. **Operational Bottleneck Diagnostics**: Interpret visual patterns to identify root causes of delay spikes, cost variances, and customer churn.
5. **Executive Word Report**: Compile an exhaustive formal report (`.docx`) with embedded high-resolution figures, formulas, and actionable strategic recommendations.

---

## 📊 Summary of Statistical Profiling (EDA)

| Feature / Metric | Mean | Median | Mode | 5% Trimmed | Std Dev | Variance | IQR | Min - Max | Skewness | Kurtosis |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **`distance_km`** | 150.39 | 151.00 | 297.10 | 150.39 | 86.41 | 7,466.6 | 149.00 | 3.6 - 297.1 | +0.002 | -1.196 |
| **`package_weight_kg`** | 25.15 | 25.15 | 0.67 | 25.15 | 14.37 | 206.5 | 24.98 | 0.67 - 49.52 | -0.003 | -1.200 |
| **`delivery_cost`** | ₹864.94 | ₹867.54 | ₹95.67 | ₹864.92 | ₹435.71 | 189,845.5 | ₹747.11 | ₹95.7 - ₹1,632.7 | +0.001 | -1.172 |
| **`cost_per_km`** | ₹7.04 | ₹5.74 | ₹26.57 | ₹6.18 | ₹5.00 | 25.0 | ₹1.07 | ₹5.0 - ₹73.5 | **+6.383** | **+50.930** |
| **`delivery_rating`** | 3.67 ★ | 4.00 ★ | 5.00 ★ | 3.73 ★ | 1.15 | 1.32 | 2.00 | 1.0 - 5.0 ★ | -0.473 | -0.739 |

### Correlation Insights
- **Distance vs. Delivery Cost**: Extremely strong positive linear correlation ($r = 0.991, p < 0.001$), confirming distance as the dominant variable cost driver.
- **Weight vs. Delivery Cost**: Near-zero correlation ($r = 0.002$), indicating flat weight tiering across regional line-hauls.
- **Delay vs. Rating**: Negative correlation ($r = -0.684$), quantifying the steep drop in customer retention on delayed dispatches.

---

## 🎨 Visualization Catalog & Methodological Justifications

| Figure # | Visualization Title | Plot Architecture | Methodological Justification |
| :---: | :--- | :--- | :--- |
| **Fig 1** | Univariate Distributions & Skewness of Key Logistics Metrics | Multi-panel Histograms + KDE + Boxplot Fences | Coupling continuous density curves with frequency histograms and boxplots captures positive skewness, modal density, and extreme outlier tails simultaneously. |
| **Fig 2** | Multi-Variable Correlation Heatmap Matrix | Annotated Lower-Triangular Heatmap | Encodes pairwise Pearson coefficients across 8+ variables into divergent color gradients, instantly highlighting collinearity and preventing multicollinearity in regression models. |
| **Fig 3** | 3PL Carrier Multidimensional Benchmark Matrix | 4D Bubble Scatter Plot | Compresses 4 dimensions into one chart: X=Delay %, Y=CSAT Rating, Bubble Size=Average Cost, Hue=Failure Rate %. Classifies carriers into elite vs high-risk tiers. |
| **Fig 4** | Delivery Mode Vulnerability Faceted by Indian Region | Faceted Grouped Bar Chart | Decomposes national delay metrics into 5 geographic corridors, proving that Express delivery failure is a systemic nationwide bottleneck rather than a localized hub anomaly. |
| **Fig 5** | Meteorological Disruption & Weather Impedance | Dual-Panel Delay Bar + Split Violin Plots | Displays macro delay probabilities alongside the complete probability density and interquartile dispersion of CSAT ratings under adverse weather conditions. |
| **Fig 6** | Transportation Cost Function & Distance Regression | OLS Regression with 95% CI + Residual Error Histogram | Validates whether line-haul freight billing strictly follows distance-proportional linear pricing ($R^2 = 0.982, p < 0.001$) and tests homoscedasticity. |
| **Fig 7** | Vehicle Fleet Efficiency & Electrification Tradeoff | Paired Comparative Bar Chart (Cost vs Delay) | Evaluates unit freight cost (₹/km) and delay rates across EV and ICE combustion fleets, demonstrating operational and economic parity (₹5.75/km). |
| **Fig 8** | Regional Shipment Density & Carrier Allocation Matrix | 2D Cross-Tabulation Density Heatmap | Visualizes consignment volumes across Indian regions and 3PL partners to detect single points of failure, load concentration risk, and network balance. |
| **Fig 9** | Customer Satisfaction (CSAT) Degradation Curve | 100% Stacked Bar + Error-Bar Mean Scores | Directly quantifies the collapse of 5-star customer feedback as dispatches transition from on-time (4.21 ★) to delayed (2.40 ★) and failed (1.31 ★). |

---

## 🔍 Key Operational Insights & Bottleneck Diagnoses
1. **The Expedited Delivery Paradox**:
   - `Express` shipments suffer a **73.78% delay rate** and a **14.42% complete failure rate** (CSAT collapsing to **2.72 ★**).
   - `Same Day` shipments experience a **32.54% delay rate** and **6.75% failure rate**.
   - `Standard` ground shipments achieve **0.00% delay**, proving that expedited SLA promises are commercially overcommitted without matching sortation infrastructure.
2. **Weather Vulnerability**:
   - Stormy weather causes a **41.45% delay rate** and **8.91% failure rate**.
   - Rainy weather causes a **37.35% delay rate**, compared to **16.0% - 17.4%** under clear/mild conditions.
3. **3PL Partner Polarization**:
   - **Top Tier (High Reliability & Value)**: **Delhivery** (24.80% delay, ₹848.11 avg cost) and **FedEx** (25.16% delay, 3.70 rating).
   - **Lagging Tier**: **Xpressbees** (28.27% delay, 5.91% failure rate, 3.61 rating).
4. **Fleet Electrification Parity**:
   - Electric Vehicles (**EV Bikes** and **EV Vans**) account for **33.3% of total dispatches** (8,334 orders).
   - Both EV classes match ICE combustion vehicles in punctuality (**26.43% - 26.63% delay**) and freight economics (**₹5.75 / km**), confirming that aggressive fleet electrification can proceed with zero operational penalty.

---

## 🚀 How to Run the Notebook
1. Ensure Python 3.10+ and the required packages are installed:
   ```bash
   pip install pandas numpy matplotlib seaborn scipy jupyter nbformat nbclient
   ```
2. Launch the Jupyter Notebook interface:
   ```bash
   jupyter notebook week-3/advanced_data_analysis_and_visualization.ipynb
   ```
3. Run all cells sequentially to view the step-by-step statistical audits, summary tables, and all 9 inline rendered publication plots.

---

## 📄 Primary Submission Deliverable
The primary formal report deliverable requested by the internship guidelines is:
* **[`Week_3_Advanced_Data_Analysis_and_Visualization_Report.docx`](file:///d:/19.3-yuva%20internship/Logistics%20Data%20Analyst%20Intern/week-3/Week_3_Advanced_Data_Analysis_and_Visualization_Report.docx)** (Comprehensive 3.26 MB executive Word report with structured tables, formulas, callout boxes, code listings, and 9 embedded high-resolution visual charts).
