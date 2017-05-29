# Make_a_neural_network
This is the code for the "Make a Neural Network" - Intro to Deep Learning #2 by Siraj Raval on Youtube

##Overview

This is the code for [this](https://youtu.be/p69khggr1Jo) video by Siraj Raval on Youtube. This is a [simple](http://computing.dcu.ie/~humphrys/Notes/Neural/single.neural.html) single layer feedforward neural network (perceptron). We use binary digits as our inputs and expect binary digits as our outputs. We'll use [backpropagation](http://neuralnetworksanddeeplearning.com/chap2.html) via gradient descent to train our network and make our prediction as accurate as possible.

##Dependencies

None! Just numpy.

## Data matrix
![https://cdn-images-1.medium.com/max/800/1*nEooKljI8XbKQh4cFbZu1Q.png]()
You might have noticed, that the output is always equal to the value of the leftmost input column. Therefore the answer is the ‘?’ should be 1.

## How to solve
* We will give each input a weight, which can be a positive or negative number. An input with a large positive weight or a large negative weight, will have a strong effect on the neuron’s output.
* Before we start, we set each weight to a random number.
* Take the inputs from a training set example, adjust them by the weights, and pass them through a special formula to calculate the neuron’s output.
* Calculate the error, which is the difference between the neuron’s output and the desired output in the training set example.
* Depending on the direction of the error, adjust the weights slightly. Repeat.
* Eventually the weights of the neuron will reach an optimum for the training set.

![https://cdn-images-1.medium.com/max/400/1*-1trgA6DUEaafJZv3k0mGw.jpeg]() Principle of backpropagation.

# How to calculate neuron's output
* First we take the weighted sum of the neuron’s inputs, which is:
![https://cdn-images-1.medium.com/max/800/1*RV7-CFkmmByfcXKkPcbAYQ.png]()
* Normalize - so result is between 0 and 1. Use Sigmoid function.
![https://cdn-images-1.medium.com/max/800/1*5il5GLo0gamypklQQ_z0AA.png]()
![https://cdn-images-1.medium.com/max/800/1*sK6hjHszCwTE8GqtKNe1Yg.png]()
* Substitute weighted sum function into Sigmoid function
![https://cdn-images-1.medium.com/max/800/1*7YdyG6fc6f6zMmx3l0ZGsQ.png]()

# How to dynamically adjust weights
* We adjust the weights. But how much do we adjust the weights by? Using Error weighted derivatives...
![https://cdn-images-1.medium.com/max/800/1*SQBjpbBcCT3lTQlPEdr1eg.png]()
* Why this formula? First we want to make the adjustment proportional to the size of the error.
* We used the Sigmoid curve to calculate the output of the neuron. Therefore, if the output is a large positive or negative number, it signifies the neuron was quite confident one way or another. We can see that at large numbers, the Sigmoid curve has a shallow gradient. If the neuron is confident that the existing weight is correct, it doesn’t want to adjust it very much.
* The gradient of the Sigmoid curve, can be found by taking the derivative: (Slope)
![https://cdn-images-1.medium.com/max/800/1*HdHm9u3_wjwBPmwuLg3D3g.png]()
* So by substituting the second equation into the first equation, the final formula for adjusting the weights is:
![https://cdn-images-1.medium.com/max/800/1*Jow4WVWNOp6rtiJ7vNQ0gQ.png]()


##Usage

Run ``python demo.py`` in terminal to see it train, then predict.

##Challenge

The challenge for this video is to create a 3 layer feedforward neural network using only numpy as your dependency. By doing this, you'll understand exactly how backpropagation works and develop an intuitive understanding of neural networks, which will be useful for more the more complex nets we build in the future. Backpropagation usually involves recursively taking derivatives, but in our 1 layer demo there was no recursion so was a trivial case of backpropagation. In this challenge, there will be. Use a small binary dataset, you can define one programmatically like in this example.

**Bonus -- use a larger, more interesting dataset**

##Credits

The credits for this code go to [Milo Harper](https://github.com/miloharper). I've merely created a wrapper to get people started.

##Additional Resources
More learning resources:
* [https://i.stack.imgur.com/eBPgU.png](https://cogsci.stackexchange.com/questions/7880/what-is-the-difference-between-biological-and-artificial-neural-networks)
* https://medium.com/technology-invention-and-more/how-to-build-a-simple-neural-network-in-9-lines-of-python-code-cc8f23647ca1#.fn92gnrar
* http://natureofcode.com/book/chapter-10-neural-networks/
* https://blog.dbrgn.ch/2013/3/26/perceptrons-in-python/
* http://neuralnetworksanddeeplearning.com/chap2.html
* https://iamtrask.github.io/2015/07/27/python-network-part2/

## Notes
Just as neurological synapses have weights to determine if will fire or not. Simple neurological computer
networks utilize the same principle when determining what value to place on a given set of inputs.
