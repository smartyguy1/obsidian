Gradient descent is a mathematical technique that iteratively finds the [[Linear Regression|weights and bias]] that produce the model with the lowest [[Loss|loss]]. Gradient descent finds the best weights and bias by repeating the following process for a number of user-defined iterations.

The model begins training with randomized weights and biases near zero, and then repeats the following steps:
- Calculate the loss with the current weight and bias.
- Determine the direction to move the weights and bias that reduce loss
- Move the weight and bias values a small amount in the direction that reduces loss. ^0847ec
- Return to step one and repeat the process until the model can't reduce the loss any further.
![[Pasted image 20250610170929.png]]
# Model convergence and loss curves
When training a model, you'll often look into a loss curve to determine if the model has converged. The loss curve shows how the loss change as the model trains.
![[Pasted image 20250610171136.png]]
It can be seen that loss dramatically decreases during the first few iterations, then gradually decreases before flattening out around the 1000th-iteration mark. After 1000 iterations, we can be mostly certain that the model has converged.

In the following figures, we draw the model at three points during the training process: the beginning, the middle, and the end. Visualizing the model's state at snapshots during the training process solidifies the link between updating the weights and bias, reducing loss, and model convergence.
![[Pasted image 20250610171610.png]]
^[snapshot at the beginning]

![[Pasted image 20250610171656.png]]
^[snapshot about midway during the training process]
![[Pasted image 20250610171726.png]]
^[At 1,000th-iteration, we can see that the model has converged, producing a model with the lowest possible loss]

### Convergence and convex functions

The loss functions for linear models always produce a convex surface. As a result of this property, when a linear regression model converges, we know the model has found the weights and bias that produce the lowest loss.

![[Pasted image 20250610172028.png]]
 It is important to note that the model almost never finds the exact minimum for each eight and bias, but instead finds a value very close to it. It's also important to note that the minimum for the weights and bias don't correspond to zero loss, only a value that produces the lowest loss for that parameter.

