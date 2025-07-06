Logistic Regression models are trained using the same process as [[Linear Regression]] models, with two key distinctions:
- Logistic regression models use the [[^log loss|log loss]] as the loss function instead of [[Loss|squared loss]].
- Applying <span title="Any mechanism that reduces overfitting"><u>regularization</u></span> is critical to prevent <span title= "Creating a model that matches the training data so closely that the model fails to make correct predictions on new data."><u>overfitting</u></span>.

# Log loss

Unlike a Linear Regression model, the rate of change of a logistic regression model is not constant. As we saw the [[Logistic Regression#^cb714b|sigmoid]] curve is S-shaped rather than linear. 
When the log-odds ($z$) value is closer to 0, small increases in $z$ result in much larger changes to $z$ than when $z$ is a large positive or negative number.

Instead, the loss function for logistic regression is Log loss.
$$
\text{Log Loss} = \sum_{(x,y)\in D} -y\log(y') - (1 - y)\log(1 - y')|1
$$
where:
- $(x,y) \in D$ is the dataset containing many labeled examples, which are $(x,y)$ pairs.
- $y$ is the label in a labeled example. Since this is logistic regression, every value of $y$ must either be 0 or 1.
- $y'$ is the model's prediction( somewhere between 0 and 1), given the set of features in $x$

# Regularization in logistic regression

**Regularization**, a mechanism for penalizing model complexity during training, is extremely important in logistic regression modeling. Without regularization, the asymptotic nature of logistic regression would keep driving loss towards 0 in cases where the model has a large number of features.

Most logistic regression models use one of the following two strategies to decrease model complexity:
- $L_2$ regularization
- Early stopping: Limiting the number of training steps to halt training while loss is still decreasing.
