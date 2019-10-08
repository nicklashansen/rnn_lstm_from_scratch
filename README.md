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


## Dataset

For this exercise we will create a simple dataset that we can learn from. We generate sequences of the form:

`a a a a b b b b EOS`, `a a b b EOS`, `a a a a a b b b b b EOS`

where `EOS` is a special character denoting the end of a sequence. The task is to predict the next token $t_n$, i.e. `a`, `b`, `EOS` or the unknown token `UNK` given the sequence of tokens $\{ t_{1}, t_{2}, \dots , t_{n-1}\}$ and we are to process sequences in a sequential manner. As such, the network will need to learn that e.g. 5 `b`s and an `EOS` token will occur following 5 `a`s.

## Results

The RNN takes considerable effort to converge to a nice solution:

![RNN loss](https://i.imgur.com/6v1ptyK.png)

The LSTM learns much faster than the RNN:

![LSTM loss](https://i.imgur.com/ZqF0wMA.png)

And finally, the PyTorch LSTM converges to an even better solution:

![PyTorch LSTM loss](https://i.imgur.com/6Rck79O.png)
