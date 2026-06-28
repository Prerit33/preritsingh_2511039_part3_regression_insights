# Model Comparison: Retail Sales Drivers

## 1. Simple Linear Regression (Marketing Focus)
* **Model Name:** Simple Regression (Marketing vs. Sales)
* **Variables Used:** * *Dependent:* `monthly_sales`
    * *Independent:* `marketing_spend`
* **R-squared:** 16.7%
    * *Interpretation:* Marketing spend alone only explains about 16.7% of the variation in store sales.
* **Significant Variables:** * `marketing_spend` (p < 0.05)
* **Business Usefulness:** * Useful for proving that marketing has a positive ROI (every $1 spent yields ~$2.13 in sales). However, it is too simplistic for strategic planning or accurate forecasting.
* **Limitations:** * **Omitted Variable Bias:** This model completely ignores massive drivers of sales like foot traffic, store location, and inventory levels. Because it lacks these factors, it oversimplifies the reality of retail performance.

## 2. Simple Linear Regression (Footfall Focus)
* **Model Name:** Simple Regression (Footfall vs. Sales)
* **Variables Used:** * *Dependent:* `monthly_sales`
    * *Independent:* `footfall`
* **R-squared:** 73.6%
    * *Interpretation:* Customer traffic is a massive driver, explaining nearly 74% of all sales variation.
* **Significant Variables:** * `footfall` (p < 0.05)
* **Business Usefulness:** * Highly useful for understanding baseline potential. It tells leadership that driving physical traffic must be priority #1.
* **Limitations:** * Doesn't explain *how* to get footfall or what operational levers (like inventory or staffing) are required to convert that footfall into actual revenue.

## 3. Multiple Linear Regression (Comprehensive Model)
* **Model Name:** Multiple Regression (Operational & Geographic Drivers)
* **Variables Used:** * *Dependent:* `monthly_sales`
    * *Independent (Numerical):* `marketing_spend`, `footfall`, `inventory_availability_pct`
    * *Independent (Dummy):* `region_North`, `region_South`, `region_West`, `store_type_High Street`, `store_type_Mall`, `store_type_Residential`
* **R-squared:** 82.7%
    * *Interpretation:* By combining these factors, the model explains nearly 83% of the variance in sales. This is a highly robust model.
* **Significant Variables (Useful p-values < 0.05):** * `footfall`, `inventory_availability_pct`, `marketing_spend`, `region_South`, `region_West`, `store_type_High Street`, `store_type_Residential`
* **Business Usefulness:** * Extremely actionable. Leadership can use this to strategically allocate resources (e.g., ensuring high inventory in South/West stores) and identify structural issues (e.g., investigating why High Street and Residential formats underperform compared to Airports/Malls).
* **Limitations:** * **Uncaptured Factors:** The model does not capture macroeconomic conditions, localized competitor pricing, or seasonal/holiday interactions. It also assumes a linear relationship, meaning it doesn't account for diminishing returns (e.g., eventually, adding more inventory won't keep boosting sales at the same rate).
