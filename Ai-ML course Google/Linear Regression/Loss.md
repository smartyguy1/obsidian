Loss is a numerical metric that describes how wrong a model's predictions are. Loss measures the distance between the model's predictions and the actual labels. The goal of training a model is the minimize the loss, reducing it to its lowest possible value.

![[Pasted image 20250610164725.png]]
# Types of losses
In linear regression, there are four main types of losses:

| Loss type                | Definition                                                                                           | Equation                                                  |
| ------------------------ | ---------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| $L_1\text{ loss}$        | The sum of the absolute values of the difference between the predicted values and the actual values. | $\sum{\|actual \ value - predicted \ value\|}$            |
| Mean absolute error(MAE) | The average of $L_1$ losses across a set of $N$ examples.                                            | $\frac{1}{N}\sum{\|actual \ value - predicted \ value\|}$ |
| $L_2$ loss               | The sum of the squared difference between the predicted values and the actual values.                | $\sum{(actual \ value - predicted \ value)^2}$            |
| Mean squared error(MSE)  | The average of $L_2$ losses across a set of $N$ examples.                                            | $\frac{1}{N}\sum{(actual \ value - predicted \ value)^2}$ |
The functional difference between $L_1$ loss and $L_2$ loss (or between MAE and MSE) is squaring. When the difference between the prediction and label is large, squaring makes the loss even larger. When the difference is small(less than 1), squaring makes the loss even smaller.

### Choosing the type of loss function
When choosing the best loss function, consider how you want the model to treat outliers. For instance, MSE moves the model more toward the outliers, while MAE doesn't. $L_2$ loss incurs a much higher penalty for an outlier than $L_1$ loss. For example, the following images show a model trained using MAE and a model trained using MSE. 
![[Pasted image 20250610170024.png]]
 Model trained with MSE modes the model closer to the outliers

![[Pasted image 20250610170148.png]]
Model trained with MAE is farther from the outliers