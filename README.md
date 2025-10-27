# Market Basket Analysis

This project performs market basket analysis on a transactional dataset to identify frequently purchased itemsets and discover association rules between items. The analysis helps understand customer purchasing patterns and can be used for targeted marketing, product placement, and recommendations.

## Dataset

The dataset used in this analysis is the "Market Basket Analysis" dataset from Kaggle. It contains transactional data of an online retail store.

- **Source:** [https://www.kaggle.com/datasets/aslanahmedov/market-basket-analysis/data](https://www.kaggle.com/datasets/aslanahmedov/market-basket-analysis/data)

## Methodology

The analysis follows these steps:

1.  **Data Loading and Exploration:** Load the data from the CSV file and perform initial exploration to understand its structure, data types, and identify missing values and outliers.
2.  **Data Cleaning:** Clean the data by handling missing values, removing entries with negative prices or quantities, and filtering the data to focus on transactions from the United Kingdom.
3.  **Data Transformation:** Create a one-hot encoded matrix where each row represents a transaction (BillNo) and each column represents an item. The values indicate whether an item was present in a transaction.
4.  **Frequent Itemsets Mining:** Apply the Apriori algorithm to find frequent itemsets with a minimum support threshold of 0.01.
5.  **Association Rule Discovery:** Generate association rules from the frequent itemsets using the `association_rules` function, filtering for rules with a lift greater than 1.0.

## Results

The analysis identifies interesting association rules, such as the strong association between different herb markers (Thyme, Rosemary, Parsley, Mint, and Basil), indicating that customers who buy one type of herb marker are likely to buy others. The generated network graph visualizes the top association rules based on lift.

(Include more specific findings from your `filtered_rules` DataFrame here if desired)

## How to Run the Code

1.  Clone the repository to your local machine.
2.  Upload your kaggle API (https://www.kaggle.com/docs/api#authentication)
3.  Make sure you have the necessary libraries installed (pandas, numpy, matplotlib, seaborn, mlxtend, networkx). You can install them using pip:
