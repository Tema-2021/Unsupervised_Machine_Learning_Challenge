# Unsupervised_Machine_Learning_Challenge
_____________________________________________________

## Cryptocurrency Clusters
_____________________________________________________
![image](https://user-images.githubusercontent.com/82990618/136713939-1b7dafdd-456c-4184-8113-0fbb648f0f50.png)


### Contributor: 

**Valense Acquah-Louis**

## Background

Cryptocurrency is a collection of binary data designed to work as a means of exchange. Individual coin ownership records are stored in a computerizes database ledger, the transaction records (e.g. the creation of additional coins, verification of transfer of coin ownership etc.) from these ledgers are secured using strong cryptography.
For this homework, we use **Unsupervised Machine Learning** to predict if analysis on cryptocurrency data.
Two models will be used to create a report that includes what cryptocurrencies are on the trading market and determine whether they can be grouped to create a classification system for this new investment. These models are, 
* Clusters 
* K-Means Elbow Curve. 
 
**Source of data:**

The source data is in the form of a raw data, so the data will first be processed and used to fit the machine learning models. The is no known classification system, hence the use of unsupervised learning. Several clustering algorithms will be used to explore whether the cryptocurrencies can be grouped together with other similar cryptocurrencies and data visualization will be used to share the findings with the investment bank.

The data was obtained from https://min-api.cryptocompare.com/data/all/coinlist (CryptoCompare)

* crypto_data.csv


### Analysis

**Data Preparation**

Using a series of steps, the data was prepared for the analysis. The steps are listed below.
*	Reading
*	Cleaning (filtering, elimination)
*	Standardize 
*	Reduction

**Reading & Cleaning**
* Read crypto_data.csv into Pandas. 
*  Discard all cryptocurrencies that are not being traded. Filter for currencies that are currently being traded. Once done this, drop the IsTrading column from the dataframe.
*  Remove all rows that have at least one null value.
*  Filter for cryptocurrencies that have been mined. That is, the total coins mined should be greater than zero.
*  Since the coin names do not contribute to the analysis of the data, delete the CoinName from the original dataframe to make the data comprehensible to a machine learning algorithm.
*  Convert the remaining features with text values, Algorithm and ProofType, into numerical data using Pandas to create dummy variables. Examine the number of rows and columns of your dataset now. How did they change?

**Standardize**

* Standardize your dataset so that columns that contain larger values do not unduly influence the outcome.

### Dimensionality Reduction and Models

* Creating dummy variables dramatically increased the number of features in the dataset. Dimensionality reduction with **PCA** was performed. Rather than specify the number of principal components when the **PCA** model is instantiated, the desired **explained variance was stated**. For example, say that a dataset has 100 features. Using **PCA**(n_components=0.99) creates a model that will preserve approximately 99% of the explained variance, whether that means reducing the dataset to 80 principal components or 3. For this project, 90% of the explained variance in dimensionality reduction was preserved. 
*  Next, further reduction of the dataset dimensions with **t-SNE** was performed  and the results visually inspected. To accomplish this task, **t-SNE** was run on the principal components: the output of the **PCA** transformation. Then a scatter plot of the **t-SNE** output was created. 

### Scatter Plot


**Fit the models**

After the processing the data was fit to the Logistic Regression and Random Forest Classifier model to determine which was more accurate i.e., whether the Logistic Regression or the Random Forrest Classifier performed better. 
The models were scored

**Scale and Fit the Models**

Using StandardScaler, the training and testing sets were scaled. The scaled data were re-fitted to the LogisticRegression and RandomForestClassifier models and scored. 
Again, which model performed better was determined. 

### Prediction and Results

**Prediction**

*Unscaled Model*

Between the two forms of sklearn module (classification) I think the Random Forest Classifier will give a better result than the Logistic Regression, this is because in the Random Forrest Classifier the presence of the estimators which I look at as questions to help make the classification more precise helps make it more accurate. 

*Scaled Model*

Between the two forms of sklearn module (classification) I think the Random Forest Classifier will give a better result than the Logistic Regression irrespective of the data being scaled (i.e. making the data more uniformed due to difference in things like the units of, measure etc.), as stated above Random Forrest Classifier the presence of the estimators which I look at as questions to help make the classification more precise helps make it more accurate. 

**Results**

*Unscaled Model*

Between the two forms of sklearn module (classification) the Random Forest Classifier did perform better than the Logistic Regression as predicted, this is because in the Random Forrest Classifier 500 estimators were used and helped make the classification more precise/ accurate.  

*Scaled Model*

The results of the scaled data were not as predicted the testing score for the Logistic Regression was better than the Random Forrest Classifier, probably the Random Forrest Classifier was over fitted and the number of estimators my need to be changed
