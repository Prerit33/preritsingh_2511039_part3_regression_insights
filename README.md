# Retail Sales Driver Analysis

## Overview

This project aims to identify the primary drivers of monthly sales performance across the retail network using regression analysis. By understanding the impact of various business factors (e.g., marketing spend, discounting, staffing, and inventory), leadership can strategically reallocate resources to maximize revenue.

Below is the initial exploratory variable assessment based on the `store_performance.csv` and `data_dictionary.csv` files.

---

## Variable Assessment

### Dependent Variable (The Target)

* **`monthly_sales`**: This is the continuous metric we are trying to predict and understand. All business actions evaluated will be measured against their impact on this number.

### Potential Independent Variables (The Predictors)

These are the operational, geographic, and environmental factors we will test to see how strongly they influence our dependent variable:

* `marketing_spend`
* `footfall`
* `avg_discount_pct`
* `staff_count`
* `inventory_availability_pct`
* `competitor_distance_km`
* `customer_rating`
* `holiday_flag`
* `region`
* `store_type`
* `month` (as a derived seasonal feature)

### Numerical Variables

These represent measurable quantities.

* **Continuous:** `marketing_spend`, `avg_discount_pct`, `inventory_availability_pct`, `competitor_distance_km`, `customer_rating`
* **Discrete:** `footfall`, `staff_count`

### Categorical Variables

These represent qualitative groups or boolean flags.

* **Nominal:** `region` (e.g., East, South)
* **Nominal:** `store_type` (Mall, High Street, Residential, Airport)
* **Binary/Boolean:** `holiday_flag` (1 or 0)

---

## Data Preprocessing Recommendations

### Variables Requiring Cleaning or Transformation

To ensure the regression model is accurate and unbiased, the following transformations are required before modeling:

1. **Categorical Encoding:** `region` and `store_type` must be converted into numerical formats using one-hot encoding, so the regression algorithm can interpret them.
2. **Date Extraction (`month`):** The `month` column (e.g., "2025-01-01") should be transformed into a seasonal categorical feature (e.g., Q1, Q2, or Month-of-Year) to capture seasonal buying trends.
3. **Feature Scaling:** Because variables like `marketing_spend` are in the tens of thousands while `avg_discount_pct` is a small decimal, we should standardize or normalize our numerical variables. This ensures the model's coefficients are comparable, making it easier to tell leadership *which* factor has the strongest relative impact.

### Variables Not Useful for This Regression

These variables should be excluded from the feature set predicting `monthly_sales`:

1. **`store_id`:** This is purely a unique identifier. Including it in a standard linear regression would create hundreds of dummy variables that don't help us generalize business rules. *(Note: If we were building an advanced mixed-effects model or panel regression, we might use this to control for unobserved store-level effects, but it should be dropped for a standard driver analysis).*
2. **`monthly_profit`:** This is a downstream result of sales minus costs. Including it as an independent variable to predict sales would cause **target leakage**, artificially inflating the model's accuracy while failing to answer the business question of *what drives the revenue in the first place*. It can be analyzed separately but must be dropped from this specific model.
