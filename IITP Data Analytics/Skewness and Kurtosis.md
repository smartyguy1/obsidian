### Not skewed:
[[Measure of Central Tendency|mean=median=mode]]
![[Skewness fig 1.excalidraw]]
### Skewed data(-ve)
![[Skewness fig 2.excalidraw]]
Mean < Median < Mode
Mean - Mode = -ve

### Skewed data(+ve)
![[Skewness fig 3.excalidraw]]
# Measure of Skewness
## Absolute measure of skewness:
- $S_{K} = \text{mean} - \text{mode}$ 
- $S_{K} = \text{mean} - \text{median}$
- $S_{K} = (\theta_{3}-\theta_{2}) - (\theta_{2}-\theta_{1}) = \theta_{3}+\theta_{1}-2\theta_{2}$
## Relative Measure of skewness

### Karl-Pearson's Coefficient of Skewness:
$$
S_{KP} = \frac{mean-mode}{std} = \frac{3(mean-medium)}{std}
$$
- If $S_{KP}=0 => \text{mean} = \text{mode} = \text{median}$
- If $S_{KP} > 0 => \text{mean} > \text{mode} => \text{+ve skewed data}$
- If $S_{KP}< 0 => \text{mean} < \text{mode} => \text{-ve skewed data}$
### Bowley's Coefficient of Skewness:
$$
S_{KB} = \frac{Q_{1}+Q_{3} - 2Q_{2}}{Q_{3}-Q_{1}}
$$
- If $S_{KB}=0 => \text{Symmetric}$
- If $S_{KB} > 0 => (Q_{3}-Q_{2}) > (Q_{2}-Q_{1}) => \text{+ve skewed data}$
- If $S_{KB}< 0 => (Q_{3}-Q_{2}) < (Q_{2}-Q_{1}) => \text{-ve skewed data}$
# Moments
## Moments about an arbitrary point
$r^{th}$ moment ($\mu_{r}$) about a point A is defined
$$
\boxed{\array{\mu_{r}= \frac{\sum\limits_{i=1}^{n}{f_{i}(x_{i}-A)^{r}}}{\sum{f_{i} = N}} & r=0,1,2\dots}} 
$$
$\array{r=0 & \mu_{0}=1}$ 
$\array{r=1 & \frac{\sum{f_{i}(x_{i}-A)}}{N}} = \frac{\sum{f_{i}x_{i}-A\sum{f_{i}}}}{N} = \bar{x} - A$
$\array{r=2 & \frac{\sum\limits_{i=1}^{n}{f_{i}(x_{i}-A)^{2}}}{N}} = (\text{RMSD})^{2}$ 

## Moments about origin
$$
\boxed{\array{\mu_{r}' = \frac{\sum{f_{i}x_{i}^{r}}}{\sum{f_{i}}} & \mu_{0}' = 1, \mu_{1}'  =\bar{x}}}
$$
$$
\begin{align*}
\mu_{2}' &= \frac{\sum{f_{i}x_{i}^{2}}}{\sum{f_{i}}} = \overline{x^{2}}\\
\mu_{3}' &= \overline{X^3}
\end{align*}
$$
## Moments about mean (Central Moments)
$$
\boxed{\array{\mu_{r}= \frac{\sum\limits_{i=1}^{n}{f_{i}(x_{i}-\overline{x})^{r}}}{N} & r=0,1,2\dots}} 
$$
$$
\begin{align*}
\mu_{o}&= 1\\
\mu_{1}&= \frac{f_{i}(x_{i}-\overline{x})^{2}}{N} => X-\overline{X} =0\\
\mu_{2}&= \frac{\sum{f_{i}(x_{i}-\bar{x})^{2}}}{N} =\sigma^{2}\\\\
\mu_{3}&= \frac{\sum{f_{i}(x_{i}-\bar{x})^{3}}}{N}
\end{align*}
$$[[Measure of Dispersion|]]
## Relation between $\mu_{r}\text{ and }\mu_{r}'$ 
$$
\array{\mu_{r}= \frac{\sum{(x_{i}-\overline{x})^{r}}}{N} & \mu_{r}' = \frac{\sum{x_{i}^{r}}}{N}}
$$
$$
\mu_{r}= \frac{\sum(x_{i}^{r}- {}^{r}C_{1}x_{i}^{r-1}\bar{x} + {}^{r}C_{2}x_{i}^{r-2}\overline{x}^{2}+\dots + {}^{r}C_{r}(x_{i})^{r})}{N}
$$

