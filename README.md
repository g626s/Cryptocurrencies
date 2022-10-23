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

<img width="705" alt="Screen Shot 2022-10-22 at 5 06 42 PM" src="https://user-images.githubusercontent.com/107281474/197366921-803184b9-8f16-4cc1-9e0b-eedc3a49b1e0.png">


_Reducing Data Dimensions Using PCA_

Using our knowledge of how to apply the `Principal Component Analysis (PCA)` algorithm, we reduced the dimensions of the _X DataFrame_ to _three principal components_ and place these dimensions in a new DataFrame.

<img width="746" alt="Screen Shot 2022-10-22 at 5 08 38 PM" src="https://user-images.githubusercontent.com/107281474/197366965-8da7b13f-10a5-4fcb-8a39-797d2aac05ba.png">

_Clustering Cryptocurrencies Using K-means_

Using our knowledge of the `K-means` algorithm, we created an elbow curve using `hvPlot` to find the best value for K from the _pcs_df DataFrame_ that was created previously. Then, we ran the `K-means` algorithm to predict the _K clusters_ for the cryptocurrencies’ data.

<img width="756" alt="Screen Shot 2022-10-22 at 5 11 14 PM" src="https://user-images.githubusercontent.com/107281474/197367002-e7258c65-21e4-4f77-9b4b-cffe481ff038.png">


_Visualizing Cryptocurrencies Results_

Using our knowledge of creating scatter plots with `Plotly Express` and `hvplot`, we visualized the distinct groups that correspond to the three principal components we created previously, then we created a table with all the currently tradable cryptocurrencies using the _hvplot.table() function_.

<img width="722" alt="Screen Shot 2022-10-22 at 5 15 01 PM" src="https://user-images.githubusercontent.com/107281474/197367059-8cdf058a-014b-4506-827f-c7f88bb96611.png">

## Summary
