# CryptoClustering
This is the repository for Monash University Data Analytics Bootcamp Module 19 Challenge

## Contents

* `Crypto_Clustering.ipynb` Jupyter notebook containing the data query for this challenge
* `.png` images for the visualisations in this ReadMe

**Resources folder**

* `crypto_market_data.csv`csv file that contains the data for this challenge

## Analysis 

**1. What is the best value for `k`?**

K = 4 is the best value based on the above elbow curve

![alt text](<Elbow curve 1.png>)

**2. What is the total explained variance of the three principal components?**

0.37701473 + 0.34354479 + 0.17333394 = 0.8938934597944491

**3. What is the best value for `k` when using the PCA data?**

The best value for K is 4

**4. Does it differ from the best k value found using the original data?**

No, the best value remains as 4

![alt text](<Elbow curve 2.png>)

**5. After visually analysing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?**

After analyzing the cluster results, it can be found that the PCA data resulted in tighter clusters and resulted in more entries within cluster 0 and cluster 3 compared to the original scatter data.

![alt text](<Original data scatter plot.png>)

![alt text](<PCA scatter plot.png>)

## Instructions 

1. Rename the `Crypto_Clustering_starter_code.ipynb` file as `Crypto_Clustering.ipynb`.

2. Load the `crypto_market_data.csv` into a DataFrame.

3. Get the summary statistics and plot the data to see what the data looks like before proceeding.

## Prepare the Data

Use the `StandardScaler()` module from `scikit-learn` to normalize the data from the CSV file.

Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best value for `k` using the following steps:

* Create a list with the number of k values from 1 to 11.

* Create an empty list to store the inertia values.

* Create a `for` loop to compute the inertia with each possible value of `k`.

* Create a dictionary with the data to plot the elbow curve.

* Plot a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.

* Answer the following question in your notebook: What is the best value for `k`?

## Cluster Cryptocurrencies with K-means Using the Original Scaled Data

Use the following steps to cluster the cryptocurrencies for the best value for `k` on the original scaled data:

* Initialise the K-means model with the best value for `k`.

* Fit the K-means model using the original scaled DataFrame.

* Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.

* Create a copy of the original data and add a new column with the predicted clusters.

* Create a scatter plot using hvPlot as follows:

    * Set the x-axis as "PC1" and the y-axis as "PC2".

    * Colour the graph points with the labels found using K-means.

    * Add the "coin_id" column in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

## Optimise Clusters with Principal Component Analysis

* Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

* Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

    * What is the total explained variance of the three principal components?

* Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the PCA Data

Use the elbow method on the PCA data to find the best value for `k` using the following steps:

* Create a list with the number of k-values from 1 to 11.

* Create an empty list to store the inertia values.

* Create a `for` loop to compute the inertia with each possible value of `k`.

* Create a dictionary with the data to plot the Elbow curve.

* Plot a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.

* Answer the following question in your notebook:
    
    * What is the best value for `k` when using the PCA data?
    
    * Does it differ from the best k value found using the original data?

## Cluster Cryptocurrencies with K-means Using the PCA Data

Use the following steps to cluster the cryptocurrencies for the best value for `k` on the PCA data:

* Initialise the K-means model with the best value for `k`.

* Fit the K-means model using the PCA data.

* Predict the clusters to group the cryptocurrencies using the PCA data.

* Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.

* Create a scatter plot using hvPlot as follows:
    
    * Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
    
    * Colour the graph points with the labels found using K-means.

    * Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

* Answer the following question:
    
    * What is the impact of using fewer features to cluster the data using K-Means?

## Requirements

**Find the Best Value for k by Using the Original Data (15 points)**

To receive all points, you must:

* Code the elbow method algorithm to find the best value for k. Use a range from 1 to 11. (5 points)

* To visually identify the optimal value for k, plot a line chart of all the inertia values computed with the different values of k. (5 points)

* Answer the following question: What’s the best value for k? (5 points)

**Cluster the Cryptocurrencies with K-Means by Using the Original Data (10 points)**

To receive all points, you must:

* Initialise the K-means model with four clusters by using the best value for k. (1 point)

* Fit the K-means model by using the original data. (1 point)

* Predict the clusters for grouping the cryptocurrencies by using the original data. Review the resulting array of cluster values. (3 points)

* Create a copy of the original data, and then add a new column of the predicted clusters. (1 point)

* Using hvPlot, create a scatter plot by setting `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`. Colour the graph points with the labels that you found by using K-means. Then add the crypto name to the `hover_cols` parameter to identify the cryptocurrency that each data point represents. (4 points)

**Optimise the Clusters with Principal Component Analysis (10 points)**

To receive all points, you must:

* Create a PCA model instance, and set `n_components=3`. (1 point)

* Use the PCA model to reduce the features to three principal components. Then review the first five rows of the DataFrame. (2 points)

* Get the explained variance to determine how much information can be attributed to each principal component. (2 points)

* Answer the following question: What’s the total explained variance of the three principal components? (3 points)

* Create a new DataFrame with the PCA data. Be sure to set the `coin_id` index from the original DataFrame as the index for the new DataFrame. Review the resulting DataFrame. (2 points)

**Find the Best Value for k by Using the PCA Data (10 points)**

To receive all points, you must:

* Code the elbow method algorithm, and use the PCA data to find the best value for k. Use a range from 1 to 11. (2 points)

* To visually identify the optimal value for k, plot a line chart of all the inertia values computed with the different values of k. (5 points)

* Answer the following questions: What’s the best value for k when using the PCA data? Does it differ from the best value for k that you found by using the original data? (3 points)

**Cluster the Cryptocurrencies with K-means by Using the PCA Data (10 points)**

To receive all points, you must:

* Initialise the K-means model with four clusters by using the best value for k. (1 point)

* Fit the K-means model by using the PCA data. (1 point)

* Predict the clusters for grouping the cryptocurrencies by using the PCA data. Review the resulting array of cluster values. (3 points)

* Create a copy of the DataFrame with the PCA data, and then add a new column to store the predicted clusters. (1 point)

* Using hvPlot, create a scatter plot by setting `x="PC1"` and `y="PC2"`. Colour the graph points with the labels that you found by using K-means. Then add the crypto name to the `hover_cols` parameter to identify the cryptocurrency that each data point represents. (4 points)

**Visualise and Compare the Results (15 points)**

To receive all points, you must:

* Create a composite plot by using hvPlot and the plus sign (`+`) operator to compare the elbow curve that you created from the original data with the one that you created from the PCA data. (5 points)

* Create a composite plot by using hvPlot and the plus (`+`) operator to compare the cryptocurrency clusters that resulted from using the original data with those that resulted from the PCA data. (5 points)

* Answer the following question: Based on visually analysing the cluster analysis results, what’s the impact of using fewer features to cluster the data by using K-means? (5 points)

**Coding Conventions and Formatting (10 points)**

To receive all points, you must:

* Place imports at the top of the file, just after any module comments and docstrings, and before module globals and constants. (3 points)

* Name functions and variables with lowercase characters, with words separated by underscores. (2 points)

* Follow DRY (Don't Repeat Yourself) principles, creating maintainable and reusable code. (3 points)

* Use concise logic and creative engineering where possible. (2 points)

**Deployment and Submission (10 points)**

To receive all points, you must:

* Submit a link to a GitHub repository that’s cloned to your local machine and that contains your files. (4 points)

* Use the command line to add your files to the repository. (3 points)

* Include appropriate commit messages in your files. (3 points)

**Code Comments (10 points)**

To receive all points, your code must:

* Be well commented with concise, relevant notes that other developers can understand. (10 points)

## Resources

BCS Xpert Learning assistant

https://scikit-learn.org/stable/modules/clustering.html#clustering

https://stackoverflow.com/questions/74296474/how-to-interpret-explained-variance-ratio-plot-from-principal-components-of-pca

https://www.analyticsvidhya.com/blog/2021/01/in-depth-intuition-of-k-means-clustering-algorithm-in-machine-learning/

https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html


## Acknowledgments 

Dataset provided by provided by edX Boot Camps LLC.