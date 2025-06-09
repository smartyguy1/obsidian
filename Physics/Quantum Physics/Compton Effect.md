# Compton Scattering

In relativity, the energy, momentum and rest mass of a particle are related by
$$
 \boxed{E^{2}-p^{2}c^{2}=m^{2}c^{4}} \tag{3}
$$
(Compare this with the classical equation $E=\frac{p^{2}}{2m}$) Of course one can also express the energy and momentum of the particle in terms of the velocity:
$$
E=\frac{mc^{2}}{\sqrt{1-(\frac{\nu}{c})^{2}}}, \ \ \pmb{p} = \frac{m\pmb{v}}{\sqrt{1- \frac{v^{2}}{c^{2}}}} \tag{4}, \ \ \pmb{m} = \frac{m}{\sqrt{1- \frac{v^{2}}{c^{2}}}}
$$
A particle that moves with the speed of light, like the photon, must have zero rest mass, otherwise its energy and momentum would be infinite due to the vanishing denominators. 
With the rest mass set to zero, $(3)$ gives the relation between photon energy $E_{\gamma}$ and photon momentum $p_{\gamma}$:
$$
E_{\gamma}=p_{\gamma}c
$$
Then, using  $\lambda\nu=c$, we reach
$$
p_{\gamma}= \frac{E_{\gamma}}{c}= \frac{h\nu}{c} = \frac{h}{\lambda}
$$
**Thompson Scattering:**
The classical counterpart to Compton scattering is the scattering of electromagnetic waves off free electrons, called *Thompson Scattering*. 
Here an EM wave is incident on an electron. 

The electric field of the wave shakes the electron which oscillates with the frequency of the incoming field. The electron oscillation produces a radiated field, of the same frequency as that of the incoming radiation. 

In classical Thomson scattering the *differential scattering cross section* is given by:
$$
\frac{d\sigma}{d\Omega}= \left(\frac{e^{2}}{mc^{2}}\right) \frac{1}{2}(1+\cos^2{\theta}).
$$
where $\theta$ is the angle between the incident and scattered wave, ==with the radiated energy at the same frequency as  the incoming light.==
The cross-section represents the the area that would extract from the incoming plane wave the amount of energy that is scattered by the electron. Indeed the quantity $\frac{e^{2}}{mc^{2}}$ is called the classical electron radius and it is about $2.8\text{ fm}$.

If we treat the light as photons, the elementary processes going on is a collision between two particles; an incoming photon and a roughly stationary electron. Two facts can be demonstrated:
- The photon cannot be absorbed by the electron. It is inconsistent with energy and momentum conservation
- The photon must lost some energy and thus the final photon wavelength $\lambda_{f}$ must be larger than the initial photon wavelength $\lambda_{i}$.

Indeed, Compton's observations did not agree with the predictions of Thompson scattering: ==the X-rays changed frequency after scattering==. A calculation using energy and momentum conservation shows that the change of wavelength is correlated with the angle between the scattered photon and the original photon.
$$
\boxed{\lambda_{f}=\lambda_{i} + \frac{h}{m_{e}c} (1-\cos{\theta}) = \lambda_{i} + l_{C}(1-\cos{\theta})}
$$
Note that appearance of the Compton wavelength of the electron, the particle the photon scatters off from. The maximum energy loss for the photon occurs at $\theta=\pi$, where
$$
\lambda_{f}=\lambda_{i} + 2\lambda_{C}
$$
The maximum possible change in wavelength is $2\lambda_{C}$. For $\theta=\frac{\pi}{2}$ the change of wavelength us exactly $l_{C}$
$$
\Delta\lambda = \lambda_{f}-\lambda_{i} = \lambda_{C}
$$
Compton's experiment used molybdenum X-rays with energy and wavelength
$$
E_{\gamma} \approx 17.5\text{ keV}, \ \ \ \ \ \lambda_{i} = 0.0709\text{ nm}
$$
incident on a carbon target. Placing the detector at an angle $\theta = 90\degree$ the plot of the intensity (or number of photons scattered) as a function of wavelength is shown in the given figure. One finds a peak for $\lambda_{f}=0.0731\text{ nm}$, but also a second peak at the original wavelength $\lambda_{i}=0.0709\text{ nm}$.

![[Pasted image 20240810171125.png]]

The peak at $\lambda_{f}$ is the expected one: $\lambda_{f}-\lambda_{i} \backsimeq 2.2 \text{ pm}$, which is about the Compton wavelength of $2.4\text{ pm}$. Given that the photons have energies of $17 KeV$ and the bound state energies of carbon are about $300\text{ eV}$, the expected  peak represents instances where the atom is ionized by the collision and it is a fine approximation to consider the ejected electrons. 

The peak at $\lambda_{i}$ represents a process in which an electron receives some momentum from the photon but still remains bound. This is not very unlikely: the typical momentum of a bound electron is actually comparable to the momentum of the photon. In this case, the photon scatters at $90\degree$ and the recoil momentum is carried by the whole atom. The relevant Compton wavelength is therefore that of the atom. Since the mass of the carbon atom is several thousands of times larger than the mass of the electron, the Compton wavelength of the atom is much smaller than the electron Compton wavelength and there should be no detectable change in the wavelength of the photon.

# Matter Waves
Light behaves as both a particle and a wave. This kind of behaviour is usually said to be a **duality**: the complete reality of the object is captured using *both* the wave and particle features of the object. The photon is a particle of energy $E_{\gamma}$, but has frequency $\nu$ which is a wave attribute, with $E=h\nu$. It is a particle with momentum $p_{\gamma}$ but it also has a $\lambda$, a wave attribute given by given by
$$
\lambda = \frac{h}{p_{\gamma}} \tag{5}
$$
Loise de Broglie proposed that the wave/particle duality of the photon was universal, and thus valid for matter particles too. In this way he conjectured the *wave nature of matter*. Inspired by $(5)$ de Broglie postulated that associated to a matter particle with momentum $p$ there is a plane wave of wavelength $\lambda$ given by
$$
\lambda= \frac{h}{p}
$$
This is a fully quantum property: if $h\rightarrow0$, then $\lambda\rightarrow0$, the particles have no wave properties. And exciting consequence of this is that matter particles can diffract and interfere.
In the famous Davisson-Germer experiment electrons strike a metal surface and one finds that at certain angles there are peaks in the intensity of the scattered electrons. The peaks showed the effect of constructive interference from scattering off the lattice of atoms in the metal, demonstrating the wave nature of the electrons. 

==The de Broglie wavelength can be calculated to estimate if quantum effects are important.== Consider for this purpose a particle of mass *m* and momentum *p* incident upon object of size *x*, as illustrated in figure 3. Let $\lambda= \frac{h}{p}$ denote the de Broglie wavelength of the particle. ==The wave nature of the particle is not important if $\lambda$ is much smaller than $x$.== Thus, the "classical approximation", in which wave effects are negligible, requires
$$
\text{Wave effects negligible: } \ \ \ \ \frac{\lambda}{x}<< 1
$$
Using $\lambda = \frac{h}{p}$, this yields a relation in which both sides have units of angular momentum,
$$
\text{Wave effects negligible: } \ \ \ \ xp >> h,
$$

![[Pasted image 20240810185613.png]]

==Classical behaviour is a subtle limit of quantum mechanics: a classical electromagnetic field requires a large number of photons.== Any state with an exact, fixed number of photons, even if large, is not classical however. Classical electromagnetic states are so-called coherent states, in which the number of photons fluctuates.

![[Compton-effect.pdf]]