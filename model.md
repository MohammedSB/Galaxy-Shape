## MVP Model Description


The goal of the model is to classify images of galaxies from their morphology. Galaxies will be classified into either Spiral or Elliptical. The model that will be used is a Convolutional Neural Network (CNN) since image data will be used to classify the galaxies. I PyTorch to build the network.

# About the Data

The original data gathered from Galaxy Zoo Table 2 has around 300,000 data points, however, only 35% (both training and testing) will be used in this model. The data is sampled to reduce the traninig time. 

![clas](https://user-images.githubusercontent.com/75508181/148419855-7e21806f-249e-42a8-b45d-7ee39d0d96f6.png)

The classes are quite balanced with 59% being spiral and 41% are elliptical. Train, validation, and test split will take place just before tranining.
