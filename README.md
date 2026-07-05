# Superstore Retail Analytics Portfolio

This repository hosts a comprehensive, two-part business intelligence suite built in Tableau using the retail Superstore dataset. The portfolio progresses from an high-level financial overview to an advanced relational data model tracking supply chain deficits.

---

## 📊 Project 1: Executive Performance Dashboard
**Filename:** `Executive_Performance_Dashboard.twbx`

### Objective
Designed an executive-ready financial overview dashboard to provide leadership with an immediate, real-time pulse on global corporate growth, regional profitability, and core inventory performance.

### Key Features & Architecture
* **Continuous Time-Series Forecasting:** Built a chronological, continuous trend line stretching across multiple fiscal years to map macro growth trajectories and seasonal revenue spikes (March, September, November).
* **Geographic Distribution Mapping:** Leveraged spatial coordinate plotting to map state-level sales data, utilizing customized color palettes to isolate geographic revenue zones.
* **Dynamic Canvas Alignment:** Structured the interface using strict layout container grids and "Entire View" object formatting to ensure zero text overlap and a balanced layout layout.

---

## 🚛 Project 2: Supply Chain Risk & Returns Optimization Suite
**Filename:** `Supply_Chain_Returns_Optimization.twbx`

### Objective
Elevated the analysis to a diagnostic level by tracing operational profit leakage. This suite links transactional volumes to return occurrences to isolate financial bleeding and territory performance issues.

### Advanced Data Modeling (Star Schema)
To unlock multi-layered insights, I engineered a relational schema by joining 3 independent data tables:
* **Orders (Fact Table):** Core transactional ledger.
* **People (Dimension Table):** Maps territorial ownership to specific Regional Managers.
* **Returns (Dimension Table):** Joined via an intentional **Left Join** to fully preserve 100% of historical sales data while cleanly appending return instances.

### Custom Calculations Written
* **Is Returned? Flag:** `IF ISNULL([Returned]) THEN 0 ELSE 1 END` (Standardizes text strings into operational binary integers).
* **Return Rate %:** `SUM([Is Returned?]) / COUNTD([Order ID])` (Measures absolute return frequency relative to changing regional volumes).

### Business Insights Discovered
* **Inventory Deficits:** Discovered a massive financial drain in the **Tables** sub-category. Despite healthy revenue volumes, high return frequencies completely eliminate its net profit margin.
* **Managerial Accountability:** Isolated clear performance variances across territory heads (Chuck, Fred, Roxanne) by benchmarking their baseline operational return rates.
* **Command Hub Interactivity:** Implemented global cross-filtering via a geographic map vector, enabling users to click any U.S. state to auto-filter manager metrics and product lines simultaneously.

---

## 🛠️ How to Explore These Projects
1. Download either the `.twbx` files from this repository.
2. Open them natively inside Tableau Desktop or Tableau Public to explore the interactive dashboard filters.

## 🌐 Live Interactive Dashboards
You can interact with these dashboards directly in your web browser without downloading any software:
* 👉 [View Executive Performance Dashboard on Tableau Public](https://public.tableau.com/app/profile/swathi.b7910/viz/Executive_Performance_Dashboard/EXECUTIVEPERFORMANCEDASHBOARD)
* 👉 [View Supply Chain & Returns Optimization on Tableau Public](https://public.tableau.com/app/profile/swathi.b7910/viz/Supply_Chain_Returns_Optimization/SUPPLYCHAINRISKRETURNSOPTIMIZATION)
