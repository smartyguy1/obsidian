[[Classification|]]Let's say we have a logistic regression model for spam-email detection that predicts a value between 0 and 1, representing the probability that a given email is spam. 

To deploy this model, we need to convert the model's raw numerical output into one of two categories: "spam" or "not spam".

To make this conversion, we choose a threshold probability, called a classification threshold. Examples with probability greater than threshold value are then assigned to the positive class, the class you are testing for(here `spam`). Examples with a lower probability are assigned to the negative class, the alternative class (here, `not spam`).

## Confusion matrix

^818dab

The probability is not reality. There are four possible outcomes for each output from a binary classifier. For the spam classifier example, if you lay out the ground truth as columns and the model's prediction as rows--This is called the confusion matrix.

|                    | Actual positive                                                                                                                                                 | Actual negative                                                                                                                                 |
| ------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Predicted positive | **True positive (TP)**: A spam email correctly classified as a spam email. These are the spam messages automatically sent to the spam folder.                   | **False positive (FP)**: A not-spam email misclassified as spam. These are the legitimate emails that wind up in the spam folder.               |
| Predicted negative | **False negative (FN)**: A spam email misclassified as not-spam. These are spam emails that aren't caught by the spam filter and make their way into the inbox. | **True negative (TN)**: A not-spam email correctly classified as not-spam. These are the legitimate emails that are sent directly to the inbox. |
When the total of actual positives is not close to the total of actual negatives, the dataset is imbalanced.

### Effect of threshold on true and false positives and negatives

Different thresholds usually result in different numbers of true and false positives and true and false negatives.