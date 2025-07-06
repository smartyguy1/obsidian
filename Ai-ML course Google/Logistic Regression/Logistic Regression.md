Many problems require probability estimate as output. Logistic regression is an extremely efficient mechanism for calculating probabilities. Practically speaking, you can use the returned probability in either of the following two ways: 

- Applied "as is." For example, if a spam-prediction model takes an email as input and outputs a value of 0.932, this implies a 93.2% probability that the email is spam. 

- Converted to a binary category such as True or False, Spam or Not Spam.

# Sigmoid function

^cb714b

there's a family of functions called logistic functions whose output has those same characteristics. The standard logistic function, also known as the sigmoid function (sigmoid means "s-shaped"), has the formula:
$$
f(x) = \frac{1}{1+e^{-x}}
$$
![[Pasted image 20250610182701.png]]
^[Graph of the sigmoid function.]
As the input `x` increases, the output of the sigmoid function approaches but never reaches `1`. Similarly, as the input decreases, the sigmoid function's output approaches but never reaches `0`

### Transforming linear output using the sigmoid function

The following equation represents the [[Linear Equations|linear]] component of a logistic regression model:
$$
z = b + w_1x_1 + w_2x_2 + \dots + w_Nx_N
$$
where,
- z = output of the linear equation, also called the log odds
- b = bias
- w = learned weights
- x = feature values

To obtain the logistic regression prediction, the $z$ value is then passed to the sigmoid function, yielding a value (a probability) between 0 and 1:
$$
y' = \frac{1}{1+e^{-x}}
$$
where:
- $y'$ is the output of the logistic regression model
- $z$ is the linear output.
![[Pasted image 20250610183319.png]]
^[Left: graph of linear function z = 2x+5; Right: sigmoid curve]

In Figure 2, a linear equation becomes input to the sigmoid function, which bends the straight line into an s-shape. Notice that the linear equation can output very big or very small values of z, but the output of the sigmoid function, y', is always between 0 and 1, exclusive. For example, the yellow square on the left graph has a z value of –10, but the sigmoid function in the right graph maps that –10 into a y' value of 0.00004.

