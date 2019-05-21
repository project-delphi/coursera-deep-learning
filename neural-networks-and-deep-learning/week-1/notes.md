# Week 1 Notes


## Introduction to Deep Learning

This week introduces what are Neural Networks and Deep Learning. It provides a high level overview along with some examples of what is possible with this technology.

### What is a Neural Network?

A neural network is a universal function approximator that is learned from examples of labelled data. It estimates the label based on the features - using convolutions of non-linear functions.

A neural network is defined by its architecture and choices of various hyperparameters. The basic unit of computation is a neuron - a *machine* that receives a number of inputs and produces an activated output (via an activation function) from it. Many such neurons can be stacked into more complicated neural network architectures.

The choice of activation function is usually made as a hyperparameter search, one of many well known candidates are tested.

The first set of neurons (called a layer) receive inputs from the input layer of features. These neurons then propogate their outputs to potentially other layers until the final layer, where they estimate the labelled data.

By convention, when counting layers, the input layer is called layer 0, and so is not counted when computing the total number of layers on a neural network architecture.

A network may have hidden layers which receive inputs from neurons and output to other neurons that are not the final layer - estimate of the label. These hidden layers can sometimes be interpreted as extracting features at a higher level.

Usually, the final layer is estimated as a probability distribution over the range of possible outcomes, but this can be condesed to just a point estimate.

#### Housing Price Example

Suppose we want to estimate the value of a house, based on a large set of historical dataset of houses with characteristics of each house (the *feature*) and its price (the *label*).


##### One Feature 

If we have just one feature that is the size of the house (in square meters), then we can think of a linear regression to find the coefficient and intercept (or bias) that links the size of a house to its price(in USD). 

This simple model can also be recast as a neural network. It is a network with just 1 input feature and it has just one neuron that predicts the output layer. The activation function is the just the identity, or linear unit.  

A better activation function would be one that puts a floor on the function of 0, to stop impossible negative house prices.  In such a case, we have what is called a rectified linear unit or RELU - which has become popular in training deep networks. 

Let's now consider how to estimate a house price when we have more features.

##### Many Features

Suppose now we have the same historical dataset, only now we have many features. In that case, we may believe that some features combine (in some non-linear way) and are better at estimating the price.

These hidden features can be seen as hidden layers - those that are not directly observed - and modelled using a more flexible network.

Here is an example:

We have features house size, bedrooms, zipcode and wealth. We believe that the best output layer has a RELU activation (or it could be learned through hyperparameter search).

We also believe that the final price is impacted by walkability, school quality and family size of a house. These are features that we don't directly observe. However, we can use a hidden layer to specify that, for example:

* Walkability is a function of zipcode
* School quality is a function of zipcode and wealth
* Family size is a function of house size and number of bedrooms

Rather than specifying these relationships exactly, we can set a fully connected feed-forward neural network. The network will learn from data the parameters and hyperparameters that define the actual relationships.

### Supervised Learning with Neural Networks

A lot of the excitement in machine learning is almost exclusively to do with supervised learning applications.

Supervised learning is about learning a good mapping from some input features to a label output (which could be a real number, a class, or a sequence of numbers/strings). Shown enough clear examples, a neural network of sufficient depth can become very good at estimating the output class.  As below there are many examples of this happening in various applications.

|Input ($\mathbf{x}$)| Output/Target (\mathbf{y})| Application |




### Why is Deep Learning Taking Off?

