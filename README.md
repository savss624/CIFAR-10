# CIFAR - 10

## Understanding the Data
The CIFAR-10 (Canadian Institute For Advanced Research) dataset consists of 60000 images each of 32x32x3 color images having ten classes, with 6000 images per category.

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
