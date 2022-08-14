# Cryptocurrencies

Module 18 Challenge


## Overview

*Background*

Martha would like our help to pitch an investment for cryptocurrency to her firm, Accountability Accountants. The popularity of BitCoin has made it unaffordable to new investors. Thankfully, there are plenty of other cryptocurrencies that can be great starter investments. Using unsupervised machine learning, Martha would like us to analyze a dataset of cryptocurrenies. Unsupervised machine learning only uses input data, so this is a perfect usage. The result should be the UML learning a pattern within the data and helping Martha to decide which currency to pitch. 


*Purpose*

You and Martha have done your research. You understand what unsupervised learning is used for, how to process data, how to cluster, how to reduce your dimensions, and how to reduce the principal components using PCA. It’s time to put all these skills to use by creating an analysis for your clients who are preparing to get into the cryptocurrency market.

Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.

*Software*

-Python
-hvPlot
-Pandas
-path
-Plotly Express
-scikit-learn

## Analysis

*Deliverable 1: Preprocessing the Data for PCA*

The IsTrading column is dropped, rows that have null values are removed, and the CoinName column is removed. We further prepared the data using the sklearn library to standarize the features. Without this preparation, the next steps would not be possible

![Data Preprocessing](https://user-images.githubusercontent.com/102566199/184518101-63d481f7-706d-4348-bba9-2c5d206d5195.png)


*Deliverable 2: Reducing Data Dimensions Using PCA*

The PCA algorithm reduced the dimensions of the newest dataframe, X, down to only three principal components. 

![PCA Dimensions](https://user-images.githubusercontent.com/102566199/184518148-ed210b72-93bb-4616-8ebc-582bf398620b.png)


*Deliverable 3: Clustering Cryptocurrencies Using K-means*

Creating an elbow curve using the hvplot allows for the best value of K to be found. The elbow curve suggested that an elbow points at four was present. This means that the data can be classified into four classes. 

![Elbow Curve](https://user-images.githubusercontent.com/102566199/184518187-db7f64f0-4e49-4766-9f6a-8278f3378476.png)

Using the K-means algorithm, predictions of the K clusters will be made for the cryptocurrencies' data. The newest table, the clustered dataframe, concatenated two dataframes with the same columns and then columns, CoinName and Class, were added to hold the predictions. Due to the classification into 4 classes, each currency was plotted accordingly. 

![Clustering Table](https://user-images.githubusercontent.com/102566199/184518198-d387de77-b63e-4662-ba7b-49253ad1ebe1.png)

*Deliverable 4: Visualizing Cryptocurrencies Results*

A 3D-Scatter plot was used to visualize the crytocurrencies results. The PCA data and clusters were used to create the figure below. The three clusters from the clustered dataframe are show in three different colors. 

![Scatter Plot](https://user-images.githubusercontent.com/102566199/184518346-c7e9913d-48ce-4b56-90eb-0358f98e288c.png)

Using hvplot.table(), a tradable cryptocurrenies table was created. It can be easily scrolled through. Examining it, it is found that there are 532 tradable cryptocurrenies. This data can be scaled to create a scatter plot that will visualize the data. 

![Table of Tradable Crypto](https://user-images.githubusercontent.com/102566199/184518458-d33d6a8d-158c-4d8e-be64-f38e9cd0c724.png)

The scatterplot was created by plotting the TotalCoinsMined vs. TotalCoinSupply by class. This visualization is interactive as well and the column data of each point will be in a pop-up when the user hovers over it. Each currency is plotted with with the TotalCoinSupply vs. TotalCoinsMined. 

![Scatter Plot](https://user-images.githubusercontent.com/102566199/184518515-fbcab767-64e1-4681-aa65-7f424b8bc960.png)

Not only can the column data be seen when hovering, but the classes can be toggled to full opacity or not.

![Example Hover](https://user-images.githubusercontent.com/102566199/184518578-8fa80e98-5177-44a4-a26a-83b9f01a947f.png)

## Summary

The majority of the crytocurrencies were assigned to either Class 0 or Class 1, seen in blue and red on the final scatter plot. These two classes are clustered near the origin of the graph. If the classes of 2 and 3 are examined closer in the final scatter plot, it is seen that they are far and few between. 

![Outlier 1](https://user-images.githubusercontent.com/102566199/184518720-b6f9c52f-0f80-4dfb-9bb9-eb0f04687224.png)

![Outlier 2](https://user-images.githubusercontent.com/102566199/184518726-bd89013a-6ddb-4d37-be56-dd0648e747ac.png)

Above, the two outliers are identified as BitTorrent (yellow point) and the class 3 points vary and are difficult to identify becuase they are so busy near the origin. 

*Recommendations*

In the next analysis, it would be a good idea to run the same code and remove the class 2 and class 3 crytocurrencies. This might help to improve the scatter plot and create a better scaled visualization. It 
