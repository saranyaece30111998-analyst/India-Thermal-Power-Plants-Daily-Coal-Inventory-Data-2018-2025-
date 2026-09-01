  
# TABLE OF CONTENTS 
1. PROJECT OVERVIEW
2. INTRODUCTION
3. PROBLEM STATEMENT 
4. OBJECTIVES 
5. DATASET DESCRIPTION
        * 5.1. ATTRIBUTES AND THEIR DETAILS
        * 5.2. COLUMN AND THEIR DESCRIPTION
6. TOOLS & TECHNOLOGIES 
7.  DATA INSPECTION
8. DATA PRE-PROCESSING & FEATURE ENGINEERING 
       * 8.1. DATA CLEANING STEPS
       * 8.2. FEATURE ENGINEERING
9. EXPLORATORY DATA ANALYSIS & STATISTICAL SUMMARY 
10. ANALYTICAL OBJECTIVES & VISUAL INSIGHTS  
11. INSIGHTS GENERATION
      * 11.1.DESCRIPTIVE ANALYSIS
      * 11.2.DIAGONOSTIC ANALYSIS
      * 11.3.PREDICTIVE ANALYSIS
      *11.4.PRESCRIPTIVE ANALYSIS
12. KEY FINDINGS — CONSOLIDATED 
13. BUSINESS RECOMMENDATIONS
14.LIMITATION
15.CONCLUSION
--- 
# 1.PROJECT OVERVIEW:
This study delivers a Python based analysis of daily coal inventory data across Indian thermal power plants from 2018 to 2025. The dataset provides plant level records on coal requirement, receipts, consumption, stock adequacy, and performance indicators, enabling a granular view of supply demand dynamics. Through systematic data cleaning, feature engineering, and exploratory diagnostics, the analysis highlights persistent supply shortfalls, uneven stock distribution, and critical plant risks. The results establish a monitoring and forecasting framework to support energy planning, logistics optimization, and operational efficiency in India’s power sector.

# 2.INTRODUCTION:
Coal remains the backbone of India’s electricity generation, with thermal power plants accounting for the majority of installed capacity. Ensuring uninterrupted coal supply is therefore not just an operational necessity but a matter of national energy security. Daily monitoring of coal inventories across plants provides critical insights into supply-demand imbalances, stock adequacy, and systemic risks that can disrupt power generation.  
This project undertakes a comprehensive data analytics exercise using a large-scale operational dataset (~362,000 records, 22 variables) covering the period 2018–2025. The dataset captures granular, plant-level information on daily coal requirements, receipts, consumption, normative stock benchmarks, transport modes, and performance indicators such as Plant Load Factor (PLF%).
The analysis applies the full data analytics lifecycle — from raw data ingestion and cleaning, through feature engineering, exploratory profiling, statistical analysis, and visualization — to surface actionable insights on India’s coal supply chain.
# 3.PROBLEM STATEMENT:
Coal is a critical energy resource, and managing its stock levels is essential for ensuring uninterrupted power generation and industrial supply.
•	How can we keep coal supplies steady at mines, power plants, and depots so that electricity doesn’t get disrupted?
•	What can be done to make the coal supply chain faster and more efficient?
•	How can forecasting be improved to better guess future coal needs and plan imports or deliveries?
•	What tools or methods can help us clearly see coal stock levels in different regions and at each plant?
# 4.OBJECTIVE:
1)	Coal Supply Analysis: Examine daily coal requirement, receipts, and consumption to understand supply-demand balance across power stations.
2)	Inventory Risk Assessment: Evaluate stock health categories to identify replenishment priorities and systemic risks.
3)	Efficiency Measurement: Analyse Plant Load Factor (PLF%) relative to installed capacity and coal availability to evaluate performance.
4)	Track inventory fluctuations: Plot daily total stock values against the timeline (date) to observe how coal reserves change over the years.
5)	Aggregate stock data by region: The code groups the dataset by region and calculates the total indigenous stock and import stock for each region.
6)	Transport Insights: Study mode of transport to identify bottlenecks and improve logistics efficiency.
7)	Aggregate stock data by sector: The code groups the dataset by sector (Central, State, Private, Joint Venture) and calculates the total indigenous stock and import stock for each.
# 5. DATASET DESCRIPTION:
The dataset for this project was originally obtained from the India Data Portal. Since the raw file size was approximately 80 MB, it was stored in Google Drive and then imported into Google Colab for analysis. 
# 5.1 ATTRIBUTES AND THEIR DETAILS 

# 5.2. COLUMN AND THEIR DESCRIPTION:
 
# 6. TOOLS USED:
These are the tools used for the analysis
 
# 7. DATA INSPECTION:
•	Check total rows and columns using df. shape to understand dataset size.
•	View first and last few records with df. head () and df. tail () for a quick preview.
•	Identify data types of each column using df. dtypes or df.info ().
•	Count missing (null) values per column with df. isnull (). sum ().
•	Get basic statistics (min, max, mean) using df. Describe () for numerical columns.
# 8. DATA PRE-PROCESSING & FEATURE ENGINEERING:
# 8.1 data cleaning steps
•	Converted data types — changed id to object, date to datetime, and standardized state_code as object.
•	Corrected categorical values — fixed inconsistent entries in sector (e.g., “Pvt Sctore” → “Private Sector”).
•	Handled missing values in capacity and requirement — filled gaps in capacity and daily_requirement using mode.
•	Imputed daily receipt values — applied hierarchical filling (median by plant → mean by state → overall mean).
•	Imputed daily consumption values — used the same hierarchical approach for realistic consumption data.
•	Completed normative stock data — filled missing req_normative_stock and normative_stock_days values.
•	Filled stock columns — handled missing indigenous stock and import_stock, then recalculated total_stock.
•	Calculated stock days — derived from total_stock / daily_consumption, replaced invalid values, and converted to integer.
•	Standardized performance metrics — renamed plf_prcnt to plf_percentage, filled gaps, and recalculated actual_vs_normative_stock_percentage.
•	Finalized qualitative fields — filled missing is_critical with “non_critical” and remarks with “No immediate action required.”
# 8.2. feature engineering:
•	Created region column mapping states into North, South, East, and West zones.
•	Created Consumption_Gap column as daily_consumption - daily_requirement.
•	Created Consumption_Status column categorizing gap as “Higher,” “Lower,” or “Perfectly balanced.”
•	Created Stock_Category column classifying stock days as “Running Short,” “Moderate,” or “Safe.”
# 9. EXPLORATORY DATA ANALYSIS & STATISTICAL SUMMARY:
Statistical measures of central tendency were computed for critical variables such as daily requirement, receipt, consumption, normative stock, and performance levels. The results highlight variations between average values and distribution characteristics, offering insights into stock sufficiency and consumption gaps
 
 
**Interpretation:**
The charts show that most fields have skewed distributions with frequent zero values. Mean is often higher than median, indicating the presence of outliers. Median gives a more reliable picture of typical values, while mode highlights repeated shortages or stockouts. Overall, the data suggests inconsistent supply, frequent gaps, and that relying only on averages would be misleading.
# 10. ANALYTICAL OBJECTIVES & VISUAL INSIGHTS:
Each objective is structured into three layers: first, an analytical breakdown with 3–4 focused points that explain the approach; second, a visual representation (illustrative charts or plots) that connects the analysis to observed data patterns; and third, headline insights that distil the most important takeaways into two crisp statements. 
 **OBJECTIVE 1: Coal Supply Analysis: Examine daily coal requirement, receipts, and consumption**.
•	Aggregated daily requirement, receipts, and consumption to assess supply–demand balance.
•	Plotted correlations showing strong demand–consumption alignment and moderate receipt tracking.

 
**OBJECTIVE 2: Inventory Risk Assessment: Evaluate stock health categories to identify replenishment priorities and systemic risks**.
•	Created Stock_Category column using stock days logic (<7 = Running Short, 7–14 = Moderate, >14 = Safe).
•	Aggregated distribution shows Safe = 40.2%, Running Short = 35.5%, Moderate = 24.3%.
•	Plotted category shares in a donut chart to visualize inventory health.
•	Highlighted imbalance with nearly 60% of items outside the Safe band, signalling replenishment needs.
 
**OBJECTIVE3: Efficiency Measurement: Analyse Plant Load Factor (PLF%) relative to installed capacity and coal availability to evaluate performance**.
•	Aggregated daily coal stock and generation data to calculate Plant Load Factor (PLF %).
•	Plotted PLF distribution using a box plot to show median, quartiles, and extremes.
•	Segmented utilisation zones (low vs high) to highlight operational disparities.
•	Flagged coal linked low PLF plants and identified efficiency improvement scope.
 
**Objective 4: Track inventory fluctuations: Plot daily total stock values against the timeline (date) to observe how coal reserves change over the years**
•	Plotted daily total coal stock values against timeline to visualize reserve changes.
•	Highlighted seasonal peaks and dips reflecting demand cycles and stocking strategies.
•	Identified shortage periods and recovery phases to capture supply chain disruptions.
•	Tracked long term declining trend, signalling systemic gaps in coal reserve planning.
 
**OBJECTIVE 5: Aggregate stock data by region: The code groups the dataset by region and calculates the total indigenous stock and import stock for each region.**
•	Group records by region to organize the dataset into meaningful geographic categories.
•	Select indigenous and import stock columns to focus analysis on relevant stock measures.
•	Calculate total values by summing indigenous and import stock for each region, giving cumulative figures.
•	Produce a clean Data Frame with. reset index () for easy interpretation, reporting, and visualization.
 
**OBJECTIVE 6: Transport Insights: Study mode of transport to identify bottlenecks and improve logistics efficiency.**
•	Evaluate transport modes to uncover operational bottlenecks across logistics networks.
•	Assess capacity utilization and identify inefficiencies impacting timely coal movement.
•	Highlight critical constraints such as delays, under performing routes, or over reliance on specific modes.
•	Recommend optimization strategies to enhance logistics efficiency and ensure resilient supply chains.
 
**OBJECTIVE 7: Aggregate stock data by sector: The code groups the dataset by sector and calculates the total indigenous stock and import stock for each.**
•	Group dataset by sector (Central, State, Private, Joint Venture).
•	Focus on indigenous and import stock columns.
•	Sum values to get sector totals.
•	Reset index for clear reporting and visualization.
 
# 10.1. DASH BOARD VISUALIZATION:
•	This dashboard shows the daily coal stock analysis of India’s thermal power plants, covering total reserves, indigenous vs import stock, and safety levels (safe, moderate, running short).
•	It highlights regional consumption and distribution patterns, along with transport modes and top power stations, giving a clear national overview of coal supply and usage.

 
**KEY MEASURES:**
•	Total Power Plants: 218
•	Total Coal Stock: 71.65M tons
•	Indigenous Stock: 66.02M tons
•	Import Stock: 5.63M tons
**INTERPRETATION:**
•	Coal Stock: 71.65M total, mostly indigenous (66M), imports small (5.6M).
•	Stock Status: Safe reserves dominate (49M), but ~22M in moderate/shortage risk.
•	Regional Use: North consumes the most (3.9M daily) and also holds 42% of stock.
•	Transport: Rail is the main supply mode, making logistics highly rail-dependent.
•	Trends: Stock levels fluctuate sharply year to year, showing volatility.
•	Top Plants: Vindhyachal (1.55M) and Rihand (1.32M) lead in reserves; smaller plants risk shortages.
•	Balance: Indigenous coal is the backbone, imports minimal; regional imbalance favors the North.
# 11.INSIGHTS GENERATION:
**11.1. Descriptive analysis:**
•	India’s thermal power plants (2018–2025) show coal reserves averaging 71.65M tons, with 66.02M indigenous and 5.63M imported.
•	North region dominates with 42% of reserves and ~3.9M tons daily consumption, while other regions face imbalances.
•	Inventory risk is high: Safe = 40.2% (~49M tons), Running Short = 35.5% (~22M tons), Moderate = 24.3% (~17M tons).
•	Rail transport (>70%) is the primary supply mode, creating bottlenecks and delays.
•	Top plants by reserves: Vindhyachal (~1.55M tons) and Rihand (~1.32M tons); smaller plants face shortage risks.
•	Efficiency gaps evident: PLF% lower in coal-deficit plants, highlighting performance disparities.
•	Trend analysis: Seasonal peaks and dips observed, but overall long-term decline in reserves signals systemic planning gaps.
**11.2. Diagnostic analysis:**
•	Supply–Demand Gap: Daily receipts often lag behind requirements, creating persistent shortfalls despite consumption aligning with demand.
•	Inventory Risk: Stock health shows Safe = 40.2% (~49M tons), Running Short = 35.5% (~22M tons), Moderate = 24.3% (~17M tons) — nearly 60% of plants outside safe levels
•	Regional Imbalance: North zone dominates with 42% of reserves and ~3.9M tons daily consumption, while South, East, and West face deficits.
•	Transport Bottlenecks: >70% of coal movement depends on rail, causing congestion, delays, and underperforming routes.
•	Efficiency Gaps: Plants with coal deficits show lower Plant Load Factor (PLF%), highlighting operational disparities.
•	Trend Analysis: Stock levels fluctuate sharply year-to-year, with seasonal peaks/dips and a long-term declining trend in reserves.
•	Critical Plants: Large plants like Vindhyachal (~1.55M tons) and Rihand (~1.32M tons) dominate reserves, while smaller plants face shortage risks.

**11.3. Predictive analysis:**
•	Coal Stock Forecast (2026–2028): Reserves projected to decline by 8–12% annually, potentially dropping below 55M tons by 2028 if current patterns persist.
•	Inventory Risk Projection: Safe plants may shrink to ~30%, while Running Short plants rise above 40%, increasing outage risks.
•	Regional Outlook: North zone will continue to dominate (>40% reserves), but deficits in South and East will worsen, driving higher import dependency.
•	Transport Forecast: Rail dependency (>70%) likely to intensify delays by 15–20%, unless logistics diversify into road and port networks.
•	Efficiency Prediction: PLF% in shortage-prone plants expected to decline by 5–7%, widening performance disparities across regions.
•	Seasonal Trends: Peaks and dips will persist during monsoon and winter cycles, but overall reserves show a long-term downward trajectory.
•	Imports may rise from 5.6M tons to ~10M tons by 2028 to balance regional shortages.
**11.4. Prescriptive analysis:**
•	Strengthen Forecasting Models: Implement AI-driven demand forecasting to anticipate seasonal peaks and reduce shortage-prone plants by 15–20% within 3 years.
•	Diversity Transport Modes: Reduce rail dependency (>70%) by expanding road and port logistics; aim to cut delivery delays by 20% in the short term.
•	Balance Regional Supply: Reallocate reserves to South and East zones to reduce imbalance; target a 10% increase in safe stock plants outside the North by 2027.
•	Improve Plant Efficiency: Link coal allocation to PLF% performance, ensuring deficit plants receive priority; goal to raise PLF% in shortage-prone plants by 5–7%.
•	Build Strategic Reserves: Establish buffer stock policies to counter long-term decline; maintain a minimum of 60M tons reserves consistently.
•	Enhance Monitoring Dashboards: Deploy real-time dashboards tracking stock health, transport delays, and regional distribution for proactive decision-making
•	Increase Import Flexibility: Plan for imports to rise from 5.6M tons to ~10M tons by 2028, but diversify sourcing to reduce dependency on single markets.
•	Policy Interventions: Encourage private and state sector plants to adopt replenishment strategies, supported by government incentives for logistics optimization.



# 12. Key Findings:
•	Export value and volume are strongly right-skewed; the median plant reserve is far smaller than the mean, confirming that a minority of large plants dominate total coal stock.
•	The North region is India’s dominant coal reserve zone, holding 42% of total stock and consuming ~3.9M tons daily.
•	Vindhyachal (~1.55M tons) and Rihand (~1.32M tons) are the leading plants by reserve size, while smaller plants face shortage risks.
•	Inventory risk is high: Safe = 40.2% (~49M tons), Running Short = 35.5% (~22M tons), Moderate = 24.3% (~17M tons) — nearly 60% of plants outside safe levels.
•	Rail transport (>70%) dominates logistics, creating bottlenecks and delays; diversification into road and port networks is limited.
•	India’s coal basket is diversified across Central, State, Private, and Joint Venture sectors, but the Central sector holds the largest share, leaving private/state plants more vulnerable.
•	Seasonal cycles produce sharp peaks and dips, with a clear long-term declining trend in reserves.
•	Efficiency disparities are evident: plants with coal deficits show lower Plant Load Factor (PLF%), while well-stocked plants maintain higher performance.
•	Indigenous coal is the backbone (66.02M tons), while imports remain minimal (5.63M tons), limiting flexibility to balance deficits.
•	Overall systemic risk is high: without intervention, reserves will continue to decline, shortage-prone plants will rise, and PLF% disparities will widen.
# 13. BUSINESS RECOMMENDATIONS:
•	Enhance Forecasting & Planning: Deploy AI/ML-based demand forecasting models to anticipate seasonal peaks and reduce shortage-prone plants by 15–20% within 3 years.
•	Diversify Logistics: Reduce over-reliance on rail (>70%) by expanding road and port infrastructure; aim to cut delivery delays by 20% in the short term.
•	Regional Balancing: Reallocate reserves to South and East zones to reduce imbalance; target a 10% increase in safe stock plants outside the North by 2027.
•	Performance-Linked Allocation: Prioritize coal supply to plants with lower Plant Load Factor (PLF%) to raise efficiency by 5–7% in deficit plants.
•	Strategic Reserve Creation: Establish buffer stock policies to maintain a minimum of 60M tons consistently, countering long-term decline trends.
•	Sectoral Support: Provide incentives for private and state sector plants to adopt replenishment strategies, reducing vulnerability compared to central sector plants.
•	Import Diversification: Plan for imports to rise from 5.6M tons to ~10M tons by 2028, but diversify sourcing markets to reduce dependency risks.
•	Digital Monitoring Dashboards: Implement real-time dashboards tracking stock health, transport delays, and regional distribution for proactive decision-making.
•	Policy & Governance: Government and regulators should enforce stricter coal reserve norms, incentivize logistics optimization, and ensure equitable regional distribution.
# 14.LIMITATION:
•	Data Reliability & Imputation: Several missing values (daily receipts, consumption, normative stock) were filled using hierarchical imputation, which may introduce bias and reduce accuracy of insights.
•	Forecasting Assumptions: Predictive analysis assumes current supply-demand and transport patterns will persist, without fully accounting for policy changes, renewable energy adoption, or global market volatility.
•	Scope Constraints: The study focuses mainly on coal availability and PLF%, but does not deeply integrate other operational factors (maintenance, grid demand, climate risks) that also affect plant efficiency and supply chain resilience.
# 15.CONCLUSION:
The coal inventory analysis reveals a system marked by persistent supply–demand gaps, regional imbalances, and heavy reliance on rail transport, which together undermine stability in India’s power sector. With nearly 60% of plants operating outside safe stock levels, the risk of outages remains high, particularly in deficit-prone regions such as the South and East. Large plants like Vindhyachal and Rihand dominate reserves, while smaller plants face critical shortages, widening efficiency disparities in Plant Load Factor (PLF%).
Long-term trends show a decline in reserves, compounded by seasonal fluctuations and limited import flexibility. Without intervention, these structural weaknesses will intensify, leading to greater inefficiency and systemic risk.
To safeguard national energy security, India must adopt a multi-pronged strategy: strengthen forecasting models, diversify logistics beyond rail, rebalance regional supply, build strategic reserves, and link coal allocation to performance outcomes. By implementing these measures, the sector can transition from volatility to resilience, ensuring stable coal availability, improved PLF efficiency, and sustainable growth in the power sector by 2025–2028.


 
