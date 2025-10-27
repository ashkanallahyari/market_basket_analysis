# Market Basket Analysis

This project performs **Market Basket Analysis** on a transactional retail dataset to identify frequently purchased itemsets and discover meaningful association rules between products.
The goal is to **understand customer purchasing behavior** and derive **actionable insights** for product bundling, recommendation systems, and marketing strategies.

---

## Problem Definition

Retailers often struggle to identify which products are commonly purchased together and how these relationships can drive sales.
This project aims to:

* Detect **frequently co-purchased items**.
* Quantify their relationships using **association metrics** (support, confidence, lift).
* Translate these insights into **business recommendations** that improve cross-selling and optimize store layout or online recommendations.

---

## Dataset

The dataset used in this analysis is the [**Market Basket Analysis** dataset from Kaggle](https://www.kaggle.com/datasets/aslanahmedov/market-basket-analysis/data).
It contains transaction-level data from an online retail store, including invoice numbers, product descriptions, quantities, prices, customer IDs, and countries.

---

## Methodology

The analysis follows these main steps:

1. **Data Loading and Exploration**

   * Load the data from CSV.
   * Explore structure, missing values, and basic statistics.

2. **Data Cleaning**

   * Removed transactions with negative quantities (returns).
   * Dropped rows with missing product names or prices.
   * Filtered for transactions from the **United Kingdom** for consistency.

3. **Data Transformation**

   * Grouped transactions by `BillNo` to form customer baskets.
   * Applied **one-hot encoding** using `TransactionEncoder` to prepare data for the Apriori algorithm.

4. **Frequent Itemset Mining**

   * Used the **Apriori algorithm** (`mlxtend.frequent_patterns`) with a `min_support` of 0.01.
   * Identified itemsets frequently appearing together.

5. **Association Rule Discovery**

   * Generated association rules using the `association_rules` function.
   * Filtered for rules with a **lift > 1.0** to focus on meaningful relationships.
   * Visualized the strongest rules using **network graphs** and **bar charts**.

---

## Key Findings

* Strong associations were observed among **Herb Marker products** (Thyme, Rosemary, Parsley, Mint, Basil).
* Customers who purchased one type of herb marker were significantly more likely to purchase others.
* Rules showed high **lift** and **confidence**, indicating strong co-purchase patterns rather than random coincidence.
* Visualization revealed clear clusters of related products, validating product-category affinities.

<img width="1019" height="642" alt="image" src="https://github.com/user-attachments/assets/126c96f5-7349-4c44-8f69-1837d9b52c55" />


---

## Business Recommendations

* **Cross-Sell Promotions:**
  Offer bundle discounts for items frequently bought together (e.g., “Buy any two herb markers, get 10% off a third”).

* **Product Placement:**
  Arrange highly associated products next to each other in stores or on online product pages to encourage impulse purchases.

* **Personalized Recommendations:**
  Implement rule-based suggestions in e-commerce (“Customers who bought *X* also bought *Y*”).

* **Inventory Planning:**
  Forecast joint demand for co-purchased items to avoid stockouts and improve replenishment cycles.

---

## Next Steps

1. **Segmentation:** Perform basket analysis separately by **customer segment**, **season**, or **country**.
2. **Business Validation:** Design **A/B tests** to measure uplift in revenue or basket size from recommendations or bundles.
3. **Sequence Analysis:** Extend to **sequential pattern mining** to uncover purchase order and temporal patterns.

---

## How to Run the Code

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/market-basket-analysis.git
   cd market-basket-analysis
   ```
2. Install dependencies:

   ```bash
   pip install pandas numpy matplotlib seaborn mlxtend networkx
   ```
3. Run the notebook or Python script:

   ```bash
   jupyter notebook Market_Basket_Analysis.ipynb
   ```
4. The output includes:

   * Cleaned transaction dataset
   * Frequent itemsets and association rules
   * Network and bar chart visualizations of top product associations

---

**Author:** Ashkan
**Tools Used:** Python, Pandas, MLxtend, Matplotlib, NetworkX, Seaborn
**Dataset Source:** [Kaggle - Market Basket Analysis](https://www.kaggle.com/datasets/aslanahmedov/market-basket-analysis/data)

---
