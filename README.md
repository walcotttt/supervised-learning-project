##INTRO
The following is a synthetic dataset of bank transactions. The goal of analyzing this dataset is to maximize detection of fraudulent transactions, while minimizing detection of false positives.


#EDA

While completing EDA, I quickly realized two things:
1. The dataset was quite large (6,362,620 rows kind of large!)
2. There were some large values (outliers) that were skewing most of the intial distributions I created.

In order to make the dataset more managable, I took a random sample of 1,000,000 rows.
To account for outliers, I applied a log scale to the historgrams. I also created boxplots to offer an alternative means of visualizing the outliers.

When atttemptign to identify which columns could habe possible relationships I generated a correlation matrix which revealed there were strong signs of linear between 'newbalanceDest' and 'oldbalanceDest'.