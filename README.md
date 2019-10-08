# How to build RNNs and LSTMs from scratch

Originally developed by me (Nicklas Hansen), Peter Christensen and Alexander Johansen as educational material for the graduate deep learning course at the Technical University of Denmark (DTU). You can access the full course material [here](https://github.com/DeepLearningDTU/02456-deep-learning-with-PyTorch).
____

In this lab we will introduce different ways of learning from sequential data.
As an example, we will train a neural network to do language modelling, i.e. predict the next token in a sentence. In the context of natural language processing a token could be a character or a word, but mind you that the concepts introduced here apply to all kinds of sequential data, such as e.g. protein sequences, weather measurements, audio signals or monetary transaction history, just to name a few.

To really get a grasp of what is going on inside the recurrent neural networks that we are about to teach you, we will carry out a substantial part of this exercise in NumPy rather than PyTorch. Once you get a hold of it, we will proceed to the PyTorch implementation.

In this notebook we will show you:
* How to represent categorical variables in networks
* How to build a recurrent neural network (RNN) from scratch
* How to build a LSTM network from scratch
* How to build a LSTM network in PyTorch
