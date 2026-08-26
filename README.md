# ⚡ India Thermal Power Plants – Daily Coal Inventory (2018–2025)




## 📂 Dataset Information  
- **Source:** India Data Portal  
- **Location:** India  
- **Timeline:** 2018–2025  
- **Domain:** Daily coal stock records  
- **Size:** ~362,000 rows, 22 columns  

**Key Columns:**  
- `date`, `state_name`, `power_station_name`, `sector`, `utility`, `mode_of_transport`  
- `daily_requirement`, `daily_receipt`, `daily_consumption`  
- `req_normative_stock`, `total_stock`, `stock_days`, `plf_percentage`  
- `is_critical`, `remarks`  

---

## ⚙️ Requirements  
```bash
Python 3.9+
pandas
numpy
matplotlib
seaborn
plotly
```

---

## 🚀 Workflow  
### Stage 1 – Data Inspection  
- Load dataset from Google Drive  
- Check shape, columns, nulls, duplicates, and summary statistics  

### Stage 2 – Data Cleaning & Transformation  
- Convert datatypes (`date`, `id`, `state_code`)  
- Handle missing values using hierarchical imputation (station median → state mean → overall mean)  
- Feature engineering:  
  - `region` (North, South, East, West)  
  - `Consumption_Gap` (consumption – requirement)  
  - `Consumption_Status` (higher/lower/balanced)  
  - `Stock_Category` (Running Short, Moderate, Safe)  

### Stage 3 – Statistical Analysis & Visualization  
- Central tendency (mean, median, mode)  
- Dispersion (variance, standard deviation)  
- Visualizations: bar charts, distribution plots, stock adequacy comparisons  

---

## 📊 Key Insights  
- **Supply-demand imbalance:** Receipts consistently below requirements.  
- **Stock inadequacy:** Many plants report zero or critically low reserves.  
- **Performance inefficiency:** Large number of plants idle or underperforming.  
- **Skewed distribution:** Few well-stocked plants mask systemic shortages.  

---

## 📈 Example Output  
- **Mean daily requirement:** 14.62 MT vs **mean receipt:** 13.23 MT → supply gap.  
- **Median stock days:** 11 (below safe threshold of 14).  
- **PLF%:** Average 48.7%, indicating underutilization.  

---

## 📝 Notes  
- Data cleaning includes imputation and normalization.  
- Some categorical inconsistencies (e.g., "Pvt Sctore") were corrected.  
- Results highlight systemic coal supply chain challenges.  

---

## 👩‍💻 Author  
- **Saranya** – Data Analyst & Engineering Graduate  
- **Skills:** Python, SQL, Power BI, Excel  
- **Location:** Bangalore, India  

---



