# iPhone Case Price Optimization Project

## Overview

This project focuses on optimizing prices for iPhone cases using advanced statistical techniques and machine learning models. The goal is to find price points that maximize revenue under various conditions, including regular and promotional events.

By analyzing sales data and applying Generalized Additive Models (GAMs), we capture the non-linear relationships between price, quantity sold, and events, allowing for nuanced price recommendations.

---

### Data Preparation

1. **Load Data**: The project begins by loading historical sales data for iPhone cases.
2. **Feature Engineering**:
    - Created a binary `is_event` column to indicate whether a sale was part of a promotion.
    - Calculated `revenue` for each sale as `price * quantity_sold`.
3. **Data Filtering**:
    - Filtered data based on promotions to analyze normal sales and promotional events separately.

### Exploratory Analysis

1. **Price vs. Quantity Sold Trends**:
    - Visualized the relationship between price and quantity sold for different products.
    - Used `Plotly` to create interactive scatter plots with a LOWESS trendline for better visual insights.
2. **Event Analysis**:
    - Analyzed how promotions impact quantity sold using scatter plots with faceting by product type and color-coded by event.

### Modeling with Generalized Additive Models (GAMs)

1. **GAM for Price Optimization**:
    - Since prices have a non-linear relationship with quantity sold, we used GAMs to model this relationship.
    - Applied Expectile GAMs with quantiles (0.025, 0.5, 0.975) to capture different levels of revenue prediction and confidence intervals.
2. **GAMs with Events**:
    - GAMs were adapted to analyze promotional events separately. Events were encoded as categorical variables, allowing the model to account for different promotional effects on quantity sold.

### Event Analysis and Price Optimization

1. **Revenue Prediction**:
    - Calculated predicted revenues for different price points using the median, lower, and upper quantiles from the GAM models.
    - Identified the price point that maximized median predicted revenue and provided confidence intervals.
2. **Optimal Price Points**:
    - Using GAM predictions, determined optimal price points based on revenue maximization at different quantiles for each product.

### Results and Visualization

1. **Revenue Optimization Plots**:
    - Visualized the optimal price points for each product, showcasing the maximum median revenue and its confidence intervals.
    - Created plots to show how promotional events affect sales and revenue potential across different price points.

### Key Technologies

- **Libraries**: `pandas`, `numpy`, `statsmodels`, `pygam`, `plotly`, `plotnine`
- **Models**: Expectile Generalized Additive Models (GAMs)
- **Visualization**: Interactive plots using `plotly`, and static charts using `plotnine`.

# KEY BUSINESS INSIGHTS

Price optimization is crucial for maximizing revenue and profitability. If done wrong, a business could be potentially be MISSING MILLIONS OF DOLLARS. This project provides actionable insights into how businesses can leverage price optimization effectively.

**Example Insight: Premium Case | iPhone 15 Pro Max**

For the Premium Case | iPhone 15 Pro Max:

- Setting the price at **$40** would yield **$37,500** in daily revenue.
- However, according to the model, increasing the price to **$70** could boost daily revenue to **$45,000**.
- This results in a **$7,500 increase per day**, which, when multiplied over a year (365 days), amounts to approximately **$2.74 million** in additional annual revenue.

**Example Insight: Standard Case | iPhone 15 Pro** 

For the Standard Case | iPhone 15 Pro: 

- Setting the price at **$40** would yield approximately **$9000** in daily revenue.
- However, according to the model, increasing the price around **$20** could boost daily revenue to **$13,000**.
- This results in a **$4000 increase per day**, which, when multiplied over a year (365 days), amounts to approximately **$1.46 million** in additional annual revenue.

This example demonstrates the significant impact of price optimization, even for a single product. Applying these insights across a broader product range can lead to substantial gains, making price optimization a valuable tool for business growth and revenue maximization.
### Conclusion

This project effectively identifies price points that maximize revenue under both normal and promotional conditions. By leveraging GAMs, we gain insight into complex price-quantity relationships, providing a strong foundation for data-driven pricing strategies.
