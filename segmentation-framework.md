# Segmentation Framework

## Purpose

Segmentation was used to convert continuous or high-cardinality variables into interpretable business categories before the main analysis.

The objective was not to create segmentation for its own sake. The categories were designed to support portfolio comparison, pricing analysis, inventory analysis and customer-perception analysis.

## Methodology

The dashboard states that segmentation thresholds were established using:

- Distribution analysis
- Histogram evaluation
- Percentile assessment
- Business interpretability
- Balanced representation across the vehicle portfolio

## 1. Review Volume Category

**Purpose:** Classifies vehicle models based on customer review volume to measure market visibility, customer engagement and overall popularity.

| Category | Reviews | Business Interpretation |
|---|---:|---|
| Niche Model | <150 | Limited review visibility / lower observed engagement |
| Emerging Favorite | 150–749 | Developing customer visibility |
| Popular Model | 750–1,999 | Established customer engagement |
| Consumer Favorite | ≥2,000 | Highest observed review popularity |

### Analytical application

Review-volume categories were used to analyze inventory value concentration and market-popularity dynamics.

## 2. Vehicle Age Category

**Purpose:** Groups vehicles according to age relative to the marketplace to evaluate pricing behavior, customer perception and lifecycle maturity.

| Category | Vehicle Age |
|---|---:|
| New Model | 0–2 years |
| Recent Model | 3–5 years |
| Mature Model | 6+ years |

### Analytical application

Vehicle-age categories were used to evaluate price depreciation patterns and customer perception across vehicle lifecycle stages.

## Important Workflow Note

The segmentation framework was created **before the main dashboard analysis** after exploratory examination of the data.

Its placement as the final Power BI page is a documentation choice: it allows stakeholders to reference definitions without interrupting the analytical pages.
