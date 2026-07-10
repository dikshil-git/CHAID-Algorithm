# CHAID-Algorithm
CHAID merges categories of a predictor variable that are not significantly different with respect to the target variable, based on a chosen significance level (p-value threshold).

Multi-way Splits: Unlike CART which strictly builds binary trees (2 branches per node), CHAID can produce multiple branches from a single node depending on the number of distinct significant categories.

Categorical Data Focus: Although it can handle continuous variables by splitting them into bins or categories, CHAID is historically optimized for categorical/nominal data.

🔄 How the Algorithm Works
Category Merging: For each predictor variable, compute a contingency table with the target variable. Test the significance of the difference between categories using the Chi-squared test. If the p-value is greater than a threshold (e.g., 0.05), merge the two most similar categories. Repeat until no more categories can be merged.

Best Split Selection: Calculate the adjusted p-value for each merged predictor variable. The variable with the smallest p-value (strongest association with the target) is selected as the splitting attribute for the node.

Tree Growth: This process repeats recursively for each child node until a stopping criterion is met (e.g., minimum node size or maximum tree depth).
