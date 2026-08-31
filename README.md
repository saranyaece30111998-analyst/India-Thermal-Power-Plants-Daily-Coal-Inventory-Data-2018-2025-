# ⚡ India Thermal Power Plants – Daily Coal Inventory (2018–2025)
# 🏭 **Coal Inventory Analytics: India (2018–2025)**

---

## ⚫ Project Overview
This Python‑based study analyzes daily coal inventory data across Indian thermal power plants (2018–2025).  
It covers ~362 000 records and 22 variables, offering a granular view of **coal requirement, receipts, consumption, stock adequacy, and performance indicators**.  
The analysis exposes persistent **supply shortfalls**, **uneven stock distribution**, and **critical plant risks**, forming a framework for **energy planning and logistics optimization**.

---

## ⚫ Objectives
1. **Coal Supply Analysis** – Examine daily requirement, receipts, and consumption.  
2. **Inventory Risk Assessment** – Evaluate stock health categories.  
3. **Efficiency Measurement** – Analyze PLF % relative to coal availability.  
4. **Track Inventory Fluctuations** – Observe reserve changes over time.  
5. **Regional Aggregation** – Indigenous vs import stock by region.  
6. **Transport Insights** – Identify bottlenecks in logistics.  
7. **Sectoral Aggregation** – Stock distribution across Central, State, Private, and JV sectors.

---

## ⚫ Dataset Description
- **Source:** India Data Portal  
- **Size:** ~80 MB  
- **Records:** ~362 000  
- **Variables:** 22 (daily coal requirement, receipts, consumption, normative stock, transport mode, PLF %, etc.)

### 🔹 Column Descriptions
| Column | Description |
|---------|-------------|
| `date` | Daily record date (datetime format) |
| `plant_id` | Unique identifier for each thermal power plant |
| `plant_name` | Name of the power plant |
| `state_code` | State abbreviation code |
| `region` | Derived zone (North, South, East, West) |
| `sector` | Ownership type (Central, State, Private, Joint Venture) |
| `installed_capacity` | Total installed generation capacity (MW) |
| `daily_requirement` | Coal required per day (tons) |
| `daily_receipt` | Coal received per day (tons) |
| `daily_consumption` | Coal consumed per day (tons) |
| `indigenous_stock` | Domestic coal stock available (tons) |
| `import_stock` | Imported coal stock available (tons) |
| `total_stock` | Sum of indigenous + import stock (tons) |
| `normative_stock_days` | Benchmark stock days for safe operation |
| `stock_days` | Actual stock days = total_stock / daily_consumption |
| `stock_category` | Classified as Safe (>14 days), Moderate (7–14 days), or Running Short (<7 days) |
| `plf_percentage` | Plant Load Factor % – efficiency indicator |
| `transport_mode` | Primary coal transport method (Rail, Road, Port) |
| `is_critical` | Flag for critical shortage plants |
| `remarks` | Operational notes or corrective actions |
| `actual_vs_normative_stock_percentage` | Ratio of actual stock to normative benchmark |
| `consumption_gap` | Difference between daily consumption and requirement |

---

## ⚫ Statistical Summary
- **Central tendency:** Mean values often exceed medians, confirming right‑skewed distributions dominated by large plants.  
- **Dispersion:** High variance and standard deviation in daily receipts and consumption, reflecting supply volatility.  
- **Percentiles:** 25th percentile shows frequent shortages; 75th percentile highlights concentration of reserves in a few plants.  
- **Skewness & Kurtosis:** Positive skewness indicates minority of large reserves dominate; high kurtosis reflects extreme outliers.  
- **Interpretation:** Median is more reliable than mean for typical plant behavior; mode highlights repeated shortages and stockouts.  

---

## ⚫ Key Metrics
| Metric | Value |
|--------|-------|
| Total Power Plants | 218 |
| Total Coal Stock | **71.65 M tons** |
| Indigenous Stock | **66.02 M tons** |
| Import Stock | **5.63 M tons** |

---

## ⚫ Insights

### 🔹 Descriptive
- Average reserves = 71.65 M tons (66.02 M indigenous, 5.63 M imported).  
- **North region dominates** (42 % of reserves, ~3.9 M tons daily consumption).  
- Inventory risk: Safe = 40.2 %, Running Short = 35.5 %, Moderate = 24.3 %.  
- Rail transport > 70 % → logistics bottlenecks.  
- Top plants: Vindhyachal (~1.55 M tons), Rihand (~1.32 M tons).  
- PLF % lower in coal‑deficit plants.  
- Long‑term decline in reserves signals systemic planning gaps.

### 🔹 Diagnostic
- Receipts lag behind requirements → persistent shortfalls.  
- Nearly 60 % of plants outside safe levels.  
- Regional imbalance favors North.  
- Rail bottlenecks cause delays.  
- Smaller plants face shortage risks.

### 🔹 Predictive
- Reserves may decline 8–12 % annually → below 55 M tons by 2028.  
- Safe plants shrink to ~30 %, Running Short rise > 40 %.  
- Import dependency could double (~10 M tons by 2028).  
- PLF % in shortage‑prone plants may drop 5–7 %.

### 🔹 Prescriptive
- **AI‑driven forecasting** to anticipate seasonal peaks.  
- **Diversify logistics** beyond rail.  
- **Rebalance regional supply** to reduce deficits.  
- **Build strategic reserves** ≥ 60 M tons.  
- **Link coal allocation** to PLF performance.  
- **Deploy real‑time dashboards** for monitoring.  
- **Diversify import sources** and strengthen policy governance.

---

## ⚫ Business Recommendations
- **Enhance forecasting & planning** with AI/ML.  
- **Diversify logistics** (road + port).  
- **Regional balancing** of reserves.  
- **Performance‑linked allocation** to raise PLF %.  
- **Strategic reserve creation** ≥ 60 M tons.  
- **Sectoral support** for private/state plants.  
- **Import diversification** to reduce risk.  
- **Digital dashboards** for real‑time tracking.  
- **Policy & governance** to enforce coal norms.

---

## ⚫ Conclusion
India’s coal supply chain faces **volatility, imbalance, and inefficiency**.  
Without intervention, reserves will decline and PLF disparities will widen.  
A multi‑pronged strategy — forecasting, logistics diversification, regional balancing, strategic reserves, and performance‑linked allocation — can transform the sector from **risk to resilience**, ensuring stable coal availability and energy security by 2025–2028.

---

## ⚫ Visuals (Insert Images)
- Daily Coal Stock Trend (Line Chart)  
- Inventory Risk (Donut Chart)  
- PLF Efficiency (Box Plot)  
- Regional Stock Distribution (Bar Chart)  
- Transport Mode Dependency (Pie Chart)  
- Dashboard Overview (Screenshot)

---

### 🟠 **Final End Border**
**From Risk to Resilience — India’s Coal Future Depends on Strategic Action**





  


