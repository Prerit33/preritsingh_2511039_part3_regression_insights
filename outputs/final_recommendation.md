## Executive Summary
---

## 1. Which factors appear most strongly associated with monthly sales?
The data unequivocally points to two operational pillars:
1.  **Footfall (Customer Traffic):** This is the strongest individual predictor. In our simple models, footfall alone accounted for 73.6% of all sales variation. In the comprehensive model, every additional store visitor is associated with an incremental increase of **$33.86** in monthly sales. 
2.  **Inventory Availability:** Keeping shelves stocked is critical to conversion. For every 1% increase in on-shelf inventory availability, expected monthly sales rise by nearly **$2,961**. 

Furthermore, location plays a strong role. Stores located in the **South** and **West** regions consistently outperform the East baseline by roughly **$18k to $20k** per month, all else being equal.

## 2. Which variables should leadership focus on?
* **Driving Local Traffic:** Since footfall is the dominant driver, leadership should prioritize localized events, strategic real-estate selection (high natural foot traffic areas), and promotions designed explicitly to get bodies in the door.
* **Supply Chain Resilience:** The high coefficient for inventory availability means supply chain bottlenecks directly translate to severe revenue losses. Ensure top-performing locations are never stocked out of core items.
* **Store Format Strategy:** "Residential" and "High Street" formats significantly underperform compared to Malls and Airports (generating up to $39k less per month). Leadership must evaluate if the overhead costs for these formats justify their diminished returns.

## 3. Which variables should not be over-interpreted?
* **Marketing Spend in Isolation:** While a simple model suggests a $1 investment yields $2.13 in sales, this variable is heavily biased if you don't account for traffic. In the multiple regression model, marketing's impact shrinks to **$1.19** per dollar spent. It helps, but it is not a silver bullet.
* **North Region Performance:** The model suggests North stores make slightly more than East stores, but the p-value (0.238) means this is **not statistically significant**. Do not treat the North region as inherently superior to the East.
* **Malls vs. Airports:** Similarly, the difference between Mall and Airport performance lacks statistical significance.

## 4. What business action would you recommend?
**Recommendation: Audit under-converting stores and reallocate marketing to supply chain optimization.**
1.  **Action 1:** Review the "Top Negative Residual" stores identified in our residual analysis. These locations have high footfall but low sales. Dispatch regional managers to audit their store layout, staff training, and product mix to fix their broken conversion funnels.
2.  **Action 2:** Halt expansion of Residential store formats until a profitable operating model can be established. 
3.  **Action 3:** Shift a portion of under-performing generalized marketing spend toward localized promotions that guarantee physical footfall, or reinvest it in supply chain logistics to ensure inventory availability stays above 95%.

## 5. What risks or limitations should leadership keep in mind?
* **Diminishing Returns:** The linear regression model assumes a straight line. In reality, adding more inventory will eventually stop yielding $2,961 per percent once the store is already 100% full. 
* **Missing Variables (Omitted Variable Bias):** Our model does not account for local macroeconomic health, specific competitor pricing strategies, or seasonal holiday interactions (which we flagged, but didn't build interaction terms for).
* **Outlier Sensitivity:** The model's accuracy is an average. Outlier stores (our massive over/under achievers) require human context to fully understand.

## 6. A Note on Correlation vs. Causation
While this regression model strongly identifies *associations*, it **does not automatically prove causation**. 
For example, we see that higher marketing spend is associated with higher sales. However, this does not guarantee the marketing *caused* the sales. It is highly possible that leadership simply allocates larger marketing budgets to stores that are *already located in high-revenue areas* (reverse causality). To prove pure causation, the business would need to run a randomized controlled trial (A/B testing) by randomly increasing marketing at select stores and observing the isolated lift.
