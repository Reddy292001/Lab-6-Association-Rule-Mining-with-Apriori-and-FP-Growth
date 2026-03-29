# Market Basket Analysis using Apriori and FP-Growth

**Lab Assignment:** Market Basket Analysis using Apriori and FP-Growth

## Project Overview

This project performs **market basket analysis** on a transactional retail dataset using two frequent itemset mining algorithms:

- **Apriori**
- **FP-Growth**

After finding frequent itemsets, the project generates **association rules** and evaluates them using:

- **Support**
- **Confidence**
- **Lift**

The goal is to discover meaningful purchasing patterns and compare the performance of both algorithms.

## Dataset Used

This project uses the **Online Retail dataset** from the UCI Machine Learning Repository.

The dataset contains transaction-level retail records such as:

- `InvoiceNo`
- `Description`
- `Quantity`
- `UnitPrice`
- `CustomerID`
- `Country`

This dataset is suitable for market basket analysis because each invoice contains item-level purchase information.

## Files Included

- `market_basket_notebook_version.ipynb` – Main notebook file
- `README.md` – Project documentation

If you created multiple notebook versions, you can also include:

- `market_basket_notebook_version_1.ipynb`
- `market_basket_notebook_version_2_submission_ready.ipynb`

## Main Steps Performed

### 1. Data Preparation

The dataset was cleaned before applying frequent itemset mining.

Cleaning steps included:

- Removing cancelled invoices
- Removing rows with missing or blank item descriptions
- Removing rows with non-positive quantity
- Removing rows with non-positive unit price
- Selecting a country subset to reduce sparsity and improve efficiency
- Converting the transaction data into a one-hot encoded basket matrix

### 2. Exploratory Data Analysis

The notebook includes visualizations to better understand the dataset, such as:

- Bar plot of the most frequently purchased items
- Heatmap of item co-occurrence

These visualizations help identify frequently occurring products and possible item relationships.

### 3. Frequent Itemset Mining using Apriori

The Apriori algorithm was used to identify frequent itemsets using a selected minimum support threshold.

The notebook displays:

- Frequent itemsets
- Support values
- A bar plot of the top frequent itemsets

### 4. Frequent Itemset Mining using FP-Growth

The FP-Growth algorithm was applied using the same support threshold as Apriori.

The notebook then compares:

- Frequent itemsets found by FP-Growth
- Runtime of FP-Growth versus Apriori
- Similarities in output between the two methods

### 5. Association Rule Generation

Using the frequent itemsets, association rules were generated with a minimum confidence threshold.

The notebook includes the following rule metrics:

- Support
- Confidence
- Lift

Visualizations include:

- Scatter plot of confidence vs lift
- Bar plot of top rules by lift

### 6. Comparative Analysis

Finally, the notebook compares Apriori and FP-Growth in terms of:

- Execution time
- Number of frequent itemsets found
- Number of association rules generated
- Practical usability on this dataset

## How to Run the Notebook

### Option 1: Run in Google Colab

1. Open Google Colab
2. Upload the notebook file
3. Run the first installation cell to install required libraries
4. Run all remaining cells in order

### Option 2: Run Locally in Jupyter Notebook

Make sure Python is installed along with the required packages.

Install the required libraries using:

```bash
pip install ucimlrepo mlxtend seaborn openpyxl
```

Then open the notebook in Jupyter Notebook or JupyterLab and run the cells in order.

## Required Libraries

The project uses the following Python libraries:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `mlxtend`
- `ucimlrepo`

## Output and Results

The notebook produces:

- A cleaned transaction dataset
- A one-hot encoded basket matrix
- Frequent itemsets from Apriori
- Frequent itemsets from FP-Growth
- Association rules with support, confidence, and lift
- Visual comparison plots
- Runtime comparison between the two algorithms

## Key Observations

- Both Apriori and FP-Growth generally produce the same or very similar frequent itemsets when the same support threshold is used.
- FP-Growth is usually faster than Apriori because it avoids repeated candidate generation.
- Association rules with high lift and confidence indicate stronger product relationships.

## Challenges Faced

Some common challenges in this project were:

- The dataset is large and sparse
- Raw transaction data contains cancelled and invalid records
- Frequent itemset mining can become slow on the full dataset

These issues were handled by:

- Cleaning the dataset carefully
- Removing invalid rows
- Working with a country subset
- Using a binary basket matrix

## Conclusion

This project shows how frequent itemset mining can be used to discover useful customer purchase patterns from retail transaction data.

Apriori is simple and easy to understand, while FP-Growth is generally more efficient for larger datasets. The generated association rules can help businesses improve product recommendations, promotions, and shelf placement strategies.

## Notes

- Replace **[Course Title]** with your actual course name before submission.
- If required by your instructor, also add your lab number or section name.
- Make sure all notebook cells run successfully before submitting.
