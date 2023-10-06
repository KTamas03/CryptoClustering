## CryptoClustering
**Module 19 Challenge - Unsupervised Machine Learning**

In this scenario, I used Python and unsupervised machine learning to predict whether cryptocurrencies are influenced by changes in prices over a 24-hour or 7-day period. I performed all the work within a Jupyter Notebook.


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

Firstly, I imported the data into a pandas dataframe, and ran summary statistics. A linechart was created to plot the data. I noticed that coin_id = 'ethlend' showed the highest price change percentage over 1 year and over 200 days, followed by coin_id = 'celsius-degree-token'. 'Theta-token' and 'havven' were the other two standouts.
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/e1cbb16f-3c80-4f40-9923-ab37034b39e3)

**Step 2.** 

I then normalised the data (using StandardScaler() module) to give all the features in the dataframe an equal weighting. I then created a new scaled dataframe, making coin_id the index.

**Step 3.** 

I then worked out the best value for k. I calculated inertia values based on k values from 0 to 10, using the k-Means model. I plotted an elbow curve, and I found the optimum number of clusters for the scaled dataset was 4:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/b0b1a269-4d07-4229-bf0b-4d448acaf655)

**Step 4.** 

Based on the outcome of the k-means test, I then predicted the cluster formations where each crytocurrency would fall in and created a scatter plot of the price_change_precentage_24h vs the price_change_percentage_7d:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/1aae4cb4-fa10-4c9e-b22c-b107180f80e0)

**Step 5.** 

Using Principal Component Analysis (PCA), I then optimised the clusters by setting the number of components to 3. I also set the random_seed to 1, to ensure the randomised initialisation of the PCA algorithm remained consistent and that my results could be reproduced. It was found that the total explained variance of the three principal components was 88.94% or 0.8894, which is quite good:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/a7554a7c-3d41-4792-be2b-4669cf9ba300)

**Step 6.** 

I then created a new dataframe with the PCA data and then worked out the best value for k using the same k-means method. I found the optimum number of clusters for the PCA dataset was also 4:
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/d852266d-3275-4bc8-8e71-b1e7c9712abb)

**Step 7.** 

Again based on the outcome of the k-means test, I then predicted the cluster formations where each cryptocurrency would fall in based on the PCA data. I created a scatter plot of principal component 1 (PC1) vs principal component 2 (PC2):
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/67c1aec2-2ac1-425a-b6ea-35b17a027fd1)

**Step 8.** 

Finally, I created a composite plot of the elbow curves for the scaled data and PCA data, and another composite plot of the scatter plots showing the cluster formations based on the scaled data and the PCA data. In summary, it was found that for both the Scaled Data and PCA Data that the optimum number of clusters was the same, 4 clusters. 
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/69ac18e4-4912-49bd-8f4b-e489e834fa0b)


Furthermore, after visually analysing the cluster analysis results, the impact of using fewer features to cluster the data using K-Means resulted in the clusters becoming more distince and easier to see visually on the scatterplot. PCA removes less informative features from the data, as it retains the most significance variance in the original dataset. The second scatterplot above for PCA, shows four distinct clusters, with 'ethland' in red and 'celsius-degree-token' in yellow. There two cryptocurrencies incidently showed significantly higher percentage price change at 200d and 1 year, compared to all the other cryptocurrencies. Splitting these two out into their own clusters makes sense.
![image](https://github.com/KTamas03/CryptoClustering/assets/132874272/9c31f9ad-72a1-41d8-9c12-669b837f003a)


**Resource File I Used:**
  - crypto_market_data.csv

**My Jupyter Notebook Python Cleaning Script:**
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



