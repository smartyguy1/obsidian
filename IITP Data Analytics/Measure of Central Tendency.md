# Arithmetic Mean
### Ungrouped Data
$$
\text{mean} = \bar{x} = \frac{x_{1}+x_{2}+\dots+x_{n}}{n} = \frac{\sum\limits_{i=1}^{n}x_{i}}{n}
$$
If frequency is given:
$$
\bar{x} = \frac{\sum{f_{i}x_{i}}}{\sum{f_{i}}}
$$
### For Grouped Data

| Marks(X) | Frequency(f) | Mid-Value(x) | $f_{i}x_{i}$ |
| -------- | ------------ | ------------ | ------------ |
| 0-10     | 3            | 5            | $3\times5$   |
| 10-20    | 5            | 15           | $5\times15$  |
| 20-30    | 7            | 25           | $25\times7$  |
| 30-40    | 9            | 35           | $9\times35$  |
| 40-50    | 4            | 45           | $45\times4$  |
$$
\bar{x} = \frac{\sum{f_{i}x_{i}}}{\sum{f_{i}}} = \frac{15+75+175+315+180}{28} = 27.14
$$

### Properties of Mean
1. Sum of deviation of observations from the mean is zero
$$\begin{align*}
x_{1}, x_{2}, x_{3}\dots,x_{n}\rightarrow\bar{x} \\
(x_{1}-\bar{x}) + (x_{2}-\bar{x}) + \dots + (x_{n}-\bar{x}) =0\\
\sum\limits_{i=1}^{n}{x_{i}}-n\bar{x} = 0
\end{align*}

$$
2. Sum of square of deviations taken from mean is minimum in comparison to the same taken  from any other average.(median/mode)
$$
\sum\limits_{i=1}^{n}({x_{i}-\bar{x}})^{2} \le \sum\limits_{i=1}^{n}({x_{i}-A})^{2}
$$
### Demerits of mean
1. It is badly affected by outliers
2. It is generally not preferred for highly skewed data

# Median
### For ungrouped data
- Arrange the data in either ascending or descending order
- If n is **odd** middle value will be the median
- If n is **even** $\frac{\frac{n}{2}^{\text{th}} + (\frac{n}{2} + 1)^{\text{th}}}{2} = \text{median}$   
### Frequency data
$$

^4bc9d5

\text{median} = \text{value of corresponding to cumulative frequency} \geq \sum\limits_{i=1}^{n}\frac{f_{i}}{2}\text{ or } \frac{N}{2}
$$
### For Grouped data
$$
\begin{align*}
\text{Median} = L + \frac{(\frac{N}{2} - C)}{f}\times{h}\\
L = \text{lower class limit of the median class}\\
C = \text{Cumulative frequency of pre-median class}\\
f = \text{frequency of the median class}\\
h = \text{width of the median class}
\end{align*}
$$

![[central tendency table.excalidraw| 600]]
### Merits
- Easy to understand and compute
- It is not affected by extremely small or large values
### Demertis
- In case of even values, we get only estimated value of median
- It doesn't utilize all the observations
- It is affected by sampling fluctuations

# Mode
Highest frequency observation

### For grouped data:
$$
\text{data} = L + \frac{|f_{1}-f_{0}|}{|f_{1}-f_{0}| + |f_{1}-f_{2}|}\times{h} = \frac{h(f_{1}-f_{0})}{2f_{1}-f_{0}-f_2}
$$

$$
\begin{align*}
L &= \text{lower class limit of the modal class}\\
f_{1}&= \text{freq. of modal class}\\
f_{0}&= \text{freq. of pre-modal class}\\
f_{2} &= \text{freq. of post-modal class}\\
h &= \text{width of the modal class}
\end{align*}

$$
### Relationship between mean, median and mode
$$
\begin{align*}
O = 3A - 2M \\
\text{or} \\
(O-M) = 3(A-M)
\end{align*}
$$
### Merits of Mode
1. Easiest to calculate and understand
2. Not affected by extreme values
3. It can be calculated for class interval with unequal width
### Demerits
1. Data can have more than one mode
2. It does not utilize all the observations
3. It is greatly affected by simple fluctuations

# Geometric Mean
### For ungrouped data:
$$
\text{GM} = \text{Antilog}\left(\frac{\sum\limits_{i=1}^{n}log(x_{i})}{n}\right)
$$
### For grouped data:

$$
\text{GM} = \text{Antilog}\left(\frac{\sum\limits_{i=1}^{n}f_{i} \ log(x_{i})}{\sum\limits_{i=1}^{n}f_{i}}\right)
$$

### Merits
- It utilizes all the observations
- If we have two data sets:
$$
\text{GM} = \frac{n\cdot GM_{1} + m\cdot GM_{2}}{n+m}
$$
- It gives more weight to small values
### Demerits
- Difficult to understand and compute
- If any value is zero, then the GM = 0

# Harmonic Mean

### For ungrouped data
$$
\text{HM} = \frac{n}{\frac{1}{x_{1}} + \frac{1}{x_{2}} + \dots + \frac{1}{x_{n}}}
$$
### For grouped data
$$
\text{HM} = \frac{N}{\frac{f_{1}}{x_{1}} + \frac{f_{2}}{x_{2}} + \dots + \frac{f_{n}}{x_{n}}} = \frac{N}{\sum\limits_{i=1}^{n}\frac{f_{i}}{x_{i}}}
$$
### Relationship between AM, GM, HM:
- $AM \geq GM \geq HM$
- $GM = \sqrt{AM\times HM}$

