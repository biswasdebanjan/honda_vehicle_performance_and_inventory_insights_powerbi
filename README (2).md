<div align="center">

# 🚗 Honda Vehicle Performance, Pricing & Inventory Insights

### A Power BI case study connecting vehicle performance, customer perception, pricing, depreciation, and inventory into one portfolio-level view.

**Project Status · Completed**

</div>

---

## 📊 Project Overview

This project examines Honda vehicle data to understand how **vehicle performance, customer perception, pricing, vehicle lifecycle, and inventory composition** interact across a vehicle portfolio.

The analysis follows one connected business story:

> **Performance → Perception → Pricing → Inventory → Strategic Action**

The goal was to move beyond isolated KPI reporting and identify where the portfolio presents opportunities to **scale, protect, reposition, selectively expand, or rationalize**.

---

## 🎯 Business Question

> **How should Honda evaluate vehicle performance, customer perception, pricing, depreciation, and inventory as one connected portfolio problem?**

The analysis focuses on five connected areas:

- 🚘 Vehicle performance and customer perception
- 💰 Pricing and value positioning
- 📦 Inventory composition and value
- ⭐ Customer advocacy and review engagement
- 🎯 Portfolio-level strategic opportunities

---

## 🗂️ Dataset

| Attribute | Detail |
|---|---|
| **Domain** | Automotive |
| **Source** | Kaggle — Honda Data (`omartorres25`) |
| **Records** | **4,999** vehicle records |
| **Models** | **145** models represented in the final dashboard |
| **Granularity** | Vehicle-level records |
| **Primary Tool** | Power BI |
| **Data Preparation** | Power Query |
| **Core Segmentation** | Vehicle Age & Review Volume |

🔗 [Honda Data — Kaggle](https://www.kaggle.com/datasets/omartorres25/honda-data)

> **Publication note:** The original source CSV is not redistributed at this stage because its current redistribution terms need to be verified. Fields such as VIN and Stock Number should also not be published unnecessarily.

---

## 🛠️ Tools & Technologies

- **Power BI** — data modeling, DAX, interactive analysis and dashboarding
- **Power Query** — data preparation, transformation, typing and standardization
- **DAX** — KPI measures and analytical calculations
- **Git / GitHub** — version control, documentation and portfolio publication

---

## 🔄 Analytical Workflow

The project was developed through an analytical workflow rather than beginning with dashboard construction.

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
Insight Development
   ↓
Strategic Recommendations
   ↓
Power BI Dashboard
```

### Why segmentation came before the main analysis

Vehicle Age and Review Volume were defined after exploring the distributions and considering business interpretability. These segments were then used throughout the analysis.

The segmentation page in the final report is therefore a **reference page for stakeholders**, not the point at which segmentation was created.

---

## 🧹 Data Preparation

The raw Honda dataset was prepared in Power Query before the analytical model was built.

### Key transformations

- Promoted the source headers
- Removed `$` from `Price`
- Converted `Not Priced` entries in `Price` to `0`
- Removed comma separators from `Price`
- Applied appropriate data types
- Renamed `Consumer_Review_#` to `Consumer_Review`
- Removed unnecessary fields
- Standardized problematic `State` values
- Applied the existing row-filter steps in the query

### Fields removed

- `VIN`
- `Stock_#`
- `Exterior_Color`
- `Interior_Color`

Blank or inconsistent `State` values, including values such as `Glens`, `Route`, and `MO-22`, were standardized to `unknown`.

---

## 🧩 Analytical Framework

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

These definitions were established using distribution analysis, histogram evaluation, percentile assessment and business interpretability.

---

## 🔍 What the Analysis Examines

### 01 — 🚘 Performance & Customer Perception

The performance analysis combines:

- Customer ratings
- Reliability
- Value-for-money
- Comfort
- Interior design
- Exterior styling
- Performance
- Review volume
- Model positioning
- Vehicle age

The emphasis is on understanding which models combine **customer perception, performance and meaningful market presence**.

### 02 — 💰 Pricing & Value

The pricing analysis examines:

- Average vehicle price
- New vs used pricing
- Price depreciation
- Vehicle age
- Price positioning
- Premium models
- Value-oriented segments

### 03 — 📦 Inventory Intelligence

Inventory is evaluated through:

- Inventory value
- Vehicle age
- Vehicle condition
- Fuel type
- Drivetrain
- Review-popularity segments
- Seller / ownership characteristics
- Geographic markets
- Model concentration

The purpose is to connect inventory composition with portfolio-level decision making.

---

# 📈 Dashboard

The README intentionally showcases the **two core analytical dashboard pages**. The remaining report pages are supporting extensions and documentation rather than the primary analytical views.

---

## 01 — Vehicle Performance & Customer Perception

The first core dashboard brings together model positioning, vehicle experience, lifecycle effects, customer ratings, review engagement and drivetrain mix.

It establishes the **performance and perception** side of the portfolio story.

![Vehicle Performance & Customer Perception](screenshots/01_performance.png)

---

## 02 — Vehicle Pricing & Inventory Insights

The second core dashboard connects price positioning, new-vs-used value, inventory value, depreciation, premium models, geographic inventory concentration and review-popularity segments.

It establishes the **pricing and inventory** side of the portfolio story.

![Vehicle Pricing & Inventory Insights](screenshots/02_pricing_inventory.png)

---

## 💡 Key Portfolio Signals

The dashboards establish several headline signals across the observed portfolio:

| Metric | Signal |
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

These headline measures provide portfolio context; the dashboard then breaks the portfolio down by model, lifecycle, review engagement, price and inventory characteristics.

---

## 🎯 Strategic Recommendations

The analysis was translated into ten strategic recommendations:

1. **Three-Tier Portfolio Strategy**
2. **Scale Honda Certified as the Strategic Bridge**
3. **Intervene Before the Mature-Vehicle Risk Cliff**
4. **Turn Used Variety into Curated Choice**
5. **Reposition Hybrid Around Value & Experience**
6. **Expand Winning Hybrids Selectively**
7. **Make MPG Transparency a Core Value Lever**
8. **Prioritize Mature Vehicles with Missing MPG Data**
9. **Use Customer Advocacy as an Investment Signal**
10. **Build a Multi-Signal Vehicle Decision Engine**

Detailed recommendation logic is documented in [`docs/recommendations.md`](docs/recommendations.md).

---

## 🧠 From Data to Decision

A central principle of the project was to avoid evaluating vehicles through isolated metrics.

The analytical chain connects:

```text
Vehicle Performance
        ↓
Customer Perception
        ↓
Pricing & Value
        ↓
Vehicle Lifecycle & Depreciation
        ↓
Inventory Positioning
        ↓
Portfolio Action
```

The final objective is therefore not simply to identify the highest-rated or highest-priced vehicles, but to understand **where different signals converge and what that implies for portfolio decisions**.

---

## 📚 Documentation

The repository separates the visual portfolio experience from the deeper technical documentation.

| Document | Purpose |
|---|---|
| [`analytical-approach.md`](docs/analytical-approach.md) | Detailed analytical workflow and reasoning |
| [`segmentation-framework.md`](docs/segmentation-framework.md) | Segment definitions and business rules |
| [`recommendations.md`](docs/recommendations.md) | Detailed strategic recommendation logic |
| [`dax-calculations.md`](docs/dax-calculations.md) | DAX measures, calculated fields and calculation notes |

The README acts as the **front door**; the supporting Markdown files provide deeper technical detail for readers who want to understand how the analysis was constructed.

---

## 📁 Repository Structure

```text
honda-vehicle-performance-and-inventory-insights/
│
├── README.md
├── .gitignore
│
├── data/
│   └── README.md
│
├── powerbi/
│   ├── Honda_Vehicle_Performance_Analysis.pbix
│   └── README.md
│
├── screenshots/
│   ├── 01_performance.png
│   └── 02_pricing_inventory.png
│
└── docs/
    ├── analytical-approach.md
    ├── segmentation-framework.md
    ├── recommendations.md
    └── dax-calculations.md
```

---

## ▶️ How to Run This Project

### Requirements

- **Power BI Desktop**
- The repository files
- Access to the source dataset if the PBIX needs to be refreshed

### Steps

1. Clone or download this repository.
2. Open `powerbi/Honda_Vehicle_Performance_Analysis.pbix` in Power BI Desktop.
3. Review the two core analytical dashboard pages.
4. If a refresh is required, configure the source according to `data/README.md`.
5. Refer to the files in `docs/` for the analytical methodology, segmentation definitions, recommendations and DAX documentation.

> **Important:** The source CSV is not currently redistributed because its current licence / redistribution terms have not been verified. The PBIX should therefore not be assumed to be immediately refreshable on another machine without access to the source data.

---

## 🏁 Results & Conclusion

This project brings together **vehicle performance, customer perception, pricing, lifecycle and inventory** into one portfolio-level analytical framework.

The final decision logic is:

> **Understand the portfolio → identify where value is created or exposed → determine which signals matter → translate evidence into action.**

The dashboard is therefore designed to answer both:

**What does the portfolio look like?**

and

**Where should management pay attention?**

---

## 🔮 Future Work

Potential extensions include:

- Adding historical pricing and inventory data to study movement over time
- Developing more granular dealership-level analysis where suitable data is available
- Building a formal vehicle-level portfolio scoring framework
- Extending depreciation analysis into predictive resale-value modeling
- Adding automated refresh and a repeatable data pipeline
- Exploring predictive approaches for vehicle demand and inventory risk

---

## 📝 Data & Provenance

This project uses the publicly available **Honda Data** dataset published on Kaggle by `omartorres25`.

**Source:** [Honda Data — Kaggle](https://www.kaggle.com/datasets/omartorres25/honda-data)

The source data was prepared in Power Query before being used for analysis in Power BI.

> **Publication note:** Check the source dataset's current licence and redistribution terms before publishing or redistributing the raw data. VIN and Stock Number fields should not be published unnecessarily.

---

## 👤 Author

**Debanjan Biswas**  
Data Analyst | SQL | Power BI | Python

---

<div align="center">

### 🚗 Performance → Perception → Pricing → Inventory → Action

**Built with Power BI**

</div>
