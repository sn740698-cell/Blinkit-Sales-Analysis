# BlinkIT Grocery Sales Analysis - Objectives & Tasks Breakdown

**Student Project:** BlinkIT Grocery Sales Analysis  
**Domain:** Retail & Grocery Sales Analytics  
**Client / Company:** Sapphire IQ  
**Tools Used:** Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook  
**Author:** Data Analyst (Ram)

---

## Table of Contents
1. [Project Overview & Business Context](#project-overview--business-context)
2. [Objective 1: Understand the Business and Its Sales Performance](#objective-1-understand-the-business-and-its-sales-performance)
   - [Task 1.1: Product Types Sold](#task-11-product-types-sold)
   - [Task 1.2: Outlet Types, Sizes, and Locations](#task-12-outlet-types-sizes-and-locations)
   - [Task 1.3: Overall Sales Performance](#task-13-overall-sales-performance)
   - [Task 1.4: Overall Customer Rating & Product Performance](#task-14-overall-customer-rating--product-performance)
3. [Objective 2: Make Sure the Available Information Is Reliable (Data Cleaning)](#objective-2-make-sure-the-available-information-is-reliable-data-cleaning)
   - [Task 2.1: Missing Value Identification & Imputation](#task-21-missing-value-identification--imputation)
   - [Task 2.2: Duplicate Records Audit](#task-22-duplicate-records-audit)
   - [Task 2.3: Anomaly & Outlier Screening](#task-23-anomaly--outlier-screening)
   - [Task 2.4: Standardization & Harmonization](#task-24-standardization--harmonization)
4. [Objective 3: Find Out What Is Driving Better Sales Performance](#objective-3-find-out-what-is-driving-better-sales-performance)
   - [Task 3.1: High-Selling Product Categories](#task-31-high-selling-product-categories)
   - [Task 3.2: High-Performing Outlets & Formats](#task-32-high-performing-outlets--formats)
   - [Task 3.3: Relationship & Correlation Analysis](#task-33-relationship--correlation-analysis)
   - [Task 3.4: Cohort Comparison (Top 10% vs Bottom 10%)](#task-34-cohort-comparison-top-10-vs-bottom-10)
5. [Objective 4: Help Management Make Better Business Decisions](#objective-4-help-management-make-better-business-decisions)
   - [Task 4.1: Product Revenue Contributions & Pareto Curve](#task-41-product-revenue-contributions--pareto-curve)
   - [Task 4.2: Top Outlets & Strategic Locations](#task-42-top-outlets--strategic-locations)
   - [Task 4.3: Underperforming Areas & Improvement Scope](#task-43-underperforming-areas--improvement-scope)
   - [Task 4.4: Strategic Recommendations for Leadership](#task-44-strategic-recommendations-for-leadership)

---

## Project Overview & Business Context
BlinkIT offers an extensive portfolio of grocery and FMCG products through multiple outlet formats across Tier 1, Tier 2, and Tier 3 cities. Sapphire IQ's management team requires a comprehensive exploratory data analysis to evaluate product sales, store formats, inventory parameters, and customer ratings.

The dataset contains **8,523 transaction records** across **12 feature attributes**, covering:
- **Product Attributes:** `Item Identifier`, `Item Type`, `Item Fat Content`, `Item Visibility`, `Item Weight`
- **Outlet Attributes:** `Outlet Identifier`, `Outlet Establishment Year`, `Outlet Type`, `Outlet Size`, `Outlet Location Type`
- **Performance Metrics:** `Sales` ($), `Rating` (1.0 to 5.0)

---

## Objective 1: Understand the Business and Its Sales Performance

### Task 1.1: Product Types Sold
BlinkIT carries **16 distinct grocery categories**. The product count and catalog share breakdown:

| Product Category | Item Count | Catalog Share (%) | Cumulative Share (%) |
| :--- | :---: | :---: | :---: |
| **Fruits and Vegetables** | 1,232 | 14.45% | 14.45% |
| **Snack Foods** | 1,200 | 14.08% | 28.53% |
| **Household** | 910 | 10.68% | 39.21% |
| **Frozen Foods** | 856 | 10.04% | 49.25% |
| **Dairy** | 682 | 8.00% | 57.25% |
| **Canned** | 649 | 7.61% | 64.86% |
| **Baking Goods** | 648 | 7.60% | 72.46% |
| **Health and Hygiene** | 520 | 6.10% | 78.56% |
| **Soft Drinks** | 445 | 5.22% | 83.78% |
| **Meat** | 425 | 4.99% | 88.77% |
| **Breads** | 251 | 2.94% | 91.71% |
| **Hard Drinks** | 214 | 2.51% | 94.22% |
| **Others** | 169 | 1.98% | 96.20% |
| **Starchy Foods** | 148 | 1.74% | 97.94% |
| **Breakfast** | 110 | 1.29% | 99.23% |
| **Seafood** | 64 | 0.75% | 100.00% |

**Key Finding:** Fruits & Vegetables, Snack Foods, and Household goods represent **39.21%** of all catalog items. Specialized categories such as Seafood and Breakfast constitute less than 2% combined.

---

### Task 1.2: Outlet Types, Sizes, and Locations
BlinkIT operates **10 unique outlets** established between **2011 and 2022**.

#### A. Outlet Formats
- **Supermarket Type1:** 5,577 records (65.43%) across 6 stores (OUT013, OUT017, OUT035, OUT045, OUT046, OUT049)
- **Grocery Store:** 1,083 records (12.71%) across 2 small-footprint locations (OUT010, OUT019)
- **Supermarket Type3:** 935 records (10.97%) across 1 flagship store (OUT027)
- **Supermarket Type2:** 928 records (10.89%) across 1 medium store (OUT018)

#### B. Location Tiers
- **Tier 3 (Metro / Large Urban):** 3,350 records (39.31%)
- **Tier 2 (Emerging Urban):** 2,785 records (32.68%)
- **Tier 1 (Core Capital / Traditional):** 2,388 records (28.02%)

#### C. Store Sizes
- **Medium:** 3,631 records (42.60%)
- **Small:** 3,139 records (36.83%)
- **High:** 1,753 records (20.57%)

---

### Task 1.3: Overall Sales Performance
Key statistical aggregates across all 8,523 transactions:

| Metric | Value |
| :--- | :--- |
| **Total Gross Sales Revenue** | **$1,201,681.49** |
| **Mean Sales per SKU** | **$140.99** |
| **Median Sales per SKU** | **$143.01** |
| **Standard Deviation** | **$62.28** |
| **Minimum Sales Recorded** | **$31.29** |
| **Maximum Sales Recorded** | **$266.89** |
| **25th Percentile (Q1)** | **$93.83** |
| **75th Percentile (Q3)** | **$185.64** |
| **Interquartile Range (IQR)** | **$91.81** |

---

### Task 1.4: Overall Customer Rating & Product Performance
- **Mean Customer Rating:** **3.97 out of 5.00** (Standard Deviation: 0.61)
- **Median Customer Rating:** **4.00 out of 5.00**
- **Rating Range:** 1.00 to 5.00
- **Rating Buckets:**
  - 4.6 - 5.0 Stars: 3,420 items (40.13%)
  - 4.1 - 4.5 Stars: 2,710 items (31.80%)
  - 3.1 - 4.0 Stars: 2,120 items (24.87%)
  - 2.1 - 3.0 Stars: 213 items (2.50%)
  - 1.0 - 2.0 Stars: 60 items (0.70%)

---

## Objective 2: Make Sure the Available Information Is Reliable (Data Cleaning)

### Task 2.1: Missing Value Identification & Imputation
- Initial audit identified **1,463 missing values** exclusively in the `Item Weight` column (17.17% of total records).
- Root-cause diagnosis: 100% of records in **OUT027** (935 rows) and **OUT019** (528 rows) had omitted weight measurements.
- **2-Stage Imputation Algorithm:**
  1. *Stage 1 (Product Match):* Imputed item weight using the average recorded weight of the exact same `Item Identifier` across all reporting stores. This resolved **1,459 out of 1,463 missing values** (99.73%).
  2. *Stage 2 (Category Match):* The remaining 4 items were imputed using the mean weight of their respective `Item Type`.
  3. *Result:* `Item Weight` now has **0 missing values** (100% completeness).

### Task 2.2: Duplicate Records Audit
- Audit for identical rows: `clean_df.duplicated().sum()` = **0**.
- Audit for duplicated (`Item Identifier`, `Outlet Identifier`) tuples: **0**.
- Conclusion: Every observation represents a unique product-store instance.

### Task 2.3: Anomaly & Outlier Screening
- **Zero Visibility Anomaly:** Exactly **526 items (6.17%)** had an `Item Visibility` of `0.0000`. Products physically stocked or displayed in a quick-commerce mobile app cannot have zero visibility.
- **Treatment:** Zero visibility values were replaced with the median non-zero visibility of that specific product across other stores; residual values were imputed with the category median.
- **IQR Outlier Bounds:**
  - `Sales`: [$0.00, $323.36] -> 0 extreme outliers.
  - `Item Visibility`: Upper Bound = 0.196 -> 144 items with high promotional visibility.
  - `Rating`: Lower Bound = 3.70 -> 273 lower-rated items identified for quality review.

### Task 2.4: Standardization & Harmonization
- **Inconsistent Fat Content Labels:**
  - `LF` (316 rows), `low fat` (112 rows), `Low Fat` (5,089 rows) -> Standardized to **`Low Fat`** (5,517 total, 64.73%).
  - `reg` (117 rows), `Regular` (2,889 rows) -> Standardized to **`Regular`** (3,006 total, 35.27%).
- **Feature Engineering:**
  - `Product Category`: Derived from `Item Identifier` prefix (`FD` = Food [6,125], `DR` = Drink [799], `NC` = Non-Consumable [1,599]).
  - `Item Fat Content Corrected`: Reclassified Non-Consumables (Household, Hygiene, Others) to **`Non-Edible`** (1,599 items).
  - `Outlet Age`: Calculated as `2022 - Outlet Establishment Year`.
- Cleaned dataset exported to:
  - `data/processed/BlinkIT_Grocery_Data_Cleaned.csv`
  - `data/processed/BlinkIT_Grocery_Data_Cleaned.xlsx`

---

## Objective 3: Find Out What Is Driving Better Sales Performance

### Task 3.1: High-Selling Product Categories
Ranked by total gross sales:

| Item Type | Total Sales ($) | Avg Sales ($) | Item Count | Revenue Share (%) |
| :--- | :---: | :---: | :---: | :---: |
| **Fruits and Vegetables** | $178,124.08 | $144.58 | 1,232 | 14.82% |
| **Snack Foods** | $172,663.85 | $143.89 | 1,200 | 14.37% |
| **Household** | $135,976.52 | $149.42 | 910 | 11.32% |
| **Frozen Foods** | $118,558.88 | $138.50 | 856 | 9.87% |
| **Dairy** | $101,276.45 | $148.50 | 682 | 8.43% |
| **Canned** | $90,706.73 | $139.76 | 649 | 7.55% |
| **Baking Goods** | $82,897.84 | $127.93 | 648 | 6.90% |
| **Health and Hygiene** | $68,367.65 | $131.48 | 520 | 5.69% |
| **Meat** | $59,046.22 | $138.93 | 425 | 4.91% |
| **Soft Drinks** | $58,358.55 | $131.14 | 445 | 4.86% |
| **Breads** | $35,716.66 | $142.30 | 251 | 2.97% |
| **Hard Drinks** | $29,668.78 | $138.64 | 214 | 2.47% |
| **Others** | $22,451.89 | $132.85 | 169 | 1.87% |
| **Starchy Foods** | $21,880.03 | $147.84 | 148 | 1.82% |
| **Breakfast** | $15,596.70 | $141.79 | 110 | 1.30% |
| **Seafood** | $9,077.87 | $141.84 | 64 | 0.76% |

**Broad Category Performance:**
- **Food:** $878,251.27 (73.08% share)
- **Non-Consumable:** $226,796.06 (18.87% share)
- **Drink:** $96,634.16 (8.04% share)

**Fat Content Breakdown:**
- **Low Fat:** $776,320.17 (64.60% share)
- **Regular:** $425,361.32 (35.40% share)

---

### Task 3.2: High-Performing Outlets & Formats
Ranked by total sales:

| Outlet Identifier | Outlet Type | Location Tier | Size | Est. Year | Total Sales ($) | Avg Sales ($) | Records |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **OUT027** | Supermarket Type3 | Tier 3 | Medium | 2018 | **$130,714.67** | $139.80 | 935 |
| **OUT013** | Supermarket Type1 | Tier 3 | High | 2014 | **$131,809.02** | $141.43 | 932 |
| **OUT035** | Supermarket Type1 | Tier 2 | Small | 2017 | **$131,477.78** | $141.37 | 930 |
| **OUT046** | Supermarket Type1 | Tier 1 | Small | 2016 | **$131,281.99** | $141.16 | 930 |
| **OUT049** | Supermarket Type1 | Tier 1 | Medium | 2012 | **$131,308.24** | $141.19 | 930 |
| **OUT045** | Supermarket Type1 | Tier 2 | Medium | 2015 | **$131,148.01** | $141.17 | 929 |
| **OUT018** | Supermarket Type2 | Tier 3 | Medium | 2022 | **$131,477.78** | $141.68 | 928 |
| **OUT017** | Supermarket Type1 | Tier 2 | Small | 2020 | **$130,524.86** | $140.96 | 926 |
| **OUT010** | Grocery Store | Tier 3 | Medium | 2011 | **$78,131.57** | $140.78 | 555 |
| **OUT019** | Grocery Store | Tier 1 | Small | 2018 | **$73,807.58** | $139.79 | 528 |

**Format Breakdown:**
- **Supermarket Type1:** $787,549.90 (65.54% share) across 6 stores
- **Grocery Store:** $151,939.15 (12.64% share) across 2 stores
- **Supermarket Type2:** $131,477.78 (10.94% share) across 1 store
- **Supermarket Type3:** $130,714.67 (10.88% share) across 1 store

---

### Task 3.3: Relationship & Correlation Analysis
- **Sales vs Item Visibility:** `r = -0.013` (Very weak negative correlation). High promotional visibility does not guarantee higher item price/sales; low-ticket everyday essentials often have high display allocation.
- **Sales vs Item Weight:** `r = 0.012` (Negligible linear relationship). Product weight is not a primary pricing or sales driver.
- **Sales vs Customer Rating:** `r = -0.021` (Independent). Customer ratings reflect product satisfaction rather than transactional price volume.
- **Sales vs Outlet Age:** `r = -0.005` (Mature stores and newly opened dark stores perform consistently, demonstrating strong brand recognition).

---

### Task 3.4: Cohort Comparison (Top 10% vs Bottom 10%)
Comparing the top 853 sales records (Sales >= $229.47) with the bottom 853 records (Sales <= $55.16):

| Attribute | Top 10% High-Performers | Bottom 10% Low-Performers | Difference / Ratio |
| :--- | :---: | :---: | :---: |
| **Average Sales ($)** | **$248.61** | **$43.32** | **5.74x Higher** |
| **Average Rating** | 3.96 | 3.95 | +0.01 |
| **Average Visibility** | 0.063 | 0.071 | -11.3% (Higher efficiency) |
| **Average Weight (kg)** | 12.87 kg | 12.79 kg | +0.08 kg |
| **Top Category** | Dairy & Household | Baking & Snacks | Premium essentials lead |

---

## Objective 4: Help Management Make Better Business Decisions

### Task 4.1: Product Revenue Contributions & Pareto Curve
- Total catalog items: **1,559 unique SKUs**.
- **Top 20% of SKUs (311 items) generate 36.57% of total revenue.**
- Top revenue-generating individual SKUs:
  1. `FDU12` (Baking Goods): $2,371.01
  2. `FDT07` (Fruits and Vegetables): $2,306.90
  3. `NCQ06` (Household): $2,294.71
  4. `FDL58` (Snack Foods): $2,111.65
  5. `NCB31` (Household): $2,104.73

### Task 4.2: Top Outlets & Strategic Locations
- **Tier 3 cities** are BlinkIT's largest revenue contributors (**$472,133.04, 39.29%**), followed by **Tier 2 ($393,150.65, 32.72%)** and **Tier 1 ($262,590.23, 21.85%)**.
- Supermarket formats consistently achieve ~930 items stocked per location compared to ~540 items in Grocery Store formats.

### Task 4.3: Underperforming Areas & Improvement Scope
1. **Grocery Store Throughput:** OUT010 and OUT019 underperform in total revenue ($78K and $73K) because their product assortment is only 58% of supermarket depth.
2. **Niche Category Under-Penetration:** Seafood ($9K) and Breakfast ($15K) contribute less than 2.1% combined, suffering from limited SKU breadth.
3. **Zero-Visibility Catalog Drag:** 526 zero-visibility SKUs previously suffered from reduced digital discoverability.

### Task 4.4: Strategic Recommendations for Leadership
1. **Supermarket Format Replication:** Rapidly deploy the Supermarket Type3 / Type1 micro-warehouse format in emerging Tier 2 and Tier 3 residential corridors.
2. **Catalog Indexing & Visibility Enforcement:** Implement real-time catalog auditing to eliminate 0.0 visibility SKUs and reward fast-turnover items with prime banner placement.
3. **Cross-Category Basket Expansion:** Create curated digital combo packs (e.g., Snacks + Cold Beverages; Breakfast Cereal + Fresh Milk) to increase average order value (AOV).
4. **Supply Chain Temperature Control:** With Fresh Produce, Dairy, and Frozen Foods generating **$397,959.41 (33.12% of revenue)**, cold-chain dark-store units are essential to minimize spoilage and cancellations.
5. **Quality Interventions for Low-Rating SKUs:** Implement supplier reviews for products scoring under 3.5 stars to protect customer retention and lifetime value (LTV).
