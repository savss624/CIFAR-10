# CIFAR - 10
![intro](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/intro.jpeg)

## Understanding the Data
The ***CIFAR-10 (Canadian Institute For Advanced Research)*** dataset consists of 60000 images each of 32x32x3 color images having ten classes, with 6000 images per category.

The dataset consists of 50000 training images and 10000 test images.

The classes in the dataset are airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck.

## Data Exploration
![DE0](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/load%20data.png)

The above line of code returns training and test images along with the labels.

Let's quickly print the shape of training and testing images shape.

![DE1](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/data%20shape.png)

Let's also find out the total number of labels and the various kinds of classes the data has.

![DE2](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/class%20names.png)

Now, plot the CIFAR-10 images.

![DE3](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/images.png)

## Feature Reduction Using Principal Component Analysis (PCA)
Now comes the most exciting part. We will see how PCA turn high-dimensional data into a low-dimensional principal components.

### But, Why use PCA ?
PCA is applied on images for a number of reasons. They are:
* ***Number of features:*** Images have huge number of features. Even a small image of 28 x 28 pixels will have 784 features to deal with.
* ***Lot of Covariance:*** When you look at an image, it is easy to understand that if we have the values for one pixel 'p', the pixels in the vicinity of 'p' will generally have similar values.
* Other fundamental reasons to apply PCA are that it ***reduces memory consumption** and **Speed Up*** the training models, reducing time taken.

### Apply PCA
But before that, let's reshape the image dimensions from three to one (flatten the images).

![reshaping](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/data%20flattening.png)

Next, make the instance of the PCA model. And lets fit PCA on the whole training data.

![pca fit](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/pca%20fit1.png)

So, currently our training data possess total of 3072 features.
Now, we will decide the value of ***'k'*** on the basis of amount of variance we want PCA to retain.

![optimal k](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/optimal%20k.png)

Thus, by keeping 217 components out of 3072, we shall retain 95% variance.

Finally, fit the PCA model again on the training data, but this time we'll also pass the optimal k (i.e. 217) as a parameter

![pca fit](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/pca%20fit2.png)

We have reduced the number of components from ***3072 to 217***. ***Reproduced the Images***, by getting the approximation from the reduced data.

This data will not be the same as the original data, as after applying PCA we lose some of the original data. But lets try and plot these images and see how much difference is achieved.

![images after pca](https://github.com/savss624/Readme-Images/blob/main/CIFAR%20-%2010/images%20after%20pca.png)

Next Step is to fit the same model to test data and transform it.

## Apply Classification Models

Models that we're using :
* ***Logistic Regression***
* ***Random Forest***
* ***Gaussian NaiveBayes***
* ***K Nearest Neighbor***
* ***Support Vector Machines***

Lets fit all models on the training data and get the testing accuracy score.

| Algorithms | Accuracy Score  |
| :-----: | :-: |
| ***Logistic Regression*** | 0.4081 |
| ***Random Forest*** | 0.441 |
| ***Gaussian NaiveBayes*** | 0.3147 |
| ***K Nearest Neighbor*** | 0.2279 |
| ***Support Vector Machines*** | 0.5518 |

Looks like, we're achieving the maximum score with SVM ( i.e. 0.5518 ). Still its not a good score. But, the best that can be achieved right now! 
