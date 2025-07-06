[[Classification|]]True and false positives and negatives are used to calculate several useful metrics for evaluating models. Which evaluation metrics are most meaningful depends on the specific model and specific task, the cost of different misclassifications, and whether the dataset is balanced or imbalanced.

# Accuracy

It is the proportion of all classifications that were correct whether $+ve$ or $-ve$.
$$
\text{Accuracy} = \frac{\text{correct classifications}}{\text{total classifications}} = \frac{TP+TN}{TP+TN+FP+FN}
$$
Because it incorporated all four outcomes from the [[Thresholds and the confusion matrix#^818dab|confusion matrix]](TF, FP, TN, FN), given a balanced dataset, with similar numbers of examples in both classes, accuracy can serve as a coarse-grained measure of model quality. For this reason, it is often the default evaluation metric used for generic or unspecified models carrying out generic or unspecified tasks.

However, when the dataset is imbalanced, or where one kind of mistake (FN or FP) is more costly than the other, which is the case in most real-world applications, it's better to optimize for one of the other metrics instead.

# Recall or true positive rate

The true positive rate (TPR) or the proportion of all actual positives that were classified correctly as positives, is also known as recall.

$$
\text{Recall (or TPR)} = \frac{\text{correctly classified actual positives}}{\text{all actual positives}} = \frac{TP}{TP+FN}
$$
In an imbalanced dataset where the number of actual positives is very low, recall is a more meaningful metric than accuracy because it measures the ability of the model to correctly identify all positive instances. For applications like disease prediction, correctly identifying the positive cases is crucial

# False positive rate

It is the proportion of all actual negatives that were classified *incorrectly* as positives, also known as the **probability of false alarm**.
$$
\text{FPR} = \frac{\text{incorrectly classified actual negatives}}{\text{all actual negatives}} = \frac{FP}{FP+TN}
$$
In an imbalanced dataset where the number of actual negatives is very, very low, say 1-2 examples in total, FPR is less meaningful and less useful as a metric.

# Precision

 *Recall has $TP+FN$ in denominator while this has $TP+FP$*. 
 This metric tells us how precise in getting a true positive.

$$
\text{Precision} = \frac{\text{correctly classified actual positives}}{\text{everything classified as positive}} = \frac{TP}{TP+FP}
$$
Precision improves as false positives decrease, while recall improves when false negatives decrease. But as seen in the previous section, increasing the classification threshold tends to decrease the number of false positives and increase the number of false negatives, while decreasing the threshold has the opposite effects. As a result, precision and recall often show an inverse relationship, where improving one of them worsens the other.

# Choice of metric and tradeoffs
| Metric                           | Guidance                                                                                                                                                                                                                              |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Accuracy                         | Use as a rough indicator of model training progress/convergence for balanced datasets.<br><br>For model performance, use only in combination with other metrics.<br><br>Avoid for imbalanced datasets. Consider using another metric. |
| Recall  <br>(True positive rate) | Use when false negatives are more expensive than false positives.                                                                                                                                                                     |
| False positive rate              | Use when false positives are more expensive than false negatives.                                                                                                                                                                     |
| Precision                        | Use when it's very important for positive predictions to be accurate.                                                                                                                                                                 |