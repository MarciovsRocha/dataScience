# Discretização, Escala, Normalização e Imputação

Many Machine Learning algorithms perform better, 
or converge faster, if data share a commom scale 
or have gaussian-like behavior.

Some algorithms that fall in these categories:

* Logistic and Linear Regression
* kNN
* Neural Networks
* SVM-RBF
* Gaussian Naive Bayes
* Principal Component Analysis

## Diving in kNN (example)

* kNN is a lazy algorithm
* Training: it buffers instances
* Testing: classification is based on the k-nearest neighbors available in the buffer

### kNN - Duck Test

If looks like a duck, swims like a duck, and quacks 
like a duck, then it probably is a duck.

## Handling Categorical Features

* if the variable is categorical but not ordnial: Dummies/One-hot-encoding
* if the variable is categorial and ordinal: Label Encoder

## Scaling

The interval in which data is laid over changes.
The data distribution (shape) does not change. 
The new scale is usyally \[0;1\]

## Standardization

change so that the standard deviation becomes 1.
The new distribution tends to be gaussian-like.
The scaling proccess applucation is often implicit.

## Normalization

Often used as synonym to one of the previous aproaches.
Therefore, be clear and explicit on what you're doing
with data.

## Missing Data

Missing data is very commom. Main reasons behind missing data:

* Users did not want to provide their data due to privacy concerns
* Lack of data during data transfer

**Important:** some algorithms will ignore missing data, 
while others won't even run

### Approach 1 - Dropping rows 

In some cases, the number of rows with missing data 
is not that high $(\le 5 \%)$. In Such scenarios, 
we can think

### Approach 2 - Removing rows where most part of the variabels are missing

A more interesting approach is to remove rows only 
if a certain amount or percentage of columns
are missing, The treshold is variable 70,75,80

### Approach 3 - Dropping columns with too many missing values

If the amount of missing values for a column is too high, perhaps we should drop it

### Approach 4 - Data imputation

Another commo approach is to replace missing 
data by a generic value.

**Commom Approach:**

* Replace missing values with a '0', or a big (+99999) or small value (-99999)
* What about outliers? What is the impact of these values when creating ML models?

**Data imputation using statics:**

* Mean *(what if the data has outliers?)*
* Median
* Mode
