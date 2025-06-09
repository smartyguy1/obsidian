![[Pasted image 20240807162228.png|500]]
It contains two beam-splitters BS1 and BS2, and twi mirrors.

Vertical cuts in the above figure intersect the two beams and we can ask what is the probability to find a photon in each of the two beams at that cut. For this we need two probability *amplitudes* or two complex numbers, whose $|z|^{2}$ would give probabilities. We encode this info in a two-component vector as,
$$
\begin{pmatrix}\alpha \\ \beta\end{pmatrix} \tag{1}
$$
Here $\alpha$ is the probability amplitude to be in the *upper beam* and $\beta$ the probability amplitude to be in the *lower beam*. Therefore, $|\alpha|^2$  would be the probability of finding photon in upper beam while $|\beta|^2$ would be of finding a photon in the lower beam. Then we must have,
$$
|\alpha|^{2}+|\beta|^{2}=1\tag{2}
$$
Following the notation, We have the following cases:
$$
\begin{align*}
\text{photon on upper beam}: \begin{pmatrix}1\\ 0 \end{pmatrix} && 
\text{photon on lower beam}: \begin{pmatrix}0\\1\end{pmatrix} \tag{3}
\end{align*}
$$
We can view the state $(1)$ as a superposition of these two simpler states using the rules of vector addition and multiplication,
$$
\begin{pmatrix}\alpha \\ \beta\end{pmatrix} = \begin{pmatrix}\alpha \\ 0\end{pmatrix} + \begin{pmatrix}0 \\ \beta\end{pmatrix} = \alpha\begin{pmatrix}1 \\ 0\end{pmatrix} + \beta\begin{pmatrix}0\\1\end{pmatrix} \tag{4}
$$
In the interferometer there is also a '**Phase Shifter**'. A piece of material whose only effect is to multiply the probability amplitude by a fixed phase $e^{i\delta}$ with $\delta\in \mathbb{R}$.

![[Pasted image 20240807163858.png|300]]

If the incoming photon hits the BS from the top we consider it in the upper beam and if it hits from the bottom we say it is in the lower beam. The effect of the beam-splitter is to give an output for each of the two cases:
$$
\text{Left BS: } \begin{pmatrix}1\\0\end{pmatrix} \rightarrow \begin{pmatrix}s\\t\end{pmatrix}, \ \ \ \ \text{Right BS: }\begin{pmatrix}0\\1\end{pmatrix}\rightarrow \begin{pmatrix}u\\ v\end{pmatrix} \tag{5}
$$
As we can tell by the diagram, for the photon hitting from the above, $s$ may be though of as a reflection amplitude and $t$ as a transmission coefficient. Similarly, for the photon hitting from the bottom, $v$ as reflection and $u$ as transmission.
The numbers, $s,t,u,v$ by linearity characterize completely the beam splitter. They can be used to predict the output given any incident photon.![[Pasted image 20240807165454.png]]
An incident photon state $\begin{bmatrix}\alpha\\ \beta\end{bmatrix}$ would give
$$
\begin{bmatrix}\alpha \\ \beta\end{bmatrix} = \alpha\begin{bmatrix}1\\0\end{bmatrix}+\beta\begin{bmatrix}u\\ v\end{bmatrix}\rightarrow\alpha\begin{bmatrix}s\\ t\end{bmatrix}+\beta\begin{bmatrix}u\\ v\end{bmatrix} = \begin{bmatrix}\alpha s+\beta u \\\alpha t+\beta v\end{bmatrix} = \begin{bmatrix}s &u\\ t&v\end{bmatrix}\begin{bmatrix}\alpha \\ \beta\end{bmatrix} \tag{6}
$$
In summary we see that BS produces the following effect:
$$
\begin{bmatrix}\alpha \\ \beta\end{bmatrix}\rightarrow\begin{bmatrix}s & u \\ t & v\end{bmatrix}\begin{bmatrix}\alpha \\ \beta\end{bmatrix}  \tag{7}
$$
We can represent the action of a beam splitter as a matrix multiplication on the incoming wavefunction, with the $2\times2$ matrix:
$$
\begin{bmatrix}s & u \\ t & v\end{bmatrix} \tag{8}
$$
The constraints on $s,t,u,v$ are (since their norms are probabilities)
$$
\begin{align*}
|s|^{2}+|t|^{2}&= 1\\
|u|^{2}+|v|^{2}&= 1
\end{align*}
$$
The kind of beam splitters we use are called balanced, which means that reflection and transmission probabilities are the same. So all four constants must have equal norm-squared:
$$
|s|^{2}=|t|^{2}=|u|^{2}=|v|^{2}=\frac{1}{2}
$$
Let us try a guess for the values:
$$
\begin{bmatrix}s & u \\ t & v\end{bmatrix} = \begin{bmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}}& \frac{1}{\sqrt{2}}\end{bmatrix}
$$
This fails if acting on normalized wavefunctions (or column vectors) does not yield normalized wavefunctions. So we try with a couple wavefunctions
$$
\begin{bmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}}& \frac{1}{\sqrt{2}}\end{bmatrix}\begin{bmatrix}1\\0\end{bmatrix} = \begin{bmatrix} \frac{1}{\sqrt{2}}\\ \frac{1}{\sqrt{2}}\end{bmatrix}, \ \ \ \ \ \begin{bmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}}& \frac{1}{\sqrt{2}}\end{bmatrix}\begin{bmatrix} \frac{1}{\sqrt{2}}\\ \frac{1}{\sqrt{2}}\end{bmatrix} = \begin{bmatrix}1\\1\end{bmatrix}
$$
While the fist example works out the second does not, $|1|^{2}+|1|^{2}=2\neq1$.
This can be fixed by changing the sign of $v$.
$$
\begin{bmatrix}s & u \\ t & v\end{bmatrix}=\begin{bmatrix} \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}\end{bmatrix}= \frac{1}{\sqrt{2}}\begin{bmatrix}1 & 1 \\ 1 & -1\end{bmatrix} \tag{9}
$$
The total probability is what we expect $|\alpha|^{2}+|\beta|^{2}=1$. ==The $-$ sign of $v$ means that a photon incident from below, as it is reflected, will have its amplitude changed by a sign or equivalently a phase shift of $\pi$.==

A typical beam splitter consists of a glass plate with a reflective dielectric coating on one side. The refractive index of the coating is chosen to be intermediate b/w that of glass and that of air. A reflection causes a phase shift only when light encounters a material of higher refractive index. This is the case in the transition of air to coating, but not in the transition from glass to coating. The the beam splitter represented by $(9)$ would have its coating on the bottom side. Transmitted waves have no phase shift.

Another possibility for a beam splitter matrix is
$$
\frac{1}{\sqrt{2}}\begin{bmatrix}-1 & 1 \\ 1 & 1\end{bmatrix}
$$
which would be realized by a dielectric coating on the top side. It can be checked that Its action also conserves probability.

We will call the left beam-splitter BS1 and the right beam-splitter BS2 and their respective matrices will be
$$
\text{BS1: } \frac{1}{\sqrt{2}}\begin{bmatrix}-1 & 1 \\ 1 & 1\end{bmatrix},
\ \ \ 
\text{BS2: } \frac{1}{\sqrt{2}}\begin{bmatrix}1 & 1 \\ 1 & -1\end{bmatrix}
$$
The two beam splitter are combined to form the interferometer shown in the given figure.
![[Pasted image 20240807172837.png|400]]
If we now assume the input photon wavefunction $\begin{bmatrix}\alpha \\ \beta\end{bmatrix}$ from the left, the output wavefunction that goes into the detectors is obtained by acting first with the BS1 matrix and then with the BS2 matrix:
$$
\text{input: }\begin{bmatrix}\alpha \\ \beta\end{bmatrix} \ \ \text{output: } \frac{1}{\sqrt{2}}\begin{bmatrix}1 & 1 \\ 1 & -1\end{bmatrix} \frac{1}{\sqrt{2}}\begin{bmatrix}-1 & 1 \\ 1 & 1\end{bmatrix}\begin{bmatrix}\alpha \\ \beta\end{bmatrix} = \frac{1}{2}\begin{bmatrix}0 & 2\\-2 & 0\end{bmatrix}\begin{bmatrix}\alpha \\ \beta\end{bmatrix} = \begin{bmatrix}\beta \\ -\alpha\end{bmatrix}
$$
So, for any input photon state we can write immediately the output photon state the goes into the detectors.

If the input photon beam is $\begin{bmatrix}0\\1\end{bmatrix}$ the output from the interferometer is $\begin{bmatrix}1\\0\end{bmatrix}$, and therefore a photon will be detected at D0. This is shown in the following figure.
![[Pasted image 20240807174205.png]]
We can make a very simple table with the possible outcomes and their respective probabilities $P$.

| Outcome      | P   |
| ------------ | --- |
| Photon at D0 | 1   |
| Photon at D1 | 0   |
Now if we block the lower path as indicated in the following figure,
![[Pasted image 20240807174326.png||400]]
The input beam acted by BS1 gives,
$$
\frac{1}{\sqrt{2}}\begin{bmatrix}-1 & 1 \\ 1 & 1\end{bmatrix}\begin{bmatrix}0\\1\end{bmatrix} = \frac{1}{\sqrt{2}}\begin{bmatrix}1\\1\end{bmatrix}
$$
Then the lower branch is stopped, while the upper branch continues. The upper branch reaches BS2, and here the input is $\begin{bmatrix} \frac{1}{\sqrt{2}}\\0\end{bmatrix}$, because nothing is coming from the lower branch. We therefore get an output
$$
\frac{1}{\sqrt{2}}\begin{bmatrix}1 & 1 \\ 1 & -1\end{bmatrix}\begin{bmatrix} \frac{1}{\sqrt{2}}\\0\end{bmatrix} = \begin{bmatrix} \frac{1}{2}\\ \frac{1}{2}\end{bmatrix}
$$
In this experiment there are 3 possible outcomes: the photon can be absorbed by the block, or can go into any of the two detectors. 

| Outcome         | P             |
| --------------- | ------------- |
| Photon at block | $\frac{1}{2}$ |
| Photon at D0    | $\frac{1}{4}$ |
| Photon at D1    | $\frac{1}{4}$ |
It is noteworthy that before blocking the lower path we could not get a photon to D1. The probability to reach D1 is now $\frac{1}{4}$ and was increased by blocking a path.

![[interfero_n_interfer.pdf]]