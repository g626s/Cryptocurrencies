# Cryptocurrencies
Analysis for clients who are preparing to get into the cryptocurrency market. 

## Resources:
<details>
<summary>Dataset:</summary>

- [crypto_data.csv](https://github.com/g626s/Cryptocurrencies/blob/main/crypto_data.csv)
</details>

<details>
<summary>Software and IDE:</summary>

- Python
- Jupyter Notebook
- Libraries:
  - Pandas
  - Sklearn
  - hvPlot
- Unsupervised Machine Learning
</details>

## Project Overview
Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. As the cyptocurrency market is highly saturated and volatile, we created a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment. The intial data was not ideal, so the data had to be processed to fit the machine learning models. Since there is no known output, we decided to use _unsupervised learning_. To group the cryptocurrencies, we incorporated a clustering algorithm. Lastly, we used data visualizations to share our findings.

For the technical analysis of this project, we:
- Preprocessing the Data for PCA
- Reducing Data Dimensions Using PCA
- Clustering Cryptocurrencies Using K-means
- Visualizing Cryptocurrencies Results

## Results and Methods
_Preprocessing the Data for PCA_

Using our knowledge of `Pandas`, we preprocessed the dataset in order to perform _PCA_. The `crypto_data.csv` was retrieved from [CryptoCompare](https://min-api.cryptocompare.com/data/all/coinlist). For this section of our project and methodology, we kept all the cryptocurrencies that are being traded. We then drop the _IsTrading_ column and removed rows that have at least one null value. From this we then filtered the _crypto_df_ DataFrame so it only has rows where coins have been mined. After we filtered the DataFrame, we create a new DataFrame that holds only the cryptocurrency names, and use the _crypto_df_ DataFrame index as the index for the new DataFrame. A crucial step in this process was to remove the _CoinName_ column from the _crypto_df_ DataFrame since it's not going to be used on the _clustering algorithm_. The _get_dummies()_ method was incorporated to create variables for the two text features, _Algorithm_ and _ProofType_, and store the resulting data in a new DataFrame named _X_. Lastly, we used the `StandardScaler` _fit_transform()_ function to standardize the features from the _X DataFrame_.

_Reducing Data Dimensions Using PCA_

_Clustering Cryptocurrencies Using K-means_

_Visualizing Cryptocurrencies Results_

## Summary
