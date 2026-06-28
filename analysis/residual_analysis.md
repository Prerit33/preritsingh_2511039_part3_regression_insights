# Residual Analysis: Uncovering Store Performance Anomalies

## Methodology
In regression analysis, a **residual** is the difference between the **Actual Sales** a store achieved and the **Predicted Sales** the model expected it to achieve based on its inputs (footfall, inventory, location, etc.). 
* **Formula:** `Residual = Actual Sales - Predicted Sales`

---

##  Top 5 Positive Residuals (The Overachievers)
These stores generated significantly *more* revenue than the model predicted. 

| Store ID | Region | Store Type | Actual Sales | Predicted Sales | Residual (Difference) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| STR-1073 | East | Residential | $813,316.71 | $697,606.08 | $115,710.63 |
| STR-1028 | East | Mall | $713,611.16 | $603,455.90 | $110,155.26 |
| STR-1026 | East | Mall | $625,514.04 | $524,454.50 | $101,059.54 |
| STR-1050 | North | Residential | $735,786.64 | $639,364.47 | $96,422.17 |
| STR-1030 | West | Residential | $820,519.04 | $724,483.26 | $96,035.78 |

**Business Interpretation:** These stores are highly efficient at converting traffic into revenue. Since our model already accounts for footfall, inventory, and location, these positive anomalies suggest other unmeasured factors are at play. This could include exceptional store management, highly effective localized promotions, superior customer service driving large basket sizes, or a lack of local competitor discounting. 
* *Action:* Leadership should interview the managers of these stores to uncover their best practices and attempt to replicate them across the network.

---

##  Top 5 Negative Residuals (The Underachievers)
These stores generated significantly *less* revenue than the model expected based on their healthy traffic and inventory levels.

| Store ID | Region | Store Type | Actual Sales | Predicted Sales | Residual (Difference) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| STR-1017 | West | High Street | $685,379.08 | $851,738.64 | $-166,359.56 |
| STR-1023 | South | Mall | $627,171.90 | $760,561.84 | $-133,389.94 |
| STR-1012 | West | Residential | $595,467.60 | $722,105.37 | $-126,637.77 |
| STR-1007 | West | Mall | $800,451.94 | $912,993.82 | $-112,541.88 |
| STR-1009 | North | Residential | $641,865.03 | $741,946.01 | $-100,080.98 |

**Business Interpretation:** Despite having good fundamental conditions (like solid foot traffic and available inventory), these stores are failing to close sales. This indicates a severe operational or structural issue. It could be due to a poor internal store layout, aggressive pricing from a competitor directly across the street, high staff turnover, or product mix issues (having inventory, but not the *right* inventory).
* *Action:* These stores require immediate auditing. Regional managers should investigate why traffic is entering the store but leaving without purchasing.

---

## Model Bias & Predictions
* **Over-Predicting vs. Under-Predicting:** By reviewing the extremes, we can check for systematic bias. For example, if all of our top negative residuals are "High Street" stores, the model might be fundamentally overestimating the conversion rate of foot traffic in High Street locations (where people might just be browsing while walking past, compared to a Mall where they intend to shop). 
* The residuals highlight that while our model explains ~83% of the variance, the remaining 17% is driven by hyper-local, human, and operational factors that a spreadsheet cannot easily capture.
