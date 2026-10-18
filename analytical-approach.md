# Analytical Approach

## Project Context

This project examines Honda vehicle performance, customer perception, pricing, depreciation, and inventory positioning as one connected portfolio problem.

The central analytical question is:

> How should Honda evaluate vehicle performance, customer perception, pricing and inventory as one connected portfolio problem?

## Analytical Workflow

The analysis followed this sequence:

**Raw Data → Data Preparation → Exploration → Segmentation → Analysis → Insights → Recommendations → Dashboard**

The dashboard page order is a presentation structure, not the sequence in which the analysis was performed.

## 1. Data Understanding

The source dataset contains vehicle-level observations covering model characteristics, pricing, condition, customer reviews, ratings, drivetrain, fuel type, transmission, engine, mileage, state and seller type.

The working dataset contains 4,999 records and 25 source columns.

## 2. Data Preparation in Power Query

The Power Query workflow included:

- Promoting the first row to headers.
- Removing `$` from `Price`.
- Converting `Not Priced` in `Price` to `0`.
- Removing comma separators from `Price`.
- Applying explicit data types, including whole-number and decimal-number fields.
- Renaming `Consumer_Review_#` to `Consumer_Review`.
- Removing `VIN`, `Stock_#`, `Exterior_Color`, and `Interior_Color` from the analytical model.
- Standardizing blank and malformed `State` values to `unknown`, including values such as `Glens`, `Route`, and `MO-22`.
- Retaining the existing row-filter steps in the query without assigning an unsupported business rationale to them.

The purpose was to make pricing analyzable, establish usable field types, simplify the analytical schema, and clean inconsistent categorical values.

## 3. Exploration Before Segmentation

Before building the main analytical views, the columns were explored in Power BI to understand their distributions, usefulness and analytical potential.

This exploration identified dimensions that could benefit from business-oriented segmentation.

## 4. Segmentation Framework

Two primary analytical segmentation dimensions were established:

### Vehicle Age

| Segment | Definition |
|---|---:|
| New Model | 0–2 years |
| Recent Model | 3–5 years |
| Mature Model | 6+ years |

### Review Volume

| Segment | Definition |
|---|---:|
| Niche Model | <150 reviews |
| Emerging Favorite | 150–749 reviews |
| Popular Model | 750–1,999 reviews |
| Consumer Favorite | ≥2,000 reviews |

The dashboard documentation states that thresholds were established using distribution analysis, histogram evaluation, and percentile assessment while maintaining business interpretability and balanced portfolio representation.

## 5. Main Analysis

The analysis then connected the following dimensions:

- Vehicle performance
- Customer ratings and perception
- Review popularity
- Vehicle lifecycle / age
- Pricing and depreciation
- Vehicle condition
- Fuel type and drivetrain
- Inventory value
- Geographic market concentration
- Seller and ownership characteristics

Rather than treating these as isolated measures, the project uses them to understand portfolio positioning and inventory productivity.

## 6. Insight Development

The dashboard translates the analytical views into business signals around:

- Strong and weak vehicle positioning
- Customer-perception differences across the portfolio
- Price movement across vehicle age stages
- Inventory value concentration
- Premium vehicle opportunities
- Hybrid positioning
- Mature-vehicle risk
- Review popularity as a customer-advocacy signal
- Information gaps such as missing MPG data

## 7. Executive Recommendations

The final analytical step converts these signals into ten strategic recommendations covering portfolio structure, certified vehicles, ageing risk, used-vehicle curation, hybrid strategy, MPG transparency, customer advocacy and multi-signal decision-making.

## 8. Dashboard Presentation

The completed Power BI presentation is organized as:

1. Project Hub
2. Vehicle Performance & Customer Perception
3. Vehicle Pricing & Inventory Insights
4. Executive Action Plan
5. Segmentation Framework & Business Definitions

The segmentation page is intentionally placed at the end as a stakeholder reference page. Segmentation was performed earlier in the analytical workflow; the final page documents the definitions so dashboard users can interpret the analysis consistently.
