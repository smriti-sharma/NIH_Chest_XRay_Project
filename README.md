# NIH_Chest_XRay_Project
The project aims at solving the multi-label classification problem in a medical domain dataset.
An associative classifier is designed using Formal Concept Analysis (FCA).
NIH Chest X-Ray image dataset from Kaggle is used for experiments.

# For preprocessing data

**Code - FeatureExtractionPreprocess.ipynb (Python 3)**

Extracts GLCM features ( Contrast, Homogeneity, Energy, Correlation, Dissimilarity, ASM, Inverse Difference Moment, Variance, Sum Average from the X-Ray images, etc.)
from the X-Ray images then handles outliers and normalize the data.

**Code - FirstOrder.ipynb (Python 3)**

Etracts first order featers (Mean, Variance, Skewness and Kurtosis) from the X-Ray images then handles outliers and normalize the data.

# For implementing MLKnn

**Code - MLKnn.ipynb (Python3)**

For implementing multi label classifier MLKNN

# For implementing a multi label classifier Lattice Miner approach

**Code - Making_transactions.ipynb (Python 3)**

This code file converts the data into the csv file of transactions that is again converted in cex format by fcastone software.

**Code - Rules.ipynb (Python 3)**

This code converts the rules generated from FCA lattice miner tool into the desired format ( csv having attributes as : premises, consequence, support and confidence).
This creates two type of csv files;
  - CAR  rules - class association rules of type features->labels
  - Correlation rules - of type labels->labels

**Code - Approach1.ipynb (Python 3)**

We separated rules of each class. For each new instance, it was matched with rules of every disease and its Jaccard was computed.
With the rule of whichever disease, this instance gave the maximum Jaccard value, it was assigned that class.

**Code - Approach2.ipynb (Python 3)**

Every instance will be matched with every rule. Then for each instance, top k Jaccard values were considered, and the majority class was assigned.
This was done just like the K-Neighbors approach operates.
