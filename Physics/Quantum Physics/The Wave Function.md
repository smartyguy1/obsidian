# Schrodinger Equation

In Quantum Mechanics we are concerned with the **wave function** $\Psi(x, t)$ which we get by solving the **Schrodinger Equation**:
$$
\boxed{i\hbar \frac{\partial\Psi}{\partial t} = -\frac{\hbar^{2}}{2m}\frac{\partial^{2}\Psi}{\partial x^{2}} + V\Psi}
$$
here, $\hbar = \frac{h}{2\pi} = 1.055 \times 10^{-34}\text{ J s}$.
==The Schrodinger equation plays an analogous role to Newton's second law==.
# Statistical Interpretation:

According to **Born's statistical interpretation**:
$$
\int_{a}^{b} |\Psi(x,t)|^{2} dx = \text{Probability of finding the particle between a and b}
$$
### Statistics:

In statistics, we have:
$$
\sum\limits_{j=0}^{\infty}P(j) = 1
$$
- **Most probable value:** $j$ for which $P(j)$ is maximum
- **Median**: $j$ for which $P(\text{getting less than }j) = P(\text{getting larger than } j)$ 
- **Average:** $\langle{j}\rangle = \sum\limits_{j=0}^{\infty}jP(j)$  It is also called the **Expectation value**.
- **Variance**: $\sigma^{2}=\langle(\Delta{j})^{2}\rangle$
- **Standard Deviation:** $\sigma = \sqrt{\langle{j^{2}}\rangle - \langle{j}\rangle^{2}}$ 
### Continuous Probability distribution

$$
\rho(x)\ dx = \text{Probability that particle lies between x and } (x+dx)
$$
$\rho(x)$ is called the **Probability Density**. 
So, the probability that $x$ lies between $a$ and $b$ :
$$
P_{ab} = \int_{a}^{b}\rho(x) \ dx
$$
The statistical formulas translate here as:
$$
\boxed{\int_{-\infty}^{+\infty} \rho(x) \ dx = 1}
$$
$$
\boxed{\langle{x}\rangle = \int_{-\infty}^{+\infty} x \rho(x) \ dx}
$$
$$
\boxed{\langle{f(x)}\rangle = \int_{-\infty}^{+\infty} f(x)\rho(x) \ dx}
$$
$$
\boxed{\sigma^{2} \equiv \langle(\Delta{x})^{2}\rangle = \langle x^{2}\rangle - \langle{x}\rangle^{2}}
$$
# Normalization
$$
\boxed{\int_{-\infty}^{+\infty}|\Psi(x,t)|^{2} \ dx = 1}
$$

