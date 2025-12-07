# Financial Performance Analysis & Visualization

This script performs the final stage of a financial data pipeline. It takes a pre-processed DataFrame containing calculated banking KPIs (Key Performance Indicators), outputs statistical summaries, and generates a suite of visualizations to identify trends, correlations, and outliers in financial performance.

## 📋 Overview

The code focuses on analyzing the relationships between income generation, operational efficiency, and risk management. It produces the following outputs:
1.  **Statistical Summary:** A textual overview of the dataset's distribution.
2.  **Correlation Heatmap:** To identify dependencies between variables.
3.  **Pairwise Analysis:** To visualize distributions and scatter plots for key profitability metrics.
4.  **Trend & Distribution Plots:** Scatter, Line, and Box plots for deep-dive analysis into specific metrics like RoE, Leverage, and Operating Costs.

## 🛠 Dependencies

To run this visualization suite, you need the following Python libraries:

*   **Pandas:** For data handling.
*   **Matplotlib:** For base plotting.
*   **Seaborn:** For statistical data visualization.

```bash
pip install pandas matplotlib seaborn
```

## 📊 Data Requirements

The script assumes a Pandas DataFrame object named **`df`** is already loaded in memory with the following calculated columns:

*   `Interest Income %`
*   `Net Interest Income Margin (NIM)`
*   `Risk Adjusted Interest Income (RAII)`
*   `Profit Before Tax % (PBT)`
*   `Profit After Tax % (PAT) (RoA)`
*   `Return on Equity (RoE)`
*   `Leverage Ratio`
*   `Operating Cost % (Opex)`
*   `Non-Interest Revenue % (NIR)`
*   `Credit Loss % (CLR)`

## 📉 Visualization Guide

### 1. Correlation Heatmap
*   **Purpose:** Displays the correlation coefficients between all numerical variables.
*   **Insight:** Helps identify strong positive or negative relationships (e.g., Does high `Leverage Ratio` correlate with lower `RoA`?). Red indicates positive correlation; Blue indicates negative.

### 2. Pairplot (Key Metrics)
*   **Variables:** Interest Income, NIM, RAII, PAT (RoA), RoE.
*   **Purpose:** Shows the univariate distribution (diagonal) and bivariate relationships (off-diagonal) for the most critical profitability ratios.
*   **Insight:** Useful for spotting clusters or non-linear relationships.

### 3. Scatterplot (Interest Income vs. RoE)
*   **Axes:** X = Interest Income %, Y = Return on Equity.
*   **Hue (Color):** Leverage Ratio.
*   **Purpose:** Analyzes how interest generation translates to equity returns, while visualizing the impact of financial leverage.

### 4. Line Plot (PBT vs. PAT)
*   **Purpose:** Compares Pre-Tax Profit against Post-Tax Profit across data points (banks/periods).
*   **Insight:** The gap between the two lines visualizes the tax burden/efficiency.

### 5. Boxplot (Opex, NIR, CLR)
*   **Purpose:** Shows the spread, median, and outliers for Operating Costs, Non-Interest Revenue, and Credit Losses.
*   **Insight:** Quickly identifies if any specific entity has abnormally high operating costs or credit losses compared to the group.

## 🚀 Usage

Ensure your DataFrame `df` is populated, then run the script:

```python
# [... Preceding code that loads and calculates 'df' ...]

# Run the visualization block
print("Updated DataFrame with Calculated Metrics:")
print(df)
# ... rest of the provided script
```

## 🏷️ Tags
`python` `pandas` `seaborn` `financial-analysis` `data-visualization` `fintech` `KPIs` `banking-metrics`
