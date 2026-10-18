<div align="center">

# 🚗 Honda Vehicle Performance, Pricing & Inventory Insights

### A Power BI portfolio project exploring vehicle performance, customer perception, pricing and inventory.

<img src="screenshots/00_title_card.png" alt="Honda Vehicle Performance, Pricing & Inventory Insights" width="100%">

**📌 Project Status: Completed**

</div>

---

## 📊 Project Overview

This project analyzes **4,999 Honda vehicle records** to understand how vehicle performance, customer perception, pricing, vehicle age and inventory characteristics connect across a vehicle portfolio.

It was created primarily as a **practical Power BI practice project** — to strengthen skills in Power Query, DAX, segmentation, dashboard design and business-oriented analysis — while also developing a portfolio-ready Data Analytics project.

The core analytical story is simple:

> **Performance → Perception → Pricing → Inventory → Action**

The goal was not just to build charts, but to turn the data into a clearer view of **where the portfolio is performing well, where attention may be needed, and what actions could follow from the analysis.**

---

## 🎯 Business Question

> **How should Honda evaluate vehicle performance, customer perception, pricing, depreciation and inventory as one connected portfolio problem?**

The analysis looks at five connected areas:

- 🚘 Vehicle performance & customer perception
- 💰 Pricing & value positioning
- 📦 Inventory value & composition
- ⭐ Customer reviews & model popularity
- 🎯 Portfolio opportunities and actions

---

## 🗂️ Dataset

| Attribute | Detail |
|---|---|
| **Domain** | Automotive |
| **Source** | Kaggle — Honda Data (`omartorres25`) |
| **Records** | **4,999** vehicle records |
| **Models** | **145** models represented in the final dashboard |
| **Granularity** | Vehicle-level |
| **Main Tool** | Power BI |
| **Data Preparation** | Power Query |
| **Main Segments** | Vehicle Age & Review Volume |

🔗 **Source:** [Honda Data — Kaggle](https://www.kaggle.com/datasets/omartorres25/honda-data)

> **Publication note:** The original source CSV is not redistributed at this stage because its current redistribution terms need to be verified. VIN and Stock Number fields are also excluded from the analytical dataset.

---

## 🛠️ Tools & Technologies

- **Power BI** — data modeling, DAX, analysis and dashboard design
- **Power Query** — data cleaning and transformation
- **DAX** — KPIs, calculations and analytical logic
- **Git / GitHub** — project documentation and version control

---

## 🔄 Analytical Workflow

The project followed a structured analytical process before the final dashboard was built:

```text
Raw Data
   ↓
Power Query Preparation
   ↓
Column-Level Exploration
   ↓
Segmentation Design
   ↓
Business Analysis
   ↓
Insights
   ↓
Recommendations
   ↓
Power BI Dashboard
```

### Why segmentation came early

Vehicle Age and Review Volume were defined **before the main analysis** after examining distributions and considering business interpretability. The final segmentation page is therefore a reference for users, not the stage where the segments were created.

📄 [Read the full Analytical Approach →](./docs/analytical-approach.md)

---

## 🧹 Data Preparation

The raw data was prepared in Power Query before analysis.

### Main cleaning steps

- Promoted the source headers
- Cleaned the `Price` field
- Removed `$` and comma separators from price values
- Converted `Not Priced` to `0`
- Applied appropriate data types
- Renamed `Consumer_Review_#` to `Consumer_Review`
- Removed fields that were not needed for the analysis
- Standardized inconsistent `State` values

### Fields removed

- `VIN`
- `Stock_#`
- `Exterior_Color`
- `Interior_Color`

Blank or inconsistent state values such as `Glens`, `Route` and `MO-22` were standardized to `unknown`.

---

## 🧩 Analytical Framework

Two main segments were used throughout the analysis.

### 🚘 Vehicle Age

| Segment | Definition |
|---|---:|
| **New Model** | 0–2 years |
| **Recent Model** | 3–5 years |
| **Mature Model** | 6+ years |

### ⭐ Review Volume

| Segment | Definition |
|---|---:|
| **Niche Model** | <150 reviews |
| **Emerging Favorite** | 150–749 reviews |
| **Popular Model** | 750–1,999 reviews |
| **Consumer Favorite** | ≥2,000 reviews |

These thresholds were established using distribution analysis, histogram evaluation, percentile assessment and business interpretability.

📄 [Read the Segmentation Framework →](./docs/segmentation-framework.md)

---

# 📈 Core Dashboard

The README focuses on the **two main analytical dashboard pages**. The remaining report pages support the project with recommendations and segmentation definitions.

## 01 — Vehicle Performance & Customer Perception

This page looks at:

- Model positioning
- Customer ratings
- Reliability
- Value-for-money
- Vehicle experience
- Review volume
- Vehicle age
- Fuel and drivetrain mix

It answers the first part of the story: **How are the vehicles performing, and how are customers responding to them?**

<img src="screenshots/01_performance.png" alt="Vehicle Performance and Customer Perception dashboard" width="100%">

---

## 02 — Vehicle Pricing & Inventory Insights

This page looks at:

- Average vehicle price
- New vs used pricing
- Used vehicle share
- Hybrid share
- Value positioning
- Inventory value
- Price depreciation
- Premium models
- Market-level inventory value
- Review popularity and inventory value

It answers the second part of the story: **How is value distributed across the portfolio, and where is inventory concentrated?**

<img src="screenshots/02_pricing_inventory.png" alt="Vehicle Pricing and Inventory Insights dashboard" width="100%">

---

## 💡 Key Portfolio Signals

| Metric | Value |
|---|---:|
| **Total Vehicles** | **4,999** |
| **Vehicle Models** | **145** |
| **Average Customer Rating** | **4.57** |
| **Average Reliability Rating** | **4.87** |
| **Average Value-for-Money Rating** | **4.58** |
| **Average Vehicle Price** | **33.45K** |
| **Average New Vehicle Price** | **39.05K** |
| **Average Used Vehicle Price** | **26.10K** |
| **Used Vehicle Share** | **40.45%** |
| **Hybrid Vehicle Share** | **11.76%** |

These figures provide the portfolio-level context. The dashboards then break them down by model, age, reviews, price, condition and inventory characteristics.

---

# 🎯 Executive Action Plan

The analysis was translated into **10 simple business actions**. The idea is straightforward: use the strongest signals from the data to decide where to scale, protect, improve or investigate.

<img src="screenshots/03_executive_actions.png" alt="Honda Executive Action Plan — Top 10 Recommendations" width="100%">

### The recommendations in simple terms

**01 — Build a clear three-tier portfolio**  
Give New, Used and Honda Certified vehicles clear roles instead of treating them the same.

**02 — Use Honda Certified as the bridge**  
Expand Certified vehicles selectively to offer stronger buying confidence without paying the full new-vehicle premium.

**03 — Act before vehicles become too old**  
Use pricing, reconditioning or exit decisions earlier as vehicles move into the mature stage.

**04 — Reduce weak used-vehicle variety**  
Focus inventory on used models that customers actually respond to instead of carrying too much low-interest variety.

**05 — Improve the hybrid value story**  
Communicate hybrid benefits around overall value and customer experience, not reliability alone.

**06 — Invest selectively in winning hybrids**  
Put more attention on hybrid models that already show strong customer response.

**07 — Make MPG information clearer**  
Complete missing MPG information so customers can compare vehicles more confidently.

**08 — Prioritize mature vehicles with missing MPG data**  
Fix information gaps first where older vehicles also need stronger value communication or inventory decisions.

**09 — Use customer reviews as a decision signal**  
Bring review activity into model and inventory decisions instead of looking only at ratings.

**10 — Combine multiple signals before making decisions**  
Consider age, fuel type, MPG, reviews, ratings, reliability and inventory value together rather than relying on one KPI.

📄 [Read the detailed recommendation logic →](./docs/recommendations.md)

---

## 🧠 From Data to Decision

The project connects the main signals in one chain:

```text
Vehicle Performance
        ↓
Customer Perception
        ↓
Pricing & Value
        ↓
Vehicle Age & Depreciation
        ↓
Inventory Positioning
        ↓
Portfolio Action
```

This means the analysis is not simply asking **which vehicle has the highest rating**. It asks how several signals work together when making portfolio decisions.

---

## 📚 Project Documentation

The README is the **visual front door** of the project. The supporting Markdown files contain the deeper technical details.

| Document | What it contains |
|---|---|
| [📘 Analytical Approach](./docs/analytical-approach.md) | How the analysis was planned and carried out |
| [🧩 Segmentation Framework](./docs/segmentation-framework.md) | Segment definitions and business rules |
| [🎯 Recommendations](./docs/recommendations.md) | Detailed reasoning behind the 10 actions |
| [📐 DAX Calculations](./docs/dax-calculations.md) | Measures, calculated fields and DAX notes |

These links are **relative repository links**, so they will open directly once the complete repository is uploaded to GitHub.

---

## ▶️ How to Run the Project

### Requirements

- Power BI Desktop
- This repository
- Access to the original source dataset if the PBIX needs to be refreshed

### Steps

1. Clone or download the repository.
2. Open `powerbi/Honda_Vehicle_Performance_Analysis.pbix` in Power BI Desktop.
3. Explore the two core dashboard pages.
4. If you need to refresh the report, provide the source dataset and update the data-source path.
5. Use the `docs/` folder if you want to understand the methodology, segmentation, recommendations or DAX.

> **Note:** The original CSV is not currently redistributed because its current licence / redistribution terms have not been verified.

---

## 🏁 Results & Conclusion

This project brings together **performance, customer perception, pricing, vehicle lifecycle and inventory** into one portfolio-level view.

The main outcome is a simple decision framework:

> **Understand the portfolio → identify where attention is needed → combine the relevant signals → take action.**

The project was also a practical exercise in using Power BI to move from **raw data → analysis → business insight → recommendation**.

---

## 🔮 Future Work

Possible extensions include:

- Add historical pricing and inventory data to study changes over time
- Build a more detailed dealership-level view
- Create a formal vehicle-level portfolio score
- Extend depreciation analysis into predictive resale-value modeling
- Add automated refresh and a repeatable data pipeline
- Explore predictive models for vehicle demand and inventory risk

---

## 📝 Data & Provenance

The project uses the publicly available **Honda Data** dataset published on Kaggle by `omartorres25`.

🔗 [Honda Data — Kaggle](https://www.kaggle.com/datasets/omartorres25/honda-data)

The dataset was prepared in Power Query and analyzed in Power BI.

> **Publication note:** Check the source dataset's current licence and redistribution terms before publishing or redistributing the raw data.

---

## 👤 Author

**Debanjan Biswas**  
Data Analyst | SQL | Power BI | Python

📧 **Email:** [bishwasdebanjan99@gmail.com](mailto:bishwasdebanjan99@gmail.com)

This project was created as a **practical Power BI practice project** to strengthen my skills in data preparation, DAX, analytical thinking, dashboard design and business storytelling, while building my Data Analytics portfolio.

---

<div align="center">

### 🚗 Performance → Perception → Pricing → Inventory → Action

**Built with Power BI**

</div>
