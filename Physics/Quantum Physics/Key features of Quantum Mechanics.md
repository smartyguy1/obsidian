# Linearity of the equations of motion

In physics a theory is usually described by a set of equations for some 
quantities called the **Dynamical variables** of the theory. 

There are Linear theories and Non-Linear Theories. Non-linear theories are more complex than linear theories. In a Linear theory: If we have 2 solutions we can obtain a third solution of the theory by simply adding the first two solutions. For example in Maxwell's theory of electromagnetism, A simple solution describes an EM wave propagating in a given direction. Another simple solution could describe an EM wave propagating in a different direction. Since the theory is linear, another solution would be $E = E_{1}+E_2$ .

We say that Maxwell's equations are linear equations as a solution to Maxwell's equation is described by an electric field **E** a magnetic field **B**, a charge density $\rho$ and a current density **J**, all collectively denoted as $(\pmb{E},\pmb{B}, \rho, \pmb{J})$ is a solution and so is $(\alpha\pmb{E},\alpha\pmb{B}, \alpha\rho, \alpha\pmb{J})$ where all fields and sources have been multiplied by the constant $\alpha$.
Given two solutions: 
$$
(\pmb{E}_{1},\pmb{B}_{1},\rho_{1},\pmb{J}_{1}) \ \ \  \text{and} \ \ \ (\pmb{E}_{2},\pmb{B}_{2},\rho_{2},\pmb{J}_{2})
$$
Linearity also implies that we can Obtain a new solution by simply adding them:
$$
(\pmb{E}_{1}+\pmb{E}_{2}, \ \pmb{B}_{1}+\pmb{B}_{2},\  \rho_{1}+\rho_{2}, \ \pmb{J}_{1}+\pmb{J}_{2})
$$
The new solution is called the **Superposition** of the original two solutions.

## Linear set of equations
Consider the equation:
$$
Lu = 0
$$
Here, $u$ denotes the unknown. The unknown may be a number, or a functions of time, function of space. It could also represent a collection of unknowns, in which case we would replace $u$ by $u_{1}, \ u_{2} \dots$. And, $L$ denotes a **linear operator**, an object that satisfies the following two properties:
$$
L(u_{1}+u_{2}) = Lu_{1}+Lu_{2}, \ \ \ \ \ \ L(au) = aLu
$$
where $a$ is a number. Note that these conditions imply:
$$
L(\alpha u_{1}+\beta u_{2}) = \alpha Lu_{1}+\beta Lu_{2}
$$
showing that if $u_1$ is a solution($Lu_1=0$) and $u_{2}$ is a solution ($Lu_{2}=0$) then $\alpha u_{1}+\beta u_{2}$ is also a solution. We call $\alpha u_{1}+\beta u_{2}$ the **general superposition** of the solutions $u_1$ and $u_2$. 
For example:
$$
\frac{du}{dt}+ \frac{1}{\tau}u = 0
$$
where $\tau$ is a constant with units of time. This is, in fact a linear differential equation, and takes the form $Lu=0$ if we define$$
Lu \equiv \frac{du}{dt}+ \frac{1}{\tau}u
$$
Here we can take $L = \frac{d}{dt}+ \frac{1}{\tau}$ . Now 
$$
L(au) = a \frac{du}{dt} + \frac{a}{\tau}u = aLu 
$$
Thus, The given equation is Linear.

Classical mechanics, as invented by Issac Newton, is also a non-Linear Theory. In classical mechanics the dynamical variables are positions and velocities of particles, acted by forces. There is no general way to use two solutions to build a third.
Eg: consider the equation of motion for a particle under the influence of a time dependent potential $V(x)$, which is in general an arbitrary function of $x$, The dynamical variable in this problem is $x(t)$, the position as a function of time. Letting $V'$ denote the derivative of $V$ with respect to its argument, Newton's second law takes the form
$$
\begin{equation}
m \frac{d^{2}x(t)}{dt^{2}} = -V'(x(t))
\end{equation} 
$$

The left-hand side is $ma$ and the RHS is the force experienced by the particel in the potential. Note that $$\left. V'(x(t)) \equiv \frac{\partial V(X)}{\partial x}\right|_{x=x(t)}$$
The reason the equation is not linear is that the function $V'(x)$ is not linear. In general for arbitrary functions $u$ and $v$ we expect
$$
V'(au) \neq aV'(u), \ \ \ V'(u+v) \neq V'(u) + V'(v)
$$
## Wave function

Quantum mechanics is a linear theory. The signature equation in this theory, the so-called Schrodinger equation is a linear equation for a quantity called the **wavefunction** and it determines its time evolution. The wavefunction encodes probabilities. 
The wavefunction $\Psi$ depends on time and may also depend on space. The Schrodinger equation (SE) is a *partial differential* equation that takes the form:
$$
i\hbar \frac{\partial \Psi}{\partial t} = \hat{H}\Psi
$$
where the Hamiltonian (or energy operator) $\hat{H}$ is a linear operator that can act on wavefuntions:
$$
\hat{H}(a\Psi) = a\hat{H}\Psi . \ \ \ \ \ \hat{H}(\Psi_{1}+\Psi_{2}) = \hat{H}(\Psi_{1}) + \hat{H}(\Psi_{2})
$$
Where $a$ is a constant that **need not be real**.
Since it is a linear equation: if $\Psi_1$ and $\Psi_2$  are solutions to the Schrodinger equation, then so is the superposition $\alpha \Psi_{1}+\beta \Psi{2}$, where $\alpha$, $\beta$ $\in \mathbb{C}$.  

# Necessity of Complex Numbers
Quantum Mechanics is the first physics theory that truly makes use of complex numbers. Some important properties of complex numbers are:
1. $\text{Re}(z) = a, \ \ \ \ \text{Im}(z)=b$
2. $\text{if} \ z = a+ib, \ \ \bar{z} \ \text{or} \ z^{*} = a-ib$. Here, $\bar{z}$ or $z^*$ is known as the complex conjugate
3. $|z| = \sqrt{a^{2}+b^{2}}$  
4. $|z|^{2}=zz^{*}$ 
## Euler's Identity:
$$
e^{i\theta}= \cos{\theta} +i\sin{\theta}
$$
Complex numbers with $|z|=1$ can be represented by this identity while other complex numbers can be represented by $|z|e^{i\theta}$.

In Quantum Mechanics, Complex Numbers are fundamental. The Schrodinger equation involves complex numbers and the wavefunction(the dynamical variable for quantum mechanics) is itself a complex number:
$$
\Psi \in \mathbb{C}
$$
# Loss of Determinism
Einstein implied in his theory that light was made up of particles, each carrying a fixed amount of energy. However, the photon is **not** like a Newtonian corpuscle, which is a zero-size object with definite position and velocity.
Energy of the photon depends on its frequency:
$$
E = h\nu
$$
The frequency determines the wavelength: $\nu\lambda = c$, where $c$ us the speed of light. 

However, the existence of photons implies that Quantum Mechanics is not deterministic. (i.e. The results of an experiment cannot be determined, as it would in classical physics, by the conditions that are controlled by the experimenter.)

Consider a polarizer whose preferential direction is aligned along the $\hat{x}$ direction. Light that is linearly polarized along the $\hat{x}$ direction (i.e. light whose electrical field points in this direction goes through the polarizer). If the incident light polarization is orthogonal to the $\pmb{\hat{x}}$ direction the light will not go through at all. Thus light polarized along the $\pmb{\hat{y}}$  direction will be totally absorbed by the polarizer.
![[Pasted image 20240804162014.png|400]]

Now let us think of a beam of light polarized along a direction forming an angle $\alpha$ with the x-axis:
![[Pasted image 20240804162436.png|400]]
Thinking of light as a propagating wave, the incident electric field $\pmb{E}_{\alpha}$ makes an angle $\alpha$ with the $x$-axis. Therefore,
$$
\pmb{E}_{\alpha}=E_{0}\cos{\alpha}\pmb{\hat{x}}+E_{0}\sin{\alpha}\pmb{\hat{y}}
$$
*We are ignoring the time and space dependency of the wave; they are not relevant to our discussion.*
When this electric field hits the polarizer, the component along the $\pmb{\hat{x}}$ goes through and the component along $\pmb{\hat{y}}$ gets absorbed. Thus,
$$
\text{Beyond the polarizer:} \ \ \ \pmb{E} = E_{0}\cos{\alpha}\pmb{\hat{x}} 
$$
We may recall that energy of  EM wave is identical and equal to $(\cos{\alpha})^{2}$ times the energy. Consequently $1-(\cos{\alpha})^2$ of the photons must be absorbed. But if all the photons are identical why are some absorbed while some are let through?

The answer in quantum mechanics is that there is indeed a loss of determinism. No one can predict if a photon will go through or not. The best anyone can do is predict probabilities. In this case there would be a probability $(\cos{\alpha})^2$ of going through and $1-(\cos{\alpha})^2$ of failing to go through.

When we describe photons quantum mechanically we could use wavefunctions, or equivalently language of states. A photon polarized along the $\pmb{\hat{x}}$ direction is not represented using an electric field, but rather we just give a name for its *state*:
$$
\ket{\text{photon}; x}
$$
We can think of these objects like vectors in some space yet to be defined. Another sate of a photon or vector is:
$$
\ket{\text{photon}; y}
$$
representing a photon polarized along $\pmb{\hat{y}}$. These sates are the wave functions that represent the photon.

We now claim that the photons in the beam that is polarized along the direction $\alpha$ are in a state $\ket{\text{photon}; \alpha}$ that can be written as a superposition of the above two states:
$$
\ket{\text{photon}; \alpha}  = \cos{\alpha}\ket{\text{photon};x} + \sin{\alpha}\ket{\text{photon};y}
$$
This equation can be compared with the electric-field equation. While similar-both are superpositions - one refers to electric fields and the other to "states" of a single photon. Any photon that emerges from the polarizer will necessarily be polarized in the $\pmb{\hat{x}}$ direction and therefore it will be in the state
$$
\text{beyond the polarizer: } \ \ \ket{\text{photon}; x}
$$

# Quantum Superpositions
An interesting example is provided by a Mach-Zehnder interferometer; an arrangement of beam splitters, mirrors, and detectors used by Ernst Mach and Ludwig Zehnder in the 1890's to study the interference between two beams of light.
![[Pasted image 20240804175638.png]]

A beam-splitter, splits an incident beam into two beams, one that is reflected from the splitter and one that goes through the splitter.  The light that bounces off is called the *reflected beam* and the light that goes through is called the *transmitted beam*. The incident beam can hit the beam splitter from the top or form the bottom.

The Mach-Zehnder configuration has a left beam splitter (BS1) and a right beam splitter (BS2). In between we have two mirrors, M1 on top and M2 on the bottom. An incoming beam from the left is split by BS1 into two beams, each of which hits a mirror and is then sent into BS2. At BS2 the beams are recombined and sent into two outgoing beams that go into photon detectors D0 and D1.

Note that we have 2 beams incident on BS2, the top beam is called 'a' and the lower beam is called 'b'. Two contributions go towards D0; the reflection of 'a' at BS2 and the transmission from 'b' at BS2. These two contributions interfere constructively to give a beam going into D0.

Two contributions also go towards D1: the transmission from 'a' at BS2 and the reflection from 'b' at BS2. These two can indeed be arranged to interfere destructively to give no beam going into D1.
Think of the incoming beam as a sequence of photons that we send into the interferometer, one photon at a time. This shows that, at the level of photons, the interference is not interference of one photon with another photon. ==Each photon must interfere with itself to give the result.== Indeed interference between two photons is not possible: destructive interference, for example, would require two photons to give no photon which is impossible by energy conservation.

**Therefore, each photon does the very strange thing of going through both branches of the interferometer. Each photon is in a *superposition* of two states: a state in which the photon is in the upper beam added to a state in which the photon is in the lower beam. Thus, the state of the photon in the interferometer is a funny state in which the photon seems to be doing two incompatible things at the same time.**

When we speak of a wavefunction, we also sometimes call it a state, because the wavefunction specifies the "state" of our quantum system. We also sometimes refer to states as vectors. A quantum state may not be a vector like the familiar vectors in 3-D but they are vectors because we can add states and multiply states by numbers. 
Just like vectors can be added, linearity guarantees that adding wavefunctions or states is a sensible thing to do. Just like how a vector can be written as a sum of other vectors we can do the same with states.

Consider now two state $\ket{A}$ and $\ket{B}$. Assume, in addition, that when measuring some property $Q$ in the state $\ket{A}$ the answer is always $a$ and when doing the same with $\ket{B}$ the answer is always $b$. Suppose now that out physical state $\ket{\Psi}$ is the superposition
$$
\ket{\Psi}=\alpha\ket{A} + \beta\ket{B}, \ \ \ \ \ \ \alpha,\beta \in \mathbb{C}
$$
A measurement of $Q$ will yield either $a$ or $b$. There is no certain answer, classical determinism is lost, but the answer is always one of these two and not an intermediate one. The coefficients $\alpha$ and $\beta$ affect the probabilities with which we may obtain two possible values. In fact,
$$
\begin{align}
\text{Probability}(a) = \frac{|\alpha|^{2}}{|\alpha|^{2}+|\beta|^{2}}, && 
\text{Probability}(b) = \frac{|\beta|^{2}}{|\alpha|^{2}+|\beta|^{2}0}
\end{align}
$$
In quantum mechanics one makes the following assumption: ==Superposing a state with itself doesn't change the physics, nor does it change the state in a non-trivial way.== Since superposing a state with itself simply changes the overall number multiplying it, we have that $\Psi$ and $\alpha\Psi$ represent the same physics for any complex number $\alpha$ different from zero. Thus, letting $\cong$ represent physical equivalence
$$
\ket{A}\cong 2\ket{A}\cong i \ket{A}\cong -\ket{A}
$$
This assumption is necessary to verify that the polarization of a photon state has the expected number of degrees of freedom. 

## Spin of electron and superposition

Once an axis is fixed, the electron has two and **only** two option: its rotation maybe **clockwise** or **counterclockwise** about the axis, but in both cases it spins at the same fixed rate. These are called *spin up* or *spin down* along the axis. The up and down refers to the direction of the angular momentum direction. According to quantum mechanics, and as verified by multiple experiments, ==the same possibilities, up or down, arise *whatever* axis we use to measure the spin of electron.==

Let us choose to describe our spinning electrons using the $z$-axis. One possible state: $\ket{\uparrow; z}$, spin up along the $z$-axis. The other state is $\ket{\downarrow;z}$ with an arrow pointing down, meaning this time spin down. If these two are possible realities, so ti would be the state $\ket{\Psi}$ representing the sum
$$
\ket{\Psi} = \ket{\uparrow;z}+\ket{\downarrow;z}
$$
The state $\ket{\Psi}$ is in a superposition of a spin up and a spin down state. This represents a state in which a measurement would result in two possible outcomes with equal probabilities. It would be found experimentally that if we took a large ensemble of electrons half of them would be $\ket{\uparrow;z}$ and the other half would be $\ket{\downarrow;z}$. There is no way to predict which option will be realized as we measure each electron. 
*We can imagine the electron in the above state to be in a different kind of existence where it is possible to be in both the states simultaneously.*
Once we measure the spin it takes one of the two values.

# Entanglement

Entangled states of two particles are those in which we can't speak separately of the state of each particle. The particles are bound to be together in a common state in which they are *entangled* with each other.

For eg: consider two non-interacting particles. Particle 1 could be in any of the states
$$
\{ \ket{u_{1}},\ket{u_{2}},\dots\}
$$
while particle 2 could be in any of the states
$$
\{\ket{v_{1}}, \ket{v_{2}}, \dots\}
$$
It may seem reasonable to conclude that the state of the full system would by specified by stating the state of particle 1 and particle 2. If that would be the case, the possible states would be written as
$$
\ket{u_{i}} \otimes \ket{v_{j}}, \ \ \ i,j\in \mathbb{N} \tag{1}
$$
for some specific choice of $i$ and $j$ that specify the state of the particle one and particle two, respectively. Here, we used $\otimes$, meaning the *tensor* product, to combine the the two states into a single state for the whole system. 
The tensor product obeys the simple rule ,
$$
\begin{align}
(\alpha_{1}\ket{u_{1}}+\alpha_{2}\ket{u_{2}}) \otimes (\beta_{1}\ket{v_{1}}+\beta_{2}\ket{v_{2}}) &= \alpha_{1}\beta_{2}\ket{u_{1}}\otimes\ket{v_{1}} + \alpha_{1}\beta_{2}\ket{u_{1}}\otimes\ket{v_{2}}\\
&+\alpha_{2}\beta_{1}\ket{u_{2}}\otimes \ket{v_{1}}+\alpha_{2}\beta_{2}\ket{u_{2}}\otimes\ket{v_{2}} \tag{2}
\end{align}
$$

The **numbers** can be moved across the $\otimes$ but the **order of states** must be **preserved**. The state on the LHS -expanded out in RHS- is still the type where we combine a state of the first particle $(\alpha_{1}\ket{u_{1}}+\alpha_{2}\ket{u_{2}})$ with a state of the second particle $(\beta_{1}\ket{v_{1}}+\beta_{2}\ket{v_{2}})$, this state is **not entangled**.

Using the state in $(1)$ we can construct intriguing superpositions. Consider 
$$
\ket{u_{1}}\otimes\ket{v_{1}}+\ket{u_{2}}\otimes\ket{v_{2}} \tag{3}
$$
==A state of two particles is said to be **entangled** if it cannot be written in the factorized form $(\dots)\otimes(\dots)$ which allows us to describe the state by simply stating the state of each particle.==
It can be seen that $(3)$ cannot be factorized. If it could it would have to be with a product as indicated in $(2)$. For that to be true the constants would give:
$$
\begin{align}
\alpha_{1}\beta_{1}=1, && \alpha_{1}\beta_{2}=0, && \alpha_{2}\beta_{1} = 0, && \alpha_{2}\beta_{2}=1 \tag{4}
\end{align}
$$
It is clear that there is no solution here. This confirms that the state $(3)$ is indeed an entangled state.

For example, consider the entangled state,
$$
\ket{\uparrow}\otimes\ket{\downarrow} + \ket{\downarrow}\otimes\ket{\uparrow}
$$
This shows two possible states of a pair of electrons.



