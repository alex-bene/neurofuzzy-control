# Function Approximation with Neural Networks

As part of the first assignment in the course of Neuro-fuzzy Control in Electrical and Computer Engineering in NTUA we were asked to approximate an unknown function f(x, y, z) --> x', y', z' with the help of an MLP model given 1001 points (meaning 1000 input-output pairs).

I ended using a simple 1-Hidden Layers Neural Network with 8 neurons trained for 300 epochs with Adabound optimizer and MSE loss and selected the best model out of all the epochs.

## Prerequisites

* pytorch (for the neural network)
* pytorchUtils (training pipeline)
* matplotlib (for plotting)
* scipy (to import .mat files)
* tqdm (for progress bars)
* adabound (optimizer)
* numpy

The adabound module is used to enrich pytorch with the implementation of Adabound optimizer. You can install it through:
```bash
pip install adabound
```

The pytorchUtils is a custom module that can be found in [this repository](https://github.com/alex-bene/pytorch-utils) and has some training and testing pipeline already implemented for pytorch (train and test functions as well as other features). You can install it through:
```bash
pip install pytorchUtils
```
