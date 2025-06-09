
# Asymptotes

Tangent line:$$tan(\Psi) = \frac{dy}{dx}= f'(x)$$
Asymptotes are the tangent line which touch the curve at only **infinity**.

![[M-2.1.excalidraw]]

$f(x) = y = \frac{1}{x}$ and $x \to \infty, \ y\to0$ the line which touches the curve at $\infty$.

## Types of Asymptotes
#### Parallel to x-axis:
>Equate the coefficients of highest power of $x$ with 0.

Example: $f(x,y) = x^{3}y+3x^{3}y^{2}+5xy^{3}+3x^{2}y^{2}+2$ 
$$
\text{Coefficient of highest power of x: } x^{3}\to y+3 y^{2}=0
$$
$$
y(1+3y) = 0 \ \implies (y=0) \text{ or } (y=\frac{-1}{3})
$$
#### Parallel to y-axis:
>Get coefficients of highest power of $y$ and then equate with zero.

From the earlier equation:
$$
5x^{2}=0 \implies x=0,0
$$

#### Oblique Asymptotes
> Not parallel to any axis

Example: $f(x,y) = x^{3}y+3x^{3}y^{2}+5xy^{3}+3x^{2}y^{2}+2$ 
General equation of line : $y=mx+c$ 
**Step-1:** $\phi_n$ is the sum of the highest degree terms in the equation. Then put $x=1 \ \text{and } y=m$.
$$
\begin{align*}
\phi_{n}&= 3x^{3}y^{2}+5x^{2}y^{3}\\
&= 3m^{2}+5m^{3}
\end{align*}
$$
**Step-2**: 
Solve $\phi_{n}(m)=0$ $\implies m^{2}(3+5m)=0$
$m=0,0,\frac{-3}{5}$ 

**Step-3:** Similarly find $\phi_{n-1}$ , $\phi_{n-2}$...
> If $\phi_{n}$ has no repeated roots, then $c = \frac{-\phi_{n-1}}{\phi'_{n}}$ 

 > If it has repeated roots (suppose $3$), then solve
 > $\frac{c^{3}}{3!}\phi'''_{n}(m) + \frac{c^{2}}{(2)!}\phi''_{n-1}(m) + \frac{c}{1!}\phi'_{n-2}(m) + \phi_{n-3}(m) = 0$ 
 > 
 