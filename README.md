## Intro

The following is a synthetic dataset of bank transactions. The goal of analyzing this dataset is to maximize detection of fraudulent transactions, while minimizing detection of false positives.


# EDA

While completing EDA, I quickly realized two things:
1. The dataset was quite large (6,362,620 rows)
2. There were outlier that were skewing most of the preliminary distributions created

In order to make the dataset more managable, I took a random sample of 1,000,000 rows.
To account for outliers, I applied a log scale to the historgrams. I also created boxplots to offer an alternative means of visualizing the outliers.

When atttemptign to identify which columns could habe possible relationships I generated a correlation matrix which revealed there were strong signs of linear between 'newbalanceDest' and 'oldbalanceDest'.

# Cleaning

To begin the data cleaning process, I considered which columns would be the focus of my efforts. Since the goal is to detect fradulent transactions I decided to drop columns that did not contain any financial data. The following columns were dropped:

- Step: A unit of time that represents hours in the dataset. Think of this as the timestamp
of the transaction (e.g. hour 1, hour 2, ... hour 534, ...)
- NameOrig: The origin account name
- NameDest: The destination account name
- IsFlaggedFraud: A “naive” model that simply flags a transaction as fraudulent if it is
greater than 200,000 (note that this currency is not USD)