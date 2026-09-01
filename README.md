# â›ï¸ India Coal Inventory Analysis â€” Thermal Power Plants (2018â€“2025)

> A Python-based end-to-end data analytics project covering **~362,000 daily records across 218 thermal power plants**, analysing coal supplyâ€“demand balance, inventory risk, plant efficiency (PLF%), logistics, and a 2026â€“2028 reserve forecast.

---

## ðŸ“‹ Table of Contents

- [Project Overview](#-project-overview)
- [Problem Statement](#-problem-statement)
- [Objectives](#-objectives)
- [Dataset](#-dataset)
- [Tools & Technologies](#-tools--technologies)
- [Data Inspection](#-data-inspection)
- [Data Pre-processing & Feature Engineering](#-data-pre-processing--feature-engineering)
- [Exploratory Data Analysis](#-exploratory-data-analysis--statistical-summary)
- [Key Measures & Dashboard](#-key-measures--dashboard)
- [Visual Insights](#-visual-insights)
- [Insights Generation](#-insights-generation)
- [Key Findings](#-key-findings--consolidated)
- [Business Recommendations](#-business-recommendations)
- [Limitations](#-limitations)
- [Conclusion](#-conclusion)
- [How to Run](#-how-to-run)

---

## ðŸ” Project Overview

This study delivers a Python-based analysis of **daily coal inventory data across Indian thermal power plants from 2018 to 2025**. The dataset provides plant-level records on coal requirement, receipts, consumption, stock adequacy, and performance indicators, enabling a granular view of supplyâ€“demand dynamics. Through systematic data cleaning, feature engineering, and exploratory diagnostics, the analysis highlights **persistent supply shortfalls, uneven stock distribution, and critical plant risks**. The results establish a monitoring and forecasting framework to support energy planning, logistics optimization, and operational efficiency in India's power sector.

## â“ Problem Statement

Coal is a critical energy resource, and managing its stock levels is essential for ensuring uninterrupted power generation and industrial supply.

- How can we keep coal supplies steady at mines, power plants, and depots so electricity doesn't get disrupted?
- What can be done to make the coal supply chain faster and more efficient?
- How can forecasting be improved to better anticipate future coal needs and plan imports or deliveries?
- What tools or methods can help us clearly see coal stock levels in different regions and at each plant?

## ðŸŽ¯ Objectives

| # | Objective |
|---|-----------|
| 1 | **Coal Supply Analysis** â€” daily requirement, receipts & consumption for supplyâ€“demand balance |
| 2 | **Inventory Risk Assessment** â€” stock health categories for replenishment priorities |
| 3 | **Efficiency Measurement** â€” PLF% vs installed capacity and coal availability |
| 4 | **Track Inventory Fluctuations** â€” daily total stock vs timeline (2018â€“2025) |
| 5 | **Regional Aggregation** â€” indigenous & import stock totals by region |
| 6 | **Transport Insights** â€” mode of transport, bottlenecks, logistics efficiency |
| 7 | **Sector Aggregation** â€” stock totals by sector (Central, State, Private, JV) |

## ðŸ“Š Dataset

- **Source:** [India Data Portal](https://indiadataportal.com) (~80 MB raw file)
- **Scale:** ~362,000 records Ã— 22 variables
- **Period:** 2018â€“2025 (daily, plant-level)
- **Workflow:** Raw CSV â†’ Google Drive â†’ Google Colab

## ðŸ› ï¸ Tools & Technologies

| Category | Tools |
|----------|-------|
| Language | Python 3 |
| Environment | Google Colab |
| Data Handling | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, Plotly |
| Storage | Google Drive |

## ðŸ”Ž Data Inspection

- `df.shape` â€” total rows and columns
- `df.head()` / `df.tail()` â€” quick record preview
- `df.dtypes` / `df.info()` â€” column data types
- `df.isnull().sum()` â€” missing value counts per column
- `df.describe()` â€” min, max, mean for numerical columns

## ðŸ§¹ Data Pre-processing & Feature Engineering

### Data Cleaning Steps
- Converted data types â€” `id` â†’ object, `date` â†’ datetime, standardized `state_code`
- Corrected categorical values â€” e.g. `"Pvt Sctore"` â†’ `"Private Sector"`
- Filled gaps in `capacity` and `daily_requirement` using **mode**
- Imputed `daily_receipt` via **hierarchical filling** (median by plant â†’ mean by state â†’ overall mean)
- Applied the same hierarchical approach to `daily_consumption`
- Completed `req_normative_stock` and `normative_stock_days`
- Filled `indigenous_stock` & `import_stock`, then recalculated `total_stock`
- Derived `stock_days = total_stock / daily_consumption`, replaced invalid values, cast to integer
- Renamed `plf_prcnt` â†’ `plf_percentage`, recalculated `actual_vs_normative_stock_percentage`
- Filled missing `is_critical` with `"non_critical"` and `remarks` with `"No immediate action required"`

### Feature Engineering
- **`region`** â€” states mapped into North, South, East, West zones
- **`Consumption_Gap`** â€” `daily_consumption - daily_requirement`
- **`Consumption_Status`** â€” "Higher" / "Lower" / "Perfectly balanced"
- **`Stock_Category`** â€” stock days â†’ "Running Short" (<7) / "Moderate" (7â€“14) / "Safe" (>14)

## ðŸ“ˆ Exploratory Data Analysis & Statistical Summary

Most fields show **skewed distributions with frequent zero values**. The mean is often higher than the median (outliers present); the median gives a more reliable picture of typical values, while the mode highlights repeated shortages or stockouts. **Relying only on averages would be misleading.**

## ðŸ“Š Key Measures & Dashboard

| Measure | Value |
|---------|------:|
| ðŸ­ Total Power Plants | **218** |
| â›ï¸ Total Coal Stock | **71.65M tons** |
| ðŸ‡®ðŸ‡³ Indigenous Stock | **66.02M tons** |
| ðŸš¢ Import Stock | **5.63M tons** |

**Dashboard interpretation:**
- Coal Stock: 71.65M total, mostly indigenous (66M), imports small (5.6M)
- Stock Status: Safe reserves dominate (49M), but ~22M in moderate/shortage risk
- Regional Use: North consumes the most (~3.9M daily) and holds **42% of stock**
- Transport: Rail is the main supply mode â€” logistics are **highly rail-dependent (>70%)**
- Trends: Stock levels fluctuate sharply year to year â€” high volatility
- Top Plants: **Vindhyachal (1.55M)** and **Rihand (1.32M)** lead in reserves; smaller plants risk shortages

## ðŸ“‰ Visual Insights

### 1. Total Stock Composition â€” Indigenous vs Import
![Stock Composition](assets/stock_composition.png)

### 2. Inventory Health by Stock Category
![Stock Health](assets/stock_health.png)
> Safe = 40.2% | Running Short = 35.5% | Moderate = 24.3% â€” **nearly 60% of plants outside the Safe band**

### 3. Regional Distribution of Reserves
![Regional Share](assets/regional_share.png)
> North holds 42% of total stock and consumes ~3.9M tons daily

### 4. Daily Total Stock Trend (2018â€“2025)
![Stock Trend](assets/stock_trend.png)
> Seasonal peaks/dips with a clear **long-term declining trend**

### 5. Mode of Transport
![Transport Modes](assets/transport_modes.png)
> Rail dominates (>70%) â†’ bottlenecks, congestion and delays

### 6. PLF% â€” Coal-Deficit vs Adequately-Stocked Plants
![PLF Boxplot](assets/plf_boxplot.png)
> Coal-deficit plants show markedly lower Plant Load Factor

### 7. Reserve Forecast 2026â€“2028
![Forecast](assets/forecast.png)
> Reserves projected to decline **8â€“12% annually**, potentially below **55M tons by 2028**

### 8. Top Power Plants by Coal Reserves
![Top Plants](assets/top_plants.png)
> Vindhyachal (~1.55M t) and Rihand (~1.32M t) dominate reserves

## ðŸ’¡ Insights Generation

### Descriptive
- Average reserves of **71.65M tons** (66.02M indigenous, 5.63M imported)
- North dominates: 42% of reserves, ~3.9M tons daily consumption
- Rail (>70%) is the primary supply mode â†’ bottlenecks
- PLF% lower in coal-deficit plants â†’ performance disparities

### Diagnostic
- **Supplyâ€“demand gap:** daily receipts lag requirements, creating persistent shortfalls
- **Regional imbalance:** South, East and West face deficits while North holds 42%
- **Transport bottlenecks:** >70% rail dependency causes congestion and delays
- **Critical plants:** large plants dominate reserves; smaller plants face shortage risk

### Predictive (2026â€“2028)
- Reserves projected to fall **8â€“12%/year** â†’ below **55M tons by 2028**
- Safe plants may shrink to ~30%; Running Short plants above 40%
- Rail delays may intensify by 15â€“20% without logistics diversification
- Imports may rise from 5.6M â†’ **~10M tons by 2028**

### Prescriptive
- AI-driven demand forecasting â†’ cut shortage-prone plants 15â€“20% in 3 years
- Expand road & port logistics â†’ cut delivery delays 20%
- Reallocate reserves to South & East â†’ +10% safe-stock plants outside North by 2027
- Maintain a minimum **60M tons** strategic buffer consistently

## âœ… Key Findings â€” Consolidated

1. Reserves are right-skewed â€” a minority of large plants dominate total stock
2. **North holds 42%** of total stock, consuming ~3.9M tons daily
3. **Vindhyachal (~1.55M t)** and **Rihand (~1.32M t)** lead reserves
4. **~60% of plants outside safe stock levels** (Safe 40.2% / Short 35.5% / Moderate 24.3%)
5. **Rail >70%** of logistics â†’ bottlenecks and delays
6. Central sector holds the largest share; private/state plants more vulnerable
7. Seasonal cycles + clear **long-term declining trend**
8. Coal-deficit plants show **lower PLF%**
9. Indigenous coal is the backbone (66.02M t); imports minimal (5.63M t)
10. Without intervention, reserves decline, shortages rise, and PLF% disparities widen

## ðŸ¢ Business Recommendations

- **Enhance Forecasting & Planning** â€” AI/ML demand models; âˆ’15â€“20% shortage-prone plants in 3 years
- **Diversify Logistics** â€” reduce rail dependency; âˆ’20% delivery delays
- **Regional Balancing** â€” +10% safe-stock plants outside North by 2027
- **Performance-Linked Allocation** â€” prioritise low-PLF% plants; +5â€“7% efficiency
- **Strategic Reserve Creation** â€” maintain â‰¥60M tons buffer consistently
- **Sectoral Support** â€” incentives for private/state plants
- **Import Diversification** â€” plan for ~10M tons by 2028 from diversified markets
- **Digital Monitoring Dashboards** â€” real-time stock health, delays, distribution
- **Policy & Governance** â€” stricter reserve norms and equitable regional distribution

## âš ï¸ Limitations

- **Imputation bias** â€” hierarchical filling of missing receipts/consumption may reduce accuracy
- **Forecasting assumptions** â€” assumes current patterns persist; excludes policy shifts, renewables adoption, global market volatility
- **Scope constraints** â€” focuses on coal availability and PLF%; excludes maintenance, grid demand, climate risks

## ðŸ Conclusion

India's coal inventory system shows persistent supplyâ€“demand gaps, regional imbalances, and heavy rail reliance, with ~60% of plants outside safe stock levels. Long-term reserve decline, seasonal volatility, and limited import flexibility compound systemic risk. A multi-pronged strategy â€” stronger forecasting, diversified logistics, regional rebalancing, strategic reserves, and performance-linked allocation â€” can move the sector from volatility to resilience by 2025â€“2028.

## ðŸš€ How to Run

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/coal-inventory-analysis.git
cd coal-inventory-analysis

# 2. Install dependencies
pip install pandas numpy matplotlib seaborn plotly

# 3. Open the notebook (Google Colab recommended â€” dataset ~80 MB hosted on Google Drive)
jupyter notebook coal_inventory_analysis.ipynb
```

---

â­ If you found this analysis useful, please star the repository!

