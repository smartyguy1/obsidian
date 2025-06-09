1. **Range**
2. **Quartile deviation**
3. **Mean deviation
4. **Standard Deviation**
# Range
$$
\text{Range} = R = X_{max} - X_{min}
$$
$$
\text{coeff. of Range} = \text{COR} = \frac{X_{max}- X_{min}}{X_{max}+ X_{min}} < 1
$$
# Quartile Deviation
$$
\text{Qw} = \frac{Q_{3}-Q_{1}}{2}
$$
$$
\text{Coeff. of Qw(CQW)} = \frac{Q_{3}-Q_{1}}{Q_{3}+Q_{1}}
$$
## Inter-Quartile Range (IQR) = $Q_{3}-Q_{1}$ 
This is used to find Outliers.
We first find the interval using:
$$
\text{Interval} = [ \ Q_{1} - 1.5\cdot\text{IQR}, \ Q_{3} + 1.5\cdot\text{IQR}]
$$
Values that lie outside this interval are outliers

## Box Plot
![[Measure of Dispersion fig 1.excalidraw]]
# Mean Deviation

## For Ungrouped data:

$$
A = \left\{\array{\text{Mean} \\ \text{Median} \\ \text{Mode}}\right.
$$
$$
\frac{|x_{1}-A| + |x_{2}-A| + \dots + |x_{n}-A|}{n} = \frac{\sum\limits_{i=1}^{n}{|x_{i}-A|}}{n}
$$
The Mean Deviation $\sum{|x_{i}-A|}$ is minimum when A is median

## For Grouped Data:
$$
\text{MD} = \frac{\sum\limits_{i=1}^{n}{f_{i}}|x_{i}-A|}{\sum{f_{i}}}
$$
## Merits of Mean Deviation
- It utilizes all the observations
- Easy to calculate and understand
- It is not much affected by extreme values
## Demerits of Mean Deviation
- Negative deviation is made +ve
- It is not useful for further mathematical analysis
$|x| \rightarrow \text{not differentiatble at x = 0}$ 

# Variance & Standard Deviation
$$
\begin{align*}
\text{Variance} &= \sigma^{2} = \frac{\sum{(x_{i}-\bar{x})^{2}}}{n}\\
\text{Standard Deviation} &= \sigma = \sqrt{\frac{\sum{(x_{i}-\bar{x})^{2}}}{n}}
\end{align*}
$$
## For grouped data
$$
\sigma^{2}= \frac{\sum\limits_{i=0}^{n}{f_{i}(x_{i}-\bar{x})^{2}}}{\sum{f_{i}}}
$$
### Another formula for Variance
$$
\text{Var}(X) = \overline{x^{2}} - \overline{x}^{2} = \sigma^{2}
$$

### Coefficient of Variation = $\text{CV} = \frac{\sigma}{\bar{x}} \times 100$ 

^6b6bf1

## Combined mean $\bar{X}$
$$
\bar{X} = \frac{\bar{x}N_{1}+\bar{y}N_{2}}{N_{1}+N_{2}}
$$
## Combined Variance
$$
\begin{align*}
d_{1}&= \bar{x} - \bar{X}\\
d_{2}&= \bar{y} - \bar{X}\\
\\

\sigma^{2}&= \frac{N_{1}(\sigma_{1}^{2}+d_{1}^{2}) + N_{2}(\sigma_{2}^{2}+ d_{2}^{2})}{N_{1}+N_{2}}
\end{align*}
$$
# Root Mean Squared Deviation(RMSD)
$$
\text{RMSD} = \sqrt{\frac{\sum\limits(x_{i}-A)^{2}}{N}}
$$
$A\rightarrow \text{median or mode}$ 
If $A = \bar{x}$ then $\text{RMSD} = \sigma$ 
[[#^6b6bf1 |Coefficient of Variation]] is a relative measure of variability

