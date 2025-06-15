These are variables that control different aspects of training. The common hyperparameters are:
- [[#^9384ff|Learning rate]]
- [[#^c632fb|Batch size]]
- [[#^797c8e|Epochs]]
In contrast, parameters are  the variables like the [[Linear Regression|weights and bias]], that are part of the model itself. In other words, hyperparameters are values that you control; parameters are values that the model calculate during training.

# Learning rate
^9384ff
This is a floating point number you set that influences how quickly the model converge. If it is too low, the model can take a long time to converge. However, if the learning rate is too high, the model never converges, but bounces around the weights and biases that minimize the loss. The goal is to pick a learning rate that is not too high nor too low so that the model converges quickly.

The model multiplies the gradient by the learning rate to determine the model's parameters (weight and bias values) for the next iteration. In the [[Gradient Descent#^0847ec|third step of gradient descent]].

The ideal learning rate helps the model converge within a reasonable number of iterations. 
![[Pasted image 20250610173627.png]]

In, contrast a learning rate that's too small can take too many iterations to converge.
![[Pasted image 20250610173818.png]]

A learning rate that's too large never converges because each iterations either causes the loss to bounce around or continually increase.
![[Pasted image 20250610173908.png]]

![[Pasted image 20250610173920.png]]

# Batch Size
^c632fb
It is a hyperparameter that refers to the number of examples the model processes before updating its weights and bias. You might think that the model should calculate the loss for _every_ example in the dataset before updating the weights and bias. However, when a dataset contains hundreds of thousands or even millions of examples, using the full batch isn't practical.

Two common techniques to get the right gradient on _average_ without needing to look at every example in the dataset before updating the weights and bias are stochastic gradient descent and mini-batch stochastic gradient descent.

- **Stochastic gradient descent(SGD)**: Stochastic gradient descent uses only a single example(a batch size of one) per iteration. Given enough iterations, SGD works but is very noisy. "Noise" refers to variations during training that cause the loss to increase rather than decrease during an iteration. The term "stochastic" indicates that the one example comprising each batch is chosen at random. ^bbd9a4

![[Pasted image 20250610181130.png]]
Note that using stochastic gradient descent can produce noise throughout the entire loss curve, not just near convergence.

- **Mini-batch stochastic gradient descent(mini-batch SGD)**: Mini-batch stochastic gradient descent is a compromise between full-batch and [[#^bbd9a4|SGD]]. For $N$ number of data points, the batch size can be any number $n$ which is $1<n<N$. The model chooses the examples included in each batch at random, averages their gradients, and then updates the weights and bias once per iteration.

Determining the number of examples for each batch depends on the dataset and the available compute resources. In general, small batch sizes behaves like SGD, and larger batch sizes behaves like full-batch gradient descent.

![[Pasted image 20250610181636.png]]
When training a model, you might think that noise is an undesirable characteristic that should be eliminated. However, a certain amount of noise can be a good thing. In later modules, you'll learn how noise can help a model generalize better and find the optimal weights and bias in a neural network.

# Epochs

^797c8e
During training, an epoch means that the model has processed every example in the training set *once*. For example, given a training with 1,000 example and a mini-batch size of 100 examples, it will take the model 10 iterations to complete one epoch.

Training typically requires many epochs. That is, the system needs to process every example in the training set multiple times.

![[Pasted image 20250610182142.png]]

| Batch type                             | When weights and bias updates occur                                                                                                                                                                                       |
| -------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Full batch                             | After the model looks at all the examples in the dataset. For instance, if a dataset contains 1,000 examples and the model trains for 20 epochs, the model updates the weights and bias 20 times, once per epoch.         |
| Stochastic gradient descent            | After the model looks at a single example from the dataset. For instance, if a dataset contains 1,000 examples and trains for 20 epochs, the model updates the weights and bias 20,000 times.                             |
| Mini-batch stochastic gradient descent | After the model looks at the examples in each batch. For instance, if a dataset contains 1,000 examples, and the batch size is 100, and the model trains for 20 epochs, the model updates the weights and bias 200 times. |