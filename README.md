# Cryptocurrencies

## Overview

The purpose of the module was to analyze the dataset from many alternative cryptocurrencies to spot trends that inform an individual whether to invest.  The issue with cryptocurrencies is that the most common ones, like bitcoin or ethereum, are becoming unaffordable to the common public.  We used unsupervised machine learning to spot trends that result i opportunities of the cryptos.

## Resources
 - Datasets
     - crypto_data.csv
 - Technologies Used:
    - Python
    - Jupyter Notebook
    - Sklearn, Pandas, Hvplot libraries
    - Unsupervised Machine Learning

### Results

First step was to transform the data provided so that unsupervised machine learning could work.  This includes dropping null values, using only tradeable and mined currencies, numerically encoding categorical columns using pandas.get_dummies method, and scaling the date using StandardScaler method.  Also, we utilized Principal Component Analysis (PCA) to reduce the 98 scaled columns to only three components.

![webpage](https://github.com/diercz/Cryptocurrencies/blob/main/Images/Three%20Principals.png)

Afterwards, to see how many clusters to divide the cryptos into I created an elbow curve, which returned 4 clusters as the result.

![webpage](https://github.com/diercz/Cryptocurrencies/blob/main/Images/Elbow%20Curve.png)

I then proceeded to utilize KMeans analysis to fit the PCA dataframe and predict the clustering.  

![webpage](https://github.com/diercz/Cryptocurrencies/blob/main/Images/Clustered_DF_withClass.png)

I created a 3D visualization to better understand the results.  This locates each clustered crypto in relation to the three principal components created on the PCA.  As you can see, there are three major groups with one outlier.

![webpage](https://github.com/diercz/Cryptocurrencies/blob/main/Images/3D_PCA%20chart.png)

Similarly, when trying to graph the clustered cryptos by total supply and mined coins, we can observe two outliers. The first one with a lot of supply and a lot of mined coins (BitTorrent Crypto) and another one with a lot of supply but not too many coins mined (TurtleCoin).

![webpage](https://github.com/diercz/Cryptocurrencies/blob/main/Images/Scatter_Plot.png)

## Summary

The purpose of unsupervised machine learning is to help discover patterns in groups of data when there is no known output.  That being said, this analysis was successful at grouping cryptos into four groups.  If we were to create a crypto investment portfolio we would need to further analyze the clusters, but this was a good first starting point to identify the most profitable and known cryptos are that they are similar as categorized into two groups.  