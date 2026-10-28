# Analytical Approach — Honda Vehicle Performance, Pricing & Inventory Insights

## Purpose

This document describes the analytical workflow used to move from the raw Honda vehicle dataset to the Power BI dashboard and strategic recommendations.

## Analytical Workflow

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

## 1. Data Preparation

The raw dataset was prepared in Power Query. The transformation process included:

- Promoting source headers
- Cleaning the `Price` field
- Removing currency symbols and thousands separators
- Converting `Not Priced` entries to `0`
- Applying appropriate data types
- Renaming `Consumer_Review_#` to `Consumer_Review`
- Removing unnecessary fields
- Standardizing inconsistent `State` values
- Applying the existing row-filter steps in the query

Removed fields included `VIN`, `Stock_#`, `Exterior_Color`, and `Interior_Color`.

Blank or inconsistent `State` values, including `Glens`, `Route`, and `MO-22`, were standardized to `unknown`.

## 2. Column-Level Exploration

After preparation, the fields were explored individually to understand:

- Data types
- Distributions
- Missing values
- Categorical variation
- Numerical ranges
- Potential analytical dimensions

This exploration informed the selection of meaningful segmentation variables.

## 3. Segmentation Before Analysis

Segmentation was established before the main business analysis. Thresholds were selected using distribution analysis, histogram evaluation, percentile assessment and business interpretability.

The two principal analytical segmentation frameworks were:

### Vehicle Age

- New Model — 0–2 years
- Recent Model — 3–5 years
- Mature Model — 6+ years

### Review Volume

- Niche Model — <150 reviews
- Emerging Favorite — 150–749 reviews
- Popular Model — 750–1,999 reviews
- Consumer Favorite — ≥2,000 reviews

These segments were then used to compare vehicle performance, customer perception, pricing, depreciation and inventory positioning.

## 4. Business Analysis

The analysis connects five areas:

1. Vehicle performance and customer perception
2. Pricing and value positioning
3. Vehicle lifecycle and depreciation
4. Inventory composition and value
5. Portfolio-level opportunities

## 5. Insight Development

The project was designed to move from descriptive measures toward decision-oriented interpretation. Vehicle age and review volume are treated as analytical dimensions that can be considered alongside ratings, pricing and inventory rather than as isolated classifications.

## 6. Recommendations

The analysis ends with ten strategic recommendations covering portfolio roles, Honda Certified, mature-vehicle risk, used-vehicle variety, hybrid positioning, MPG transparency, customer advocacy and a multi-signal decision framework.

## 7. Dashboard Presentation

The README showcases the two core analytical pages:

- Vehicle Performance & Customer Perception
- Vehicle Pricing & Inventory Insights

The other report pages function as supporting extensions, including the Executive Action Plan and Segmentation Framework.
