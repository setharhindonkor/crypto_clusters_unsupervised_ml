# Cryptocurrency Clusters

## Background

As part of the Advisory Services Team of a financial consultancy. One client, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. They need a report that includes what cryptocurrencies are on the trading market and to determine whether they can be grouped to create a classification system for this new investment.

A raw data has been obtained to be processed and fit to the machine learning models. Since there is no known classification system, this will require unsupervised learning. Several clustering algorithms will be used to explore whether the cryptocurrencies can be grouped together with other similar cryptocurrencies. Data visualization will be used to share findings with the investment bank.


## Data Preparation

The crypto_data.csv was read into Pandas. The dataset was obtained from CryptoCompare.

All cryptocurrencies that are not being traded was discarded. In other words, a filter for currencies that are currently being traded. Once this was done, the IsTrading column was dropped from the dataframe.

All rows that have at least one null value was removed.

Cryptocurrencies that have been mined was filtered for. That is, the total coins mined was greater than zero.

In order for the dataset to be comprehensible to a machine learning algorithm, the data was made numeric. Since the coin names do not contribute to the analysis of the data, it was deleted from the original dataframe.

The next step in data preparation was to convert the remaining features with text values, Algorithm and ProofType, into numerical data

The dataset was standardized so that columns that contain larger values do not unduly influence the outcome.


## Dimensionality Reduction

A dimensionality reduction with PCA was performed and rather than specify the number of principal components when you instantiate the PCA model, the desired explained variance was stated using 90% of the explained variance in dimensionality reduction. 

A further reduction of the dataset dimensions with t-SNE was done and visually inspected the results. 


## Cluster Analysis with k-Means

An elbow plot was created to identify the best number of clusters. A for-loop was used to determine the inertia for each k between 1 through 10.
