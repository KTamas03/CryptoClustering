## CryptoClustering
**Module 19 Challenge - Unsupervised Machine Learning**

In this scenario, I used Python and unsupervised machine learning to predict whether cryptocurrencies are influenced by changes in prices over different time periods. I performed all the work within a Jupyter Notebook.


**Repository Folders and Contents:**
- Resources:
  - crypto_market_data.csv
- Crypto_Clustering.ipynb


## Table of Contents

- [About](#about)
- [Getting Started](#getting-started)
- [Installing](#installing)
- [Contributing](#contributing)


## About

**Step 1.** 

First, I imported the data into a pandas dataframe and ran summary statistics. Then, I created a line chart to visualize the data. I observed that the cryptocurrency with the highest price change percentage over one year and 200 days was 'ethlend', followed by 'celsius-degree-token'. 'Theta-token' and 'havven' were also notable standouts.
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/e1cbb16f-3c80-4f40-9923-ab37034b39e3)

**Step 2.** 

Next, I normalized the data using the StandardScaler() module to ensure that all the features in the dataframe had equal weight. Afterward, I created a new scaled dataframe, with cryptocurrency names ('coin_id') as the index.

**Step 3.** 

Afterwards, I determined the optimal value for 'k'. I calculated inertia values for 'k' values ranging from 0 to 10 using the K-Means model. By plotting an elbow curve, I identified that the ideal number of clusters for the scaled dataset was 4:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/b0b1a269-4d07-4229-bf0b-4d448acaf655)

**Step 4.** 

With the results of the K-Means test in mind, I proceeded to predict the cluster assignments for each cryptocurrency and created a scatter plot of 'price_change_percentage_24h' versus 'price_change_percentage_7d':
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/1aae4cb4-fa10-4c9e-b22c-b107180f80e0)

**Step 5.** 

I then optimized the clusters using Principal Component Analysis (PCA) by setting the number of components to 3. Additionally, I set the random seed to 1 to ensure consistent random initialization of the PCA algorithm, allowing for reproducible results. It was observed that the total explained variance of the three principal components amounted to 88.94% or 0.8894, which is quite promising:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/a7554a7c-3d41-4792-be2b-4669cf9ba300)

**Step 6.** 

Subsequently, I generated a new dataframe containing the PCA data and proceeded to determine the optimal value for 'k' using the same K-Means approach. I identified that the ideal number of clusters for the PCA dataset was also 4:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/d852266d-3275-4bc8-8e71-b1e7c9712abb)

**Step 7.** 

Once again, relying on the results of the K-Means test, I proceeded to predict the cluster assignments for each cryptocurrency based on the PCA data. I then generated a scatter plot of Principal Component 1 (PC1) versus Principal Component 2 (PC2):
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/67c1aec2-2ac1-425a-b6ea-35b17a027fd1)

**Step 8.** 

Finally, I generated a composite plot displaying the elbow curves for both the scaled data and PCA data. Additionally, I created another composite plot featuring scatter plots illustrating the cluster formations based on the scaled data and the PCA data. In summary, it was observed that the optimal number of clusters was consistent across both the Scaled Data and PCA Data, with both indicating the presence of 4 clusters: 
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/69ac18e4-4912-49bd-8f4b-e489e834fa0b)


Furthermore, upon visually analyzing the cluster analysis results, it became evident that using fewer features to cluster the data with K-Means led to more distinct clusters that were visually prominent on the scatterplot. PCA, in this regard, eliminates less informative features from the data while retaining the most significant variance present in the original dataset. The second scatterplot, depicting PCA, clearly illustrates the presence of four distinct clusters, with 'ethland' marked in orange and 'celsius-degree-token' in yellow. Incidentally, these two cryptocurrencies exhibited significantly higher percentage price changes at the 200-day and 1-year marks compared to all other cryptocurrencies. Hence, isolating them into their respective clusters makes sense:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/9c31f9ad-72a1-41d8-9c12-669b837f003a)


**Resource File I Used:**
  - crypto_market_data.csv

**My Jupyter Notebook Python Script:**
  - Crypto_Clustering.ipynb

**Tools/Libraries I Imported:**
  - pandas library: for data manipulation and analysis
  - hvplot.pandas library: to create plots
  - sklearn.cluster: to create clusters using k-means
  - sklearn.decomposition: for principal component analysis (PCA)
  - sklearn.preprocessing: used for normalising the data


## Getting Started

**Programs/software I used:**
  - Jupyter Notebook: python programming tool, was used for data manipulation and consolidation.

**To activate dev environment and open Jupyter Notebook:**
  - Open Anaconda Prompt
  - Activate dev environment, type 'conda activate dev'
  - Navigate to the folder where repository is saved on local drive
  - Open Jupyter Notebook, type 'Jupyter Notebook'

## Installing

**Install scikit-learn library**
  - https://scikit-learn.org/stable/install.html

**Install hvPlot**
  - After activating the dev environment (see Getting Started), in terminal type 'conda install -c pyviz hvplot'.
  
## Contributing
  - How to create composite plots: https://holoviz.org/tutorial/Composing_Plots.html



