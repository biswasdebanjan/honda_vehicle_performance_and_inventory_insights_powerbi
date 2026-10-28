# DAX Calculations — Honda Vehicle Performance, Pricing & Inventory Insights

## Purpose

This document records the key DAX calculations used to support the Honda Power BI analysis.

The goal is not to list every trivial Power BI field. Instead, it documents the calculations that demonstrate the analytical logic behind the dashboard:

- Core KPI measures
- Pricing and inventory measures
- Customer-perception measures
- Portfolio-share measures
- Vehicle lifecycle segmentation
- Review-volume segmentation
- Supporting calculated fields used by the report

The calculation layer sits between the prepared dataset and the dashboard:

```text
Prepared Data
      ↓
Calculated Columns / Business Definitions
      ↓
DAX Measures
      ↓
Visual Analysis
      ↓
Insights
      ↓
Executive Recommendations
```

---

## 1. Core KPI Measures

### Total Vehicles

**Business purpose:** Counts the vehicle records represented in the analytical dataset.

```DAX
Total Vehicles =
COUNTROWS(honda_car)
```

**Used for:** Executive KPI cards, portfolio analysis and denominator calculations.

---

### Distinct Models

**Business purpose:** Counts the unique vehicle models represented in the report.

```DAX
Distinct Models =
DISTINCTCOUNT(honda_car[Model])
```

**Used for:** Portfolio breadth and model-count KPIs.

---

### Average Vehicle Price

**Business purpose:** Calculates the average listed vehicle price.

```DAX
Avg Vehicle Price =
AVERAGE(honda_car[Price])
```

**Used for:** Pricing analysis and portfolio-level price positioning.

---

### Average New Vehicle Price

**Business purpose:** Measures average price for vehicles classified as new.

```DAX
Avg New Vehicle Price =
CALCULATE(
    [Avg Vehicle Price],
    honda_car[Condition] = "New"
)
```

**Used for:** New-vs-used pricing comparison.

---

### Average Used Vehicle Price

**Business purpose:** Measures average price for vehicles classified as used.

```DAX
Avg Used Vehicle Price =
CALCULATE(
    [Avg Vehicle Price],
    honda_car[Condition] = "Used"
)
```

**Used for:** Used-market pricing and value analysis.

---

## 2. Customer Perception Measures

### Average Consumer Rating

```DAX
Avg Consumer Rating =
AVERAGE(honda_car[Consumer_Rating])
```

**Business purpose:** Measures overall customer perception of the vehicle portfolio.

---

### Average Reliability Rating

```DAX
Avg Reliability Rating =
AVERAGE(honda_car[Reliability_Rating])
```

**Business purpose:** Measures perceived reliability across the portfolio.

---

### Average Value Rating

```DAX
Avg Value Rating =
AVERAGE(honda_car[Value_for_Money_Rating])
```

**Business purpose:** Measures perceived value for money.

---

### Average Performance

```DAX
Avg Performance =
AVERAGE(honda_car[Performance_Rating])
```

**Business purpose:** Supports the vehicle-performance and customer-perception analysis.

---

## 3. Inventory & Portfolio Measures

### Total Inventory Value

```DAX
Total Inventory Value =
SUM(honda_car[Price])
```

**Business purpose:** Estimates the aggregate listed value represented by the vehicle inventory.

**Used for:** Inventory-value distribution, market positioning and portfolio analysis.

---

### Used Vehicle Share

```DAX
Used Vehicle % =
DIVIDE(
    CALCULATE(
        [Total Vehicles],
        honda_car[Condition] = "Used"
    ),
    [Total Vehicles],
    0
)
```

**Business purpose:** Measures the proportion of inventory classified as used.

---

### Hybrid Vehicle Share

```DAX
Hybrid Share % =
DIVIDE(
    CALCULATE(
        [Total Vehicles],
        honda_car[Fuel_Type] = "Hybrid"
    ),
    [Total Vehicles],
    0
)
```

**Business purpose:** Measures the portfolio share represented by hybrid vehicles.

---

## 4. Portfolio-Level Rating Measures

The report also uses portfolio-oriented measures for comparative analysis and selected-rating visuals.

### Portfolio Average Consumer Rating

```DAX
Portfolio Avg Consumer Rating =
AVERAGE(honda_car[Consumer_Rating])
```

### Portfolio Average Value Rating

```DAX
Portfolio Avg Value Rating =
AVERAGE(honda_car[Value_for_Money_Rating])
```

### Portfolio Average Vehicle Price

```DAX
Portfolio Avg Vehicle Price =
AVERAGE(honda_car[Price])
```

These measures provide portfolio-level reference points against which vehicle, model, lifecycle or other segments can be compared.

---

## 5. Review Metrics

### Median Reviews

Review volume is used as an analytical signal for model popularity and customer engagement.

```DAX
Median Reviews =
MEDIAN(honda_car[Review_Count])
```

**Business purpose:** Provides a robust central reference point for review-volume analysis.

---

### Portfolio Median Consumer Review

```DAX
Portfolio Median Consumer Review =
MEDIAN(honda_car[Consumer_Review])
```

**Business purpose:** Provides a portfolio-level median for the consumer-review field where used in the report.

---

## 6. Vehicle Age Segmentation

Vehicle age was converted into business-oriented lifecycle groups before the main portfolio analysis.

The report uses the following definitions:

| Vehicle Age | Segment |
|---:|---|
| 0–2 years | New Model |
| 3–5 years | Recent Model |
| 6+ years | Mature Model |

### Vehicle Age Category

Conceptually, the calculated column follows this business rule:

```DAX
Vehicle Age Category =
SWITCH(
    TRUE(),
    [Vehicle Age] <= 2, "New Model",
    [Vehicle Age] <= 5, "Recent Model",
    "Mature Model"
)
```

**Business purpose:** Converts raw vehicle age into interpretable lifecycle groups.

**Used for:**

- Vehicle ageing analysis
- Depreciation analysis
- Customer-perception comparison
- Inventory positioning
- Mature-vehicle risk analysis
- Executive recommendations

> **Implementation note:** The business thresholds above are the documented segmentation definitions for this project. If the PBIX uses a different technical expression to derive the underlying age value, the technical expression should be retained in Power BI; the business segmentation remains 0–2 / 3–5 / 6+.

---

## 7. Review Volume Segmentation

Review volume was also converted into business-oriented model popularity groups.

| Review Count | Segment |
|---:|---|
| <150 | Niche Model |
| 150–749 | Emerging Favorite |
| 750–1,999 | Popular Model |
| ≥2,000 | Consumer Favorite |

### Review Volume Category

```DAX
Review Volume Category =
SWITCH(
    TRUE(),
    honda_car[Review_Count] < 150, "Niche Model",
    honda_car[Review_Count] < 750, "Emerging Favorite",
    honda_car[Review_Count] < 2000, "Popular Model",
    "Consumer Favorite"
)
```

**Business purpose:** Converts raw review counts into interpretable customer-engagement/popularity segments.

**Used for:**

- Model positioning
- Customer advocacy analysis
- Review-volume comparisons
- Portfolio strategy
- Model-performance prioritization

---

## 8. Other Supporting Calculated Fields

The report also contains supporting fields used for analytical presentation, including:

- `MPG Status`
- `State Full Name`
- `Vehicle Age Category`
- `Review Volume Category`

These fields should be treated differently from the two principal analytical segmentation frameworks.

### Principal analytical segments

1. **Vehicle Age Category**
2. **Review Volume Category**

These are the project's main business segmentation systems.

### Supporting fields

`MPG Status` and `State Full Name` support data interpretation and presentation rather than representing the core portfolio segmentation framework.

---

## 9. Dynamic Measures vs Calculated Columns

A key Power BI design principle demonstrated in this project is the distinction between calculated columns and measures.

### Calculated columns

Calculated columns create a value at the **row level** and are appropriate when a business classification needs to exist as a reusable field.

Examples:

- Vehicle Age Category
- Review Volume Category
- Supporting classification fields

They can then be used as:

- Axis/category fields
- Slicers
- Filters
- Segmentation dimensions

### Measures

Measures are calculated dynamically according to the current filter and visual context.

Examples:

- Total Vehicles
- Distinct Models
- Average Vehicle Price
- Average Ratings
- Total Inventory Value
- Used Vehicle %
- Hybrid Share %

This allows the same measure to respond dynamically to:

- Vehicle age
- Condition
- Fuel type
- Model
- State
- Other report filters

---

## 10. Why DAX Was Important in This Project

The DAX layer was not used simply to reproduce numbers already present in the source data.

It was used to convert the prepared dataset into reusable business metrics and analytical dimensions.

The progression was:

```text
Raw Vehicle Attributes
        ↓
Power Query Preparation
        ↓
Business Segmentation
        ↓
Reusable DAX Measures
        ↓
Cross-dimensional Analysis
        ↓
Portfolio Insights
        ↓
Strategic Recommendations
```

This is important because the dashboard's recommendations depend on combining multiple signals rather than looking at individual columns in isolation.

For example:

**Vehicle age + price + customer perception + review volume + inventory value**

can be interpreted together to identify portfolio positioning and ageing risks.

---

## 11. Calculation Design Principles

The project follows several practical DAX principles:

### Reuse measures

Where possible, higher-level calculations reference existing measures rather than repeating the same aggregation.

For example:

```DAX
Used Vehicle % =
DIVIDE(
    CALCULATE(
        [Total Vehicles],
        honda_car[Condition] = "Used"
    ),
    [Total Vehicles],
    0
)
```

This makes the calculation easier to maintain and allows it to respond naturally to report filters.

### Use DIVIDE for ratios

`DIVIDE()` is preferred over direct division when a denominator could potentially be zero.

### Separate business classification from KPI calculation

Segmentation logic belongs in calculated columns when the classification needs to behave as a dimension, while KPI calculations remain measures.

### Keep business thresholds explicit

The Vehicle Age and Review Volume thresholds are documented explicitly so that a stakeholder can understand the definition without inspecting the DAX itself.

---

## 12. Calculation Inventory

| Type | Calculation | Primary purpose |
|---|---|---|
| Measure | Total Vehicles | Inventory volume |
| Measure | Distinct Models | Portfolio breadth |
| Measure | Avg Vehicle Price | Pricing |
| Measure | Avg New Vehicle Price | New pricing |
| Measure | Avg Used Vehicle Price | Used pricing |
| Measure | Total Inventory Value | Inventory economics |
| Measure | Used Vehicle % | Portfolio mix |
| Measure | Hybrid Share % | Fuel/technology mix |
| Measure | Avg Consumer Rating | Customer perception |
| Measure | Avg Reliability Rating | Reliability perception |
| Measure | Avg Value Rating | Value perception |
| Measure | Avg Performance | Performance perception |
| Measure | Median Reviews | Review-volume reference |
| Calculated Column | Vehicle Age Category | Vehicle lifecycle |
| Calculated Column | Review Volume Category | Model popularity |
| Supporting Column | MPG Status | Data/analysis support |
| Supporting Column | State Full Name | Geographic presentation |

---

## Important Publication Note

The formulas in this document are intended to document the calculation logic behind the report. The **business definitions and thresholds are taken from the completed Honda project**.

Before treating this file as a literal source-code export of the PBIX, the final DAX syntax should be cross-checked against the formulas displayed in Power BI Desktop's Data/Model view. This is especially important for supporting fields and any measure whose implementation may have been written differently while producing the same business result.

The purpose of this document is therefore twofold:

1. Make the analytical calculation layer understandable to recruiters and reviewers.
2. Preserve the business logic behind the dashboard rather than presenting the dashboard as a black box.
