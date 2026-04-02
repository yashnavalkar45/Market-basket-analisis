# Market Basket Analysis using Python
## Project Overview
This project performs "Market Basket Analysis (MBA)" on a retail dataset to identify frequent itemsets and discover strong association rules between products. By applying the "Apriori Algorithm", we can determine which items are frequently bought together (e.g., "If a customer buys Bread, they are 80% likely to buy Milk").

These insights are crucial for retail strategies such as:
* Cross-selling: Suggesting related products to customers.
* Store Layout Optimization: Placing associated items closer together.
* Promotional Bundling: Creating discount bundles for frequently paired items.

## Files in this Repository
* store_data.csv: The dataset containing 7,501 retail transactions.
* Market_Basket_Analysis.ipynb: The Jupyter Notebook containing the code for data preprocessing, the Apriori algorithm, and rule generation.

## Technologies Used
* Python: Core programming language.
* Pandas: For data manipulation and creating the transaction matrix.
* Mlxtend: For implementing the Apriori algorithm and generating association rules.
* Matplotlib / Seaborn: For visualizing support, confidence, and lift metrics.

## Methodology

### 1. Data Preprocessing
The raw dataset consists of transactions where each row represents a basket of items.
* Step 1: Loaded the dataset using Pandas.
* Step 2: Converted the dataframe into a list of lists format.
* Step 3: Applied TransactionEncoder to transform the list into a One-Hot Encoded boolean matrix (True/False indicating if an item exists in a transaction).

### 2. Frequent Itemset Mining (Apriori Algorithm)
We used the "Apriori algorithm" to filter out items that don't meet a specific threshold of popularity (Support).
* Minimum Support: Set to 0.01 (1%) to filter out rarely purchased items.

### 3. Association Rule Generation
We generated rules based on "Lift" and "Confidence" to find meaningful relationships.
* Metric: Lift (measures how much more likely items are bought together compared to random chance).
* Threshold: Rules with Lift > 1.0 (indicating a positive correlation).

## Key Insights & Results
After running the algorithm, we discovered several strong associations. Example insights:

| Antecedents (If you buy...) | Consequents (...you also buy) | Confidence | Lift |
|:----------------------------|:------------------------------|:-----------|:-----|
| *Frozen Vegetables* | *Shrimp* | 0.25       | 2.5  |
| *Escargots* | *Pasta* | 0.35       | 2.2  |
| *Ground Beef* | *Spaghetti* | 0.40       | 1.8  |
