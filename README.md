# RoboGarden-Capstone-Project

README

This project is my RoboGarden ML Bootcamp completion project.   The objective is to identify credit card fraud transactions.  A description of the dataset is listed below. 

License:  Public Domain (CCO)

The dataset was obtained from Data World (https://data.world/raghu543/credit-card-fraud-data) and is available on other data sites.
The dataset was collected and analysed during a research collaboration of Worldline and the Machine Learning Group.

Reference:	
Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015

Work Summary:
In this project I apply several classifiers such as Random Forest, SGD, SVC, Logistic Regression, MLP, and I apply a simple autoencoder method using keras Model to classify fraud vs. normal transaction in this highly unbalanced dataset.

Steps:
  1.	Analyse and visualize the data and remove duplicates. 
  2.	Run a first pass of 7 classifiers to see default performance.  Then optimize the classifiers with RandomSearchCV, CalibratedClassifierCV, and loops and re-run. 
  3.	Run MLP and Random Forest on a reduced feature set selected from feature importance.  
(The performance dropped marginally going from 29 to 10 features.)
  4.	Make a more balanced dataset (under-sampling) by randomly selecting 1500 normal transaction and merge with the fraud transactions (shuffle, re-indexe and split maintaining a consistent ratio of frauds in the train & test sets.  I again ran MLP & RF on this set.  Test results were very good with the reduced test set, but the trained models performed poorly on the larger full data test set.  Finally, I built a 6-layer autoencoder and ran it with 10 and 4 features.  I kept the nodes simple with 10, 5, 3, 3, 5, 10 and 4, 3, 2, 2, 3, 4 construction.

Possible future work may include (but not limited to):
  1.	Use SMOTE with the under-sampling / do more reading on applying the under-sampling technique.
  2.	Spend more time optimizing the classifiers by choosing more parameters to vary.
  3.	Investigate a hybrid classifier by voting with multiple classifiers to reduce false positives. Or feed a classifier with the    reconstructed output from the autoencoder.
  4.	Vary the combination of features used, / feature number and layers in the autoencoder.  Performance improved going from 10 to 4 features.  Conversely, build a larger model and use all features.  Or investigate extracting from the encoded layer.

References & Inspiration:
  1.	My classmates and TA’s at RoboGarden.
  2.	Scikit-learn documentation.
  3.	Online articles:
    a.	https://machinelearningmastery.com/tactics-to-combat-imbalanced-classes-in-your-machine-learning-dataset/
    b.	https://towardsdatascience.com/extreme-rare-event-classification-using-autoencoders-in-keras-a565b386f098
  4.	kernel:  (https://www.kaggle.com/currie32/predicting-fraud-with-tensorflow)

Dataset Description:
The dataset contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.
It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, ... V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.
Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.
The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection. More details on current and past projects on related topics are available on http://mlg.ulb.ac.be/BruFence and http://mlg.ulb.ac.be/ARTML
Please cite: Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015
