# Classifying Galaxy Morphology using Convlutional Neural Networks
## Abstract
The goal of this project is to train a deep learning classification model to predict galaxy morphology from their images. All galaxies could be classified into 3 main types: elliptical, spiral, and irregular (which also includes peculiar). The morphology of a galaxy can tell us a lot about its history (whether it has collided with another galaxy), and the aggregation of stars within it. I used data from the [Galaxy Zoo 2 project](https://data.galaxyzoo.org/) to predict whether a galaxy is spiral or elliptical. The images were originally labelled by citizen scientists in the DR7 legacy survey and a data table is provided by [Jaime Trickz](https://www.kaggle.com/jaimetrickz/galaxy-zoo-2-images) that maps each Galaxy ID to a specific set of images.

## Design
Scientists have classified elliptical and spiral galaxies into many different subtypes depending on their disks, bulges, and bars. These can range from E0, E1, up to E7 for elliptical and SAa, SBa, and SABa for normal, intermediate, and barred spirals. For the purposes of this project, I grouped all types of spirals (beginning with S) and ellipticals (beginning with E) into either a "Spiral" or "Elliptical". This was done for simplicity and because many subtypes did not have enough observations for the model to learn. Automatically classifying galaxy morphology can save us a lot of time and resources and make our outer space telescopes operate more autonomously. 

## Data
The original dataset includes over 300,000 galaxies and their specific classification. It also includes data about the survey conducted to classify them like the total number of votes and the total number of classification for a specific galaxy. They are originally divided into 59% spiral, and 41% elliptical. For better accuracy, I used a filter to look for observations that have more than 40 total classifications and more than 130 total votes. I also sampled half of the data left after applying the filter, and the data was reduced to 76,400 observations 53% of which are spiral, and 47% are elliptical.  

## Algorithms

### Model 

The model used is a Convolutional Neural Network with 3 convolutional layers, and 3 connected layers. d average pooling and dropout are also used to avoid overfitting.

### Model Evaluation and Selection

The dataset of 76,400 observations was split into 80/20 train and test sets. The train set was further divided 80/20 into train and validation subsets to find the optimal model and hyperparameters. The test set was never used during training or validation and was only used to score the model. I also trained my data on resnet18 with pretrained parameters to compare a pretrained to a non-pretrained model. Both are trained on 20 epochs.

### Non-pretrained model

* Training
    * Accuracy
    * precision
    * recall
  
* Testing
    * Accuracy
    * precision
    * recall

### Resnet18

* Training
    * Accuracy  99.02%
    * Precision 99.02%
    * Recall    99.13% 
 
* Testing
    * Accuracy
    * precision
    * recall

## Tools
* Numpy and Pandas to manipulate data
* Pytorch and Scikit-learn for modeling
* Ray tune for optimization
* Matplotlib for plotting

## Communication
![loss_graph](https://user-images.githubusercontent.com/75508181/149231884-3cfea88b-4047-4601-b0c3-e61f3ba8374f.png)
