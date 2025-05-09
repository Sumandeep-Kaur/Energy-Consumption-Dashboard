# Energy Consumption Dashboard
![Overview](https://github.com/user-attachments/assets/c7f6b8ae-8e20-443a-963e-7e8715f3f70f)

## 📊 Project Overview
The **Energy Consumption Dashboard** is an interactive Power BI tool designed to monitor, analyze, and visualize energy usage—including **electricity**, **gas**, and **water**, across multiple cities and buildings.  
It provides key insights into energy costs, usage patterns, and consumption trends to enable data-driven decision-making and cost optimization.  
This dashboard serves **facility managers**, **sustainability teams**, and **executives** by helping them identify inefficiencies, reduce energy costs, and improve operational sustainability.

---

## 🎯 Objectives

✅ Track and evaluate **electricity, gas, and water** usage.  
✅ Analyze historical trends and forecast consumption growth.  
✅ Identify high-cost, high-consumption buildings to target for savings.  
✅ Provide an intuitive, interactive dashboard for stakeholders.  
✅ Leverage effective **data modeling**, **DAX**, and **optimization** for high performance.

---

## 🚀 Project Workflow

### 1️⃣ Data Collection & ETL (Extract, Transform, Load)

- **Data Sources:**  
  - Excel File

Collected **monthly energy consumption data** from **2016 to 2019** for multiple cities and buildings.

- **Data Cleaning & Transformation:**  
  - Handled outliers, missing values, and inconsistencies using **Power Query (M language)**.  
  - Reformatted dates for trend analysis.  
  - Aggregated data for analytical consistency.

- **Data Modeling:**  
  - Built **Fact** and **Dimension** tables.  
  - Designed a **Star Schema** for optimized relationships.  
  - Enhanced query efficiency for fast dashboard loading.

---

### 2️⃣ Dashboard Development & Design

The dashboard is divided into **three main sections**:

### ⚡ Electricity Overview
![Electricity](https://github.com/user-attachments/assets/2b4dde00-5d43-43aa-bd89-2128bdeccbd4)

**Key Features:**
- **Total Electricity Cost (Millions):** Overall electricity spending.
- **Total Electricity Units Consumed (Millions):** Total energy used in selected timeframe.
- **Filters:** City, Building, Date Range selectors.
- **Monthly Cost Trend:** Line chart showing electricity cost over time.
- **Cost by City:** Pie chart visualizing which cities spend most on electricity.
- **Cost by Building:** Bar chart identifying top-consuming buildings.
- **Detailed Table:** Breakdown by Year, Quarter, Month, Units, and Total Cost.

---

### 🔥 Gas Overview
![Gas](https://github.com/user-attachments/assets/c4b4d4a7-1315-4c31-89e3-4c688a8d1f8f)

**Key Features:**
- Similar structure to Electricity tab.
- Focuses on **gas consumption** metrics.
- Dedicated charts for gas-specific trends by **city** and **building**.

---

### 💧 Water Overview
![Water](https://github.com/user-attachments/assets/20619830-dac2-4930-8ab5-796117609fc0)

**Key Features:**
- Same KPI structure for **water consumption**.
- Visualization of water-related costs and usage trends.
- Identify water-intensive buildings or areas.

---

### 🏠 Main KPI Metrics

- **Total Cost (Millions)**
- **Total Units Consumed (Millions)**
- **Filters:** City, Building, Date Range
- **Trend Analysis:** Time-series charts
- **Cost by City & Building:** Pie & bar charts
- **Detailed Table View:** Full breakdown for deeper insights

---

## 📝 DAX Measures Used

```DAX
Total Cost = SUM(ConsumptionData[Total Cost])
Total Units = SUM(ConsumptionData[Unit Consumed])

YoY Growth = 
VAR PrevYear = CALCULATE(SUM(ConsumptionData[Total Cost]), SAMEPERIODLASTYEAR(Date[Date]))
RETURN IF(ISBLANK(PrevYear), BLANK(), (SUM(ConsumptionData[Total Cost]) - PrevYear) / PrevYear)
