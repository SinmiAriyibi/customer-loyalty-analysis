# Customer Loyalty Analysis

Which customers does this retailer depend on, and who is starting to slip away? I used RFM segmentation on 4,338 customers to find out.

- **Portfolio page:** https://sinmiariyibi.my.canva.site
- **Interactive dashboard:** [add your Tableau Public link]

## Questions

- Which customers drive the most revenue?
- Which high-value customers are at risk of leaving?
- How many customers come back, and what do repeat customers buy?

## What I found

| Finding | Number |
|---|---|
| High-Value Loyalists | 1,317 customers (30.4%) bring in 73.0% of sales |
| At-Risk High Value | 449 customers (10.4%), 10.8% of sales |
| At-Risk average behavior | 4.68 orders, $499.83 average order value, $2,128.69 average spend, about 106 days since last purchase |
| Repeat customers | 2,845 customers (65.6%) bought more than once |
| One-time customers | 1,493 customers (34.4%) |

At-Risk High Value customers used to buy often and spend well, and they haven't ordered in a while. They are the group worth a win-back effort first.

## Segments

| Segment | Customers | Share of customers | Share of sales |
|---|---|---|---|
| High-Value Loyalists | 1,317 | 30.4% | 73.0% |
| At-Risk High Value | 449 | 10.4% | 10.8% |
| Regular Customers | 1,004 | 23.1% | 5.7% |
| New & Promising | 665 | 15.3% | 5.6% |
| Lapsed | 903 | 20.8% | 4.9% |

Each customer is scored 1 to 4 on Recency, Frequency and Monetary value using quartiles. Segment rules:

- **High-Value Loyalists:** R, F and M all 3 or higher
- **New & Promising:** R 3 or higher, F 2 or lower
- **At-Risk High Value:** R 2 or lower, F and M 3 or higher
- **Lapsed:** R equals 1, F 2 or lower
- **Regular Customers:** everyone else

## Data and cleaning

Data: Online Retail dataset (UCI / Kaggle), transactions from 2010-12-01 to 2011-12-09. The analysis date is one day after the last transaction.

| Step | Rows |
|---|---|
| Original | 541,909 |
| Removed (missing customer ID, duplicates, zero or negative quantity or price, cancelled invoices) | 149,217 |
| Clean | 392,692 |

After cleaning: 4,338 customers, 18,532 orders, $8,887,208.89 total sales, $479.56 average order value.

## Run it

```bash
pip install pandas numpy matplotlib openpyxl jupyter
# put Online Retail.xlsx next to the notebook
jupyter notebook customer_loyalty_analysis.ipynb   # run top to bottom
```

The notebook exports `customer_loyalty_tableau.csv` and `customer_segments.csv` for the Tableau dashboard.

Tools: Python (pandas, numpy, matplotlib), Tableau Public.
