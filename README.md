# PITE-PyTorch
Track Reconstruction using pytorch.

## Overview:

The main goal of the project is to show how different models perform with the problem of binary classification with given data from LHCb experiment, how to build your own model using libraries like sklearn or pytorch and to tune hyperparamiters of your model.

## current goal:
Now we are trying to understend the data and create good model that is suposed to predict if the particle with given features will be possible to detect in downstream detectors or if it's a "gohst particle".

## Future plans:
We woudl like to prepare some kind of guide or lecture to show how to use machine learning and deep machine learning models from sklearn and pytorch so that it can be used for teaching at our university.

## Data:
### We got over two million samples with 10 features, splited in to two categories determine by **is_downstream_reconstructible** to work with:
![](images/data.PNG)

### To understeand our data we split it for two classes and compare them side by side like this:
![](images/Histograms.PNG)

### Also, we create corelation matrix to drop most corelated features:
![](images/Corelation.PNG)
Code can be found hear: [DataAnalysis](https://github.com/Kavaldrin/PITE-PyTorch/blob/master/DataAnalysis.ipynb)
    
## SKLEARN:

### Logistic regresion:
For varius solvers {‘newton-cg’, ‘lbfgs’, ‘liblinear’, ‘sag’, ‘saga’}  and penaltty {‘l1’, ‘l2’, ‘elasticnet’} and max iterations {50, 150, 1000} we got similar score of 71% accuracy. [Logistic regresion]

### Random forest clasifier:
We mennaged to get score of 81% accuracy with this model and auc 0.87 tuning hyperparameters by hand.<br />
Trying grid serch cross validation and random search we got better result of 82% and auc 0.88.<br />
[RFC](https://github.com/Kavaldrin/PITE-PyTorch/blob/master/RFC.ipynb)

### Support Vector Machines:
I usually get score of ~80% accuracy with this model and auc 0.86.<br />
I use NuSVC model. I dropped some features to get better score also to make training faster. Tuning by guessing gave me 80% score.<br />
I will try to search for better hyperparametrs using Grid Search.<br />
[SVC](https://github.com/Kavaldrin/PITE-PyTorch/blob/master/svm.ipynb)

### Naive bayes classifier:
In this case results were really weak in comparasion with classifiers above. <br />
We managed to get accuracy around 69%. We have choosen Gaussian Kernel because of continous values in data set. <br />
It was almost impossible to tune this model, because of lack of hyperparameteres. <br />
Using this model we have removed dependency in data set to get best results <br />
[GaussianNB](https://github.com/Kavaldrin/PITE-PyTorch/blob/master/GaussianNB%20KNeighbors%20SVM.ipynb)

### K Nearest Neighbours classifier:
Results which we got using this classifier were slighty better than using NB classifier, accuracy around 75%. <br />
In this case we have used grid search to tune model and find best values of hyperparameters. <br />
The most important hyperparameter is number of neighbours, we got best results for 25.
Another thing which was important to get best results -> we had to normalize values in data set because this classifier is very sensitive to data sets where every value of feature is in another scale. <br />
[KNN](https://github.com/Kavaldrin/PITE-PyTorch/blob/master/GaussianNB%20KNeighbors%20SVM.ipynb)



## Authors

* **Kamil Hałat** - [Barnabasz](https://github.com/Barnabasz)
* **Miłosz Filus** - [Kavaldrin](https://github.com/Kavaldrin)
* **Dawid Gwiżdż** - [Nabiz](https://github.com/Nabiz)
* **Michał Piwowarczyk** - [MichalPiwo](https://github.com/MichalPiwo)
See also the list of [contributors](https://github.com/Kavaldrin/PITE-PyTorch/contributors) who participated in this project.

## PyTorch
### Logistic regresion
Pytorch let us got much beter resoults, we used logistic regression model with deep neural network generated in various shapes, and with tuning by hand give us satisfying results: accuracy = 88.8% and loss = 0.279,
with auc = 0.95.<br /> 
[pytorch - logistic regresion](https://github.com/Kavaldrin/PITE-PyTorch/blob/master/Binary%20clasification.ipynb)

## Django
We created simple web service using Django that let user pass one data sample to model and gives back prediction based on a trained mod. 
Sadly we weren't able to put it on our academic web server. [Django](https://github.com/Kavaldrin/PITE-PyTorch/tree/master/Django)

# [![Build Status](https://travis-ci.com/Kavaldrin/PITE-PyTorch.svg?branch=master)](https://travis-ci.com/Kavaldrin/PITE-PyTorch)
  
