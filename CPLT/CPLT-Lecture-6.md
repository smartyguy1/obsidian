# Binary Arithmetic
It is the foundation of all digital systems in computer science.
### Binary Addition:
Binary addition is similar to decimal addition but it only involves two digits 0 and 1.
$$
\begin{align*}
0+0=0\\
0+1=1\\
1+0=1\\
1+1 =10 &&\text{ (Which is 0 with carry of 1)}
\end{align*}
$$
$$
\begin{align*}
1011\\
+1101\\
\hline11000
\end{align*}
$$
### Binary Subtraction
It also follows the rule as binary addition and only involved  two digits 0 and 1.
$$
\begin{align*}
0-0=0\\
1-0=1\\
1-1=0\\
0-1=1 &&\text{(borrow one from the nest significant bit)}
\end{align*}
$$

Eg
$$
\begin{align*}
1011\\
-110\\
\hline101
\end{align*}
$$
### Binary Multiplication
It is straightforward as it involves shifting and adding
$$
\begin{align*}
0 * 0&= 0\\
0*1&= 0 \\
1*0&= 0\\
1*1&= 1\\
\end{align*}
$$
Eg:
$$
\begin{align*}
101\\
*11\\
\hline101\\
101\times\\
\hline1111
\end{align*}
$$
### Binary Division
Also works like normal arithmetic division
Eg:
$$
\frac{101101}{101} = 1001
$$

### Negative numbers in Binary
Negative numbers in binary are typically represented using 2's complement notation.
**Step1**: Write the number in binary
**Step2**: Invert the digits (changes 0 to 1 and 1 to 0)
**Step3:** Add 1 to the result
$$
\begin{align*}
-8 \text{ (in binary 8 is given by 1000)}\\
\end{align*}
$$
Write it as a 8 bit number: $00001000 = 8$
1's complement: $00001000\rightarrow 11110111$
**2's complement(Adding 1 to the 1's complements):** 
$$
\begin{align*}
11110111\\
+1\\
\hline11111000
\end{align*}$$



