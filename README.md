# 🏭 Coal Inventory Analytics (India, 2018–2025)

> **Comprehensive Python-based analysis of daily coal inventory data across Indian thermal power plants (2018–2025).**  
> Focused on supply-demand dynamics, inventory risks, transport bottlenecks, and forecasting to support energy planning and operational efficiency.

---

## 📑 Table of Contents
1. Project Overview  
2. Introduction  
3. Problem Statement  
4. Objectives  
5. Dataset Description  
   - 5.1 Attributes and Their Details  
   - 5.2 Column and Their Description  
6. Tools & Technologies  
7. Data Inspection  
8. Data Pre-Processing & Feature Engineering  
   - 8.1 Data Cleaning Steps  
   - 8.2 Feature Engineering  
9. Exploratory Data Analysis & Statistical Summary  
10. Analytical Objectives & Visual Insights  
11. Insights Generation  
   - 11.1 Descriptive Analysis  
   - 11.2 Diagnostic Analysis  
   - 11.3 Predictive Analysis  
   - 11.4 Prescriptive Analysis  
12. Key Findings — Consolidated  
13. Business Recommendations  
14. Limitations  
15. Conclusion  

---

## 1. Project Overview
This study delivers a Python based analysis of daily coal inventory data across Indian thermal power plants from 2018 to 2025. The dataset provides plant level records on coal requirement, receipts, consumption, stock adequacy, and performance indicators, enabling a granular view of supply demand dynamics. Through systematic data cleaning, feature engineering, and exploratory diagnostics, the analysis highlights persistent supply shortfalls, uneven stock distribution, and critical plant risks. The results establish a monitoring and forecasting framework to support energy planning, logistics optimization, and operational efficiency in India’s power sector.

---

## 2. Introduction
Coal remains the backbone of India’s electricity generation, with thermal power plants accounting for the majority of installed capacity. Ensuring uninterrupted coal supply is therefore not just an operational necessity but a matter of national energy security. Daily monitoring of coal inventories across plants provides critical insights into supply-demand imbalances, stock adequacy, and systemic risks that can disrupt power generation.  

This project undertakes a comprehensive data analytics exercise using a large-scale operational dataset (~362,000 records, 22 variables) covering the period 2018–2025. The dataset captures granular, plant-level information on daily coal requirements, receipts, consumption, normative stock benchmarks, transport modes, and performance indicators such as Plant Load Factor (PLF%).  

The analysis applies the full data analytics lifecycle — from raw data ingestion and cleaning, through feature engineering, exploratory profiling, statistical analysis, and visualization — to surface actionable insights on India’s coal supply chain.

---

## 3. Problem Statement
Coal is a critical energy resource, and managing its stock levels is essential for ensuring uninterrupted power generation and industrial supply.  
- How can we keep coal supplies steady at mines, power plants, and depots so that electricity doesn’t get disrupted?  
- What can be done to make the coal supply chain faster and more efficient?  
- How can forecasting be improved to better guess future coal needs and plan imports or deliveries?  
- What tools or methods can help us clearly see coal stock levels in different regions and at each plant?  

---

## 4. Objectives
1. Coal Supply Analysis  
2. Inventory Risk Assessment  
3. Efficiency Measurement  
4. Track Inventory Fluctuations  
5. Aggregate Stock Data by Region  
6. Transport Insights  
7. Aggregate Stock Data by Sector  

---

## 5. Dataset Description
- Source: India Data Portal  
- Size: ~80 MB  
- Storage: Google Drive → Imported into Google Colab  
- <img width="1090" height="568" alt="image" src="https://github.com/user-attachments/assets/bfe543fa-d68f-4091-ba5f-9b04b7fe92a3" />
**COLUMN NAME AND THEIR DESCRIPTION**
- <img width="1090" height="934" alt="image" src="https://github.com/user-attachments/assets/f721af7d-ad40-4f39-92e2-00600f1dda20" />

---

## 6. Tools & Technologies
- Python (Pandas, NumPy, Matplotlib, Seaborn)  
- Google Colab  
- Power BI / Tableau  

---

## 7. Data Inspection
- Checked dataset size with `df.shape`  
- Previewed records with `df.head()` and `df.tail()`  
- Identified data types with `df.dtypes` / `df.info()`  
- Counted missing values with `df.isnull().sum()`  
- Computed statistics with `df.describe()`  

---

## 8. Data Pre-Processing & Feature Engineering
### 8.1 Data Cleaning Steps
- Converted data types  
- Corrected categorical values  
- Filled missing values (capacity, requirement, receipts, consumption)  
- Completed normative stock data  
- Calculated stock days  
- Standardized performance metrics  
- Finalized qualitative fields  

### 8.2 Feature Engineering
- Region mapping  
- Consumption Gap  
- Consumption Status  
- Stock Category  

---

## 9. Exploratory Data Analysis & Statistical Summary
- Computed mean, median, mode
- <img width="1073" height="459" alt="image" src="https://github.com/user-attachments/assets/bf524a26-84fc-45f4-9f97-665fa71e7580" />

- Identified skewed distributions
- <img width="1090" height="571" alt="image" src="https://github.com/user-attachments/assets/88623f5b-fe1f-4e0f-b68e-df8dcf110a79" />

- Highlighted supply inconsistencies  

---

## 10. Analytical Objectives & Visual Insights
- Objective 1: Coal Supply Analysis
  <img width="1089" height="1088" alt="image" src="https://github.com/user-attachments/assets/9af2ddc0-6b5f-437f-b8b3-bcc998d13d04" />

- Objective 2: Inventory Risk Assessment  
- Objective 3: Efficiency Measurement  
- Objective 4: Inventory Fluctuations  
- Objective 5: Regional Stock Aggregation  
- Objective 6: Transport Insights  
- Objective 7: Sectoral Stock Aggregation  

---

## 10.1 Dashboard Visualization
- **Total Plants**: 218  
- **Total Coal Stock**: 71.65M tons  
- **Indigenous Stock**: 66.02M tons  
- **Import Stock**: 5.63M tons  

---

## 11. Insights Generation

### 11.1 Descriptive Analysis
- India’s thermal power plants (2018–2025) show coal reserves averaging **71.65M tons**, with **66.02M indigenous** and **5.63M imported**.  
- **North region** dominates with **42% of reserves** and ~**3.9M tons daily consumption**, while other regions face imbalances.  
- Inventory risk is high:  
  - Safe = **40.2% (~49M tons)**  
  - Running Short = **35.5% (~22M tons)**  
  - Moderate = **24.3% (~17M tons)**  
- Rail transport (>70%) is the primary supply mode, creating bottlenecks and delays.  
- Top plants by reserves: **Vindhyachal (~1.55M tons)** and **Rihand (~1.32M tons)**; smaller plants face shortage risks.  
- Efficiency gaps evident: PLF% lower in coal-deficit plants, highlighting performance disparities.  
- Trend analysis: Seasonal peaks and dips observed, but overall long-term decline in reserves signals systemic planning gaps.  

---

### 11.2 Diagnostic Analysis
- **Supply–Demand Gap**: Daily receipts often lag behind requirements, creating persistent shortfalls despite consumption aligning with demand.  
- **Inventory Risk**: Stock health shows Safe = **40.2% (~49M tons)**, Running Short = **35.5% (~22M tons)**, Moderate = **24.3% (~17M tons)** — nearly **60% of plants outside safe levels**.  
- **Regional Imbalance**: North zone dominates with **42% of reserves** and ~**3.9M tons daily consumption**, while South, East, and West face deficits.  
- **Transport Bottlenecks**: >70% of coal movement depends on rail, causing congestion, delays, and underperforming routes.  
- **Efficiency Gaps**: Plants with coal deficits show lower Plant Load Factor (PLF%), highlighting operational disparities.  
- **Trend Analysis**: Stock levels fluctuate sharply year-to-year, with seasonal peaks/dips and a long-term declining trend in reserves.  
- **Critical Plants**: Large plants like **Vindhyachal (~1.55M tons)** and **Rihand (~1.32M tons)** dominate reserves, while smaller plants face shortage risks.  

---

### 11.3 Predictive Analysis
- **Coal Stock Forecast (2026–2028)**: Reserves projected to decline by **8–12% annually**, potentially dropping below **55M tons by 2028** if current patterns persist.  
- **Inventory Risk Projection**: Safe plants may shrink to ~**30%**, while Running Short plants rise above **40%**, increasing outage risks.  
- **Regional Outlook**: North zone will continue to dominate (>40% reserves), but deficits in South and East will worsen, driving higher import dependency.  
- **Transport Forecast**: Rail dependency (>70%) likely to intensify delays by **15–20%**, unless logistics diversify into road and port networks.  
- **Efficiency Prediction**: PLF% in shortage-prone plants expected to decline by **5–7%**, widening performance disparities across regions.  
- **Seasonal Trends**: Peaks and dips will persist during monsoon and winter cycles, but overall reserves show a long-term downward trajectory.  
- **Imports** may rise from **5.6M tons to ~10M tons by 2028** to balance regional shortages.  

---

### 11.4 Prescriptive Analysis
- **Strengthen Forecasting Models**: Implement AI-driven demand forecasting to anticipate seasonal peaks and reduce shortage-prone plants by **15–20% within 3 years**.  
- **Diversify Transport Modes**: Reduce rail dependency (>70%) by expanding road and port logistics; aim to cut delivery delays by **20% in the short term**.  
- **Balance Regional Supply**: Reallocate reserves to South and East zones to reduce imbalance; target a **10% increase in safe
- **Improve Plant Efficiency**: Link coal allocation to PLF% performance, ensuring deficit plants receive priority; goal to raise PLF% in shortage-prone plants by 5–7%.

- **Build Strategic Reserves**: Establish buffer stock policies to counter long-term decline; maintain a minimum of 60M tons reserves consistently.

- **Enhance Monitoring Dashboards**: Deploy real-time dashboards tracking stock health, transport delays, and regional distribution for proactive decision-making.

- **Increase Import Flexibility**: Plan for imports to rise from 5.6M tons to ~10M tons by 2028, but diversify sourcing to reduce dependency on single markets.

---

## 12. Key Findings
- Export values skewed; few large plants dominate reserves.  
- North region holds 42% reserves, ~3.9M daily consumption.  
- Vindhyachal & Rihand lead reserves; smaller plants face shortages.  
- Inventory risk: nearly 60% plants outside safe levels.  
- Rail transport >70% → congestion.  
- Central sector largest share; private/state vulnerable.  
- Seasonal cycles → volatility; long-term decline in reserves.  
- Efficiency disparities: deficit plants show lower PLF%.  
- Indigenous coal backbone (66.02M tons); imports minimal (5.63M tons).  
- Systemic risk: reserves declining, shortages rising, PLF disparities widening.  

---

## 13. Business Recommendations
- AI/ML forecasting models → reduce shortages by 15–20% in 3 years.  
- Diversify logistics beyond rail → cut delays by 20%.  
- Regional balancing → +10% safe plants outside North by 2027.  
- Performance-linked allocation → raise PLF% in deficit plants by 5–7%.  
- Strategic buffer stock ≥60M tons.  
- Incentives for private/state plants.  
- Import diversification (~10M tons by 2028).  
- Real-time dashboards for monitoring.  
- Policy enforcement for reserve norms & logistics optimization.  

---

## 14. Limitations
- Imputation bias due to missing values.  
- Forecasting assumes current patterns persist.  
- Limited integration of external factors (renewables, climate risks, maintenance, grid demand).  

---

## 15. Conclusion
India’s coal inventory system shows **persistent supply-demand gaps, regional imbalances, and heavy rail dependency**.  
Nearly 60% of plants operate outside safe stock levels → high outage risk.  
Large plants dominate reserves; smaller plants face shortages.  
Long-term decline in reserves + seasonal volatility + limited import flexibility → systemic risk.  

**Multi-pronged strategy required:**  
- Strengthen forecasting models  
- Diversify logistics beyond rail  
- Rebalance regional supply  
- Build strategic reserves  
- Link coal allocation to performance outcomes  

