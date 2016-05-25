# Data-Classifier
Training k-nearest neighbours and MLE classifier, and testing with test data.

### Overview
Uses Feature Selection and Extraction (Principal Component Analysis (PCA) and Dimensionality Reduction) to gain features by which to classify training data. Creates models using both Nearest-Centroid and Maximum Likelihood in order to classify test data.

### Objective
Create classifiers based on `150` training samples, in order to (hopefully) correctly classify `15` test samples.

### Feature Selection
Each of the `150` training samples and `15` test samples had `5` features. However, some of these features didn't yeild much information w.r.t. creating a classifier.

The first plan of action was plotting all the training data against each other, based on their features. Below are the `25` scatter plots:

![Scatter](https://raw.githubusercontent.com/crowoy/Data-Classifier/master/res/overall.png)

As you can clearly see from the plot, the `0`<sup>th</sup> and the `2`<sup>nd</sup> features are the best at clustering the data. There are `3` clusters which are well formed.

From here onwards, we will only use these `2` features of the data.

### Putting the Training Data into Classes

The k-mean algorithm was used to find the classes which each data point belonged to. This is done in an iterative process. I will not go into the actual algorithm here, if you would like more information: https://sites.google.com/site/dataclusteringalgorithms/k-means-clustering-algorithm

From this, the `3` clusters found earlier were classed (you can see the means of each cluster as well):

![Clusters](https://raw.githubusercontent.com/crowoy/Data-Classifier/master/res/clusters.png)

### Applying the Test Data
Now that we have our classes. Vornoi decision boundaries were put on the scatters. These decision boundaries tell you which test points are going to fall into which classes.

![Cluster and Test](https://raw.githubusercontent.com/crowoy/Data-Classifier/master/res/clusters1.png)

Basically, the decision boundaries tell you which cluster (centroid) a test point is closest to. It does not affect the actual classifier in any way. The test points are simply overlayed onto the classifier and coloured according to which class they fall into.

### Maximum Likelihood Classification

Finally, it was a also a good idea to see what a Maximum Likelihood (ML) Classifier would look like. For this, the idea was to create a classifier where the decision boundaries would effectively give a `95%` confidence about a test point belonging to a specific cluster. Both linear and non-linear decision boundaries were implemented.

![Linear MLE](https://raw.githubusercontent.com/crowoy/Data-Classifier/master/res/straightMLE.png)

![Non-Linear MLE](https://raw.githubusercontent.com/crowoy/Data-Classifier/master/res/MLE.png)

### Dependencies
- Python
- Jupyter Notebook
- Training and Test Data
