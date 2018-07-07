# Handwriting Recognition

Code for recognizing digits using the MNIST database and a forward feed network.

Usage:

First we have to load the MNIST data. To do that we have a small helper program called mnist_loader.
We execute the following commands in a Python shell,
```
  import mnist_loader
  
  training_data, validation_data, test_data = \
  ... mnist_loader.load_data_wrapper()
  ```
 After loading the mnist data, we set up a network. This can be done by importing the program called Network as shown below:
 
 ```
 import network
 ```
 
 To create a network, we call the Network instance as shown below:
 
 ```
 net = network.Network([784, 30, 10])
 ```
 
 This will create a network with 30 hidden layers, 784 input layers(since every picture in database is 28*28 pixels=784) and 10 outer layers(one for each digit from 0-9).
Finally, we'll use stochastic gradient descent to learn from the MNIST training_data over 30 epochs, with a mini-batch size of 10, and a learning rate of η=3.0,
```
net.SGD(training_data, 30, 10, 3.0, test_data=test_data)
```
