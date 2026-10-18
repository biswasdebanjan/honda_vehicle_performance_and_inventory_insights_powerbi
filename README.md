# Honda Vehicle Performance, Pricing & Inventory Insights

> A Power BI case study examining vehicle performance, customer
> perception, pricing, depreciation, and inventory positioning to
> understand how these signals interact across a vehicle portfolio.

**Power BI · Power Query · Exploratory Analysis · Segmentation ·
Business Intelligence**

![Honda Vehicle Performance Dashboard](screenshots/01_project_hub.png)

------------------------------------------------------------------------

## The Business Question

Vehicle performance, customer perception, pricing, and inventory are
often examined independently.

This project looks at them as **one connected portfolio problem**.

> **Which vehicle models are performing well, how does customer
> perception relate to value, how does vehicle age affect pricing and
> experience, and where should inventory and portfolio strategy be
> adjusted?**

The objective was not simply to report vehicle KPIs, but to move from
descriptive performance information toward commercially useful decisions
around **pricing, inventory, model positioning, and customer
perception**.

The analytical story can be summarized as:

**Performance → Perception → Pricing → Inventory → Strategic Action**

------------------------------------------------------------------------

## Project at a Glance

  -----------------------------------------------------------------------
  Area                                Details
  ----------------------------------- -----------------------------------
  **Domain**                          Automotive

  **Primary Tool**                    Power BI

  **Data Preparation**                Power Query

  **Dataset**                         Publicly available Honda vehicle
                                      data

  **Records**                         4,999 vehicle records

  **Models**                          145 models represented in the final
                                      analytical dashboard

  **Core Focus**                      Performance, customer perception,
                                      pricing, depreciation, and
                                      inventory

  **Segmentation**                    Vehicle Age and Review Volume

  **Output**                          5-page interactive Power BI report
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## What I Investigated

The analysis was organized around five connected questions.

### 01 --- Vehicle Performance & Customer Perception

Which models demonstrate stronger customer satisfaction, reliability,
value perception, and overall product experience?

The analysis considers:

-   Customer ratings
-   Reliability
-   Value-for-money
-   Comfort
-   Interior design
-   Exterior styling
-   Performance
-   Review volume
-   Model positioning

The objective was not simply to identify the highest-rated vehicles, but
to understand **which models combine customer perception with meaningful
market presence**.

### 02 --- Pricing & Value

How does vehicle pricing behave across condition, age, and market
positioning?

The analysis examines:

-   Average vehicle price
-   New vs used pricing
-   Price depreciation
-   Vehicle age
-   Price positioning
-   Premium models
-   Value-oriented segments

Rather than treating used vehicles simply as a cheaper version of new
vehicles, the analysis considers **how value changes across the vehicle
lifecycle**.

### 03 --- Inventory Intelligence

Where is inventory value concentrated, and what does the composition of
that inventory suggest?

The analysis looks at:

-   Inventory value
-   Vehicle age
-   Vehicle condition
-   Review-popularity segments
-   Fuel type
-   Drivetrain
-   Seller and ownership characteristics
-   Geographic markets
-   Model concentration

This provides a basis for distinguishing vehicles that may warrant
**scaling, protection, selective expansion, repositioning, or
rationalization**.

### 04 --- Customer Advocacy

Does customer engagement provide a useful signal for understanding model
strength?

Review volume is treated as an additional lens for understanding
**consumer attention and model positioning**, rather than being
interpreted in isolation from ratings and vehicle characteristics.

### 05 --- Portfolio Opportunities

The final question is strategic:

> **Which parts of the portfolio should be protected, scaled,
> repositioned, or investigated further?**

The analysis therefore ends with portfolio-level recommendations rather
than stopping at descriptive charts.

------------------------------------------------------------------------

## Analytical Approach

The project followed a deliberate analytical workflow rather than
beginning with dashboard construction.

``` text
Raw Data
   ↓
Data Preparation
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

### 1. Data Preparation

The raw dataset was prepared in Power Query.

The transformation process included:

-   Promoting the source headers
-   Cleaning the `Price` field
-   Removing currency symbols and thousands separators
-   Converting `Not Priced` entries to `0`
-   Changing data types
-   Renaming `Consumer_Review_#` to `Consumer_Review`
-   Removing unnecessary fields
-   Standardizing inconsistent `State` values
-   Applying the existing row-filter steps in the query

The removed fields included:

-   `VIN`
-   `Stock_#`
-   `Exterior_Color`
-   `Interior_Color`

Problematic or unusable `State` values---including blanks and values
such as `Glens`, `Route`, and `MO-22`---were standardized to `unknown`.

The preparation therefore served three purposes:

**Make the data analytically usable → reduce unnecessary fields →
standardize inconsistent categorical values.**

### 2. Column-Level Exploration

After preparation, the fields were explored individually to understand:

-   Data types
-   Distributions
-   Missing values
-   Categorical variation
-   Numerical ranges
-   Potential analytical dimensions

This exploration helped determine which variables could support
meaningful business segmentation.

### 3. Segmentation Before Analysis

Segmentation was established before the main business analysis.

Thresholds were selected using distribution analysis, histogram
evaluation, percentile assessment, and business interpretability.

Two principal calculated segmentation frameworks were developed:

**Vehicle Age**

-   New Model --- 0--2 years
-   Recent Model --- 3--5 years
-   Mature Model --- 6+ years

**Review Volume**

-   Niche Model --- \<150 reviews
-   Emerging Favorite --- 150--749 reviews
-   Popular Model --- 750--1,999 reviews
-   Consumer Favorite --- ≥2,000 reviews

These segments were then used to compare vehicle performance, customer
perception, pricing, depreciation, and inventory positioning.

------------------------------------------------------------------------

## From Data to Decision

A central principle of the project was to avoid evaluating vehicles
through isolated metrics.

The analysis connects:

**Vehicle Performance → Customer Perception → Pricing & Value → Vehicle
Lifecycle & Depreciation → Inventory Positioning → Portfolio Action**

Vehicle age is therefore not treated simply as a numeric field. It
becomes a lifecycle dimension that can be examined alongside price,
customer perception, and inventory value.

Similarly, review volume is not treated as a standalone popularity
ranking. It becomes an additional signal that can be considered
alongside customer ratings and portfolio positioning.

This creates a more decision-oriented view of the vehicle portfolio.

------------------------------------------------------------------------

## Key Portfolio Signals

The dashboard establishes several headline signals across the dataset.

### Customer Perception

-   **Average Customer Rating:** 4.57
-   **Average Reliability Rating:** 4.87
-   **Average Value-for-Money Rating:** 4.58

These portfolio averages provide context, while the model-level analysis
examines differences in customer perception and engagement.

### New vs Used Market

-   **Average New Vehicle Price:** 39.05K
-   **Average Used Vehicle Price:** 26.10K
-   **Used Vehicle Share:** 40.45%

The size of the used-vehicle component makes used inventory an important
part of the observed portfolio.

### Hybrid Presence

The dashboard reports an **11.76% Hybrid Vehicle Share**.

The analysis therefore treats hybrid vehicles as a portfolio-positioning
question, examining where hybrid models can create a compelling
combination of customer experience and perceived value.

### Vehicle Lifecycle

  Segment              Definition
  ------------------ ------------
  **New Model**        0--2 years
  **Recent Model**     3--5 years
  **Mature Model**       6+ years

### Customer Engagement

  Segment                   Review Volume
  ----------------------- ---------------
  **Niche Model**                   \<150
  **Emerging Favorite**          150--749
  **Popular Model**            750--1,999
  **Consumer Favorite**            ≥2,000

------------------------------------------------------------------------

## Strategic Recommendations

The analysis was translated into ten strategic recommendations:

1.  **Three-Tier Portfolio Strategy**
2.  **Scale Honda Certified as the Strategic Bridge**
3.  **Intervene Before the Mature-Vehicle Risk Cliff**
4.  **Turn Used Variety into Curated Choice**
5.  **Reposition Hybrid Around Value & Experience**
6.  **Expand Winning Hybrids Selectively**
7.  **Make MPG Transparency a Core Value Lever**
8.  **Prioritize Mature Vehicles with Missing MPG Data**
9.  **Use Customer Advocacy as an Investment Signal**
10. **Build a Multi-Signal Vehicle Decision Engine**

Detailed recommendation logic is documented separately in
`docs/recommendations.md`.

------------------------------------------------------------------------

## Power BI Dashboard

The final report is organized as a business-facing analytical narrative.

### 01 --- Project Hub

Introduces the project context, business objectives, analytical scope,
and navigation structure.

![Project Hub](screenshots/01_project_hub.png)

### 02 --- Vehicle Performance & Customer Perception

Examines vehicle performance, customer ratings, reliability, value
perception, vehicle experience, review engagement, model positioning,
and lifecycle.

![Vehicle Performance & Customer
Perception](screenshots/02_performance.png)

### 03 --- Pricing & Inventory Insights

Connects new vs used pricing, depreciation, inventory value, vehicle
age, condition, price positioning, fuel/drivetrain patterns, and
portfolio composition.

![Pricing & Inventory Insights](screenshots/03_pricing_inventory.png)

### 04 --- Executive Action Plan

Translates the analytical findings into ten strategic recommendations.

![Executive Action Plan](screenshots/04_executive_actions.png)

### 05 --- Segmentation Framework

Documents the definitions behind the analytical segments used throughout
the report.

![Segmentation Framework](screenshots/05_segmentations.png)

------------------------------------------------------------------------

## Dashboard Architecture

``` text
PROJECT HUB
     ↓
PERFORMANCE
     ↓
PRICING & INVENTORY
     ↓
ACTION PLAN
     ↓
SEGMENTATION REFERENCE
```

The presentation order should not be confused with the analytical
workflow. Segmentation was established during the analysis phase; the
final Segmentation Framework page exists as a stakeholder reference.

------------------------------------------------------------------------

## Data & Provenance

> **Publication note:** The original source CSV is not redistributed in this repository at this stage because the source dataset's current redistribution terms need to be verified. See `data/README.md` for provenance and the publication decision.

This project uses the publicly available **Honda Data** dataset
published on Kaggle by `omartorres25`.

**Source:** [Honda Data ---
Kaggle](https://www.kaggle.com/datasets/omartorres25/honda-data)

The dataset was prepared and transformed in Power Query before being
used for analysis in Power BI.

> **Publication note:** The final repository dataset should be published
> only after checking the source dataset's current licence and
> redistribution terms. Fields such as VIN and Stock Number should not
> be published unnecessarily.

------------------------------------------------------------------------

## Repository Structure

``` text
honda-vehicle-performance-analysis/
│
├── README.md
│
├── data/
│   └── README.md   # source & redistribution note
│
├── powerbi/
│   └── Honda_Vehicle_Performance_Analysis.pbix
│
├── screenshots/
│   ├── 01_project_hub.png
│   ├── 02_performance.png
│   ├── 03_pricing_inventory.png
│   ├── 04_executive_actions.png
│   └── 05_segmentations.png
│
└── docs/
    ├── analytical-approach.md
    ├── segmentation-framework.md
    └── recommendations.md
```

------------------------------------------------------------------------

## Tools & Skills

-   **Power BI** --- data modeling, measures, interactive reporting,
    visualization, and business storytelling
-   **Power Query** --- data preparation, transformation, value
    standardization, data typing, and analytical dataset preparation
-   **Git & GitHub** --- version control, project documentation, and
    portfolio publication

------------------------------------------------------------------------

## Project Perspective

The purpose of this project was to move beyond a conventional vehicle
dashboard.

The analysis connects **performance, customer perception, pricing,
vehicle lifecycle, and inventory** into one portfolio-level view.

The resulting decision chain is:

> **Understand the portfolio → identify where value is created or
> exposed → determine which signals matter → translate evidence into
> action.**

The final report is designed not only to answer **"What does the data
say?"**, but also:

> **"What should we pay attention to next?"**
