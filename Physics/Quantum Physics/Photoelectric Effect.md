
It was first observed by Heinrich Hertz in 1887. When polished metal plates are irradiated, he observed, they may emit electrons, then called "photo-electrons". The emitted electrons thus produce a *photoelectric current*. The key observations are:
- There is a threshold frequency $\nu_{0}$. Only for frequencies $\nu > \nu_{0}$ is there a photoelectric current. The frequency $\nu_{0}$ depends on the metal and the configuration of the atoms at the surface. It is also affected by inhomogenities.
- The magnitude of the photoelectric current is $\propto$ intensity of the light source.
- Energy of the photoelectrons is *independent* of the intensity of the light source.

Einstein explained the other effects by postulating that the energy in light is carried by discrete quanta (later called photons) with energy $h\nu$. Here $h$ is the **Planck's constant**, the constant used by Planck to produce a fit for the blackbody energy as a function of frequency.

A given material has a characteristic energy $W$, called the *work function*, which is the minimum energy required to eject an electron. This is not easily calculated because it is the result of an interaction of many electrons with the background of atom.

It is easily measured however, when the surface of the material is irradiated, electrons in the material absorb the energy of the incoming photons. If the energy imparted on the electrons by the absorption of a single photon is greater than the work function $W$, then the electron is ejected with kinetic energy 
$$
E_{e^{-1}} = \frac{1}{2}mv^{2}=h\nu - W= E_{\gamma}-W \tag{1}
$$
This equation explains the experimental features noted above, once we assume that the quanta act on individual electrons to eject them. The threshold frequency is defined by
$$
h \nu_{0}=W \tag{2}
$$
as it leads to an electron with zero energy. For $\nu > \nu_{0}$ the electrons will be ejected. Increasing the intensity of the light source increases the rate that photons arrive, which will increase the magnitude of the current, but will not change the energy of each incoming quanta.

Eq$^{n}$ $(2)$ allowed Einstein to make a prediction: ==The Kinetic Energy of the photoelectrons $\uparrow$es linearly with $\nu$.== This was confirmed experimentally by Millikan.

**Example:** Consider UV light with $\lambda = 290\text{nm}$ incident on a metal with $W=4.05eV$. What is the energy of the photo-electrons and what is its speed?
**Solution**:
$$
\hbar c = 197.33\ \text{MeV.fm}, \ \ \ \hbar = \frac{h}{2\pi}
$$
where $\text{MeV } = 10^{6}\text{ eV}$ and $\text{fm} = 10^{-15}\text{m}$. Let us use this to compute the photon energy.
$$
E_{\gamma}=h\nu= 2\pi\hbar \frac{c}{\lambda}= \frac{2\pi\cdot197.33\text{MeV.fm}}{290\times10^{-9}}= \frac{2\pi\cdot197.33}{290} \approx 4.28\text{ eV}
$$
and thus, 
$$
E_{e^{-}} = E_{\gamma}-W= 0.23\text{ eV}
$$
To compute the energy we set
$$
0.23\text{ eV} = \frac{1}{2}m_{e}v^{2}=\frac{1}{2}(m_{e}c^{2})\left(\frac{v}{c}\right)^{2}
$$
Recalling that $m_{e}c^{2} \simeq 511,000\text{ eV}$ one finds
$$
\frac{0.46}{511000}= \left(\frac{v}{c}\right)^{2}\rightarrow \ \frac{v}{c}=0.0009488
$$
With $c = 3 \times 10^{8}$ we finally get $v\simeq284.4\text{ Km/s}$.

**Units of h**:
$$
[h] = \left[\frac{E}{v}\right] = \frac{ML^{2}/T^2}{1/T} = L\cdot M \frac{L}T
$$
Therefore,
$$
[h] = [\pmb{r\times p}] = [\pmb{L}]
$$
==We see that $h$ has units of angular momentum!== Indeed for a spin one-half particle, the magnitude of the spin angular momentum is $\frac{1}{2}\hbar$ 

The result $[h]=[r][p]$ gives us a way to associate a length to any particle of a given mass $m$. Indeed, using speed of light we can construct $p=mc$. Then $l=\frac{h}{p}=\frac{h}{mc}$. This is the Compton Wavelength $l_{C}$ of a particle:
$$
\lambda_{C} = \frac{h}{mc}
$$Note that this length is independent of the velocity of the particle. The *de Broglie* wavelength of the particle uses the true momentum of the particle, not $mc$. Thus *Compton* and *de Broglie* wavelengths should not be confused.

It is possible to get some physical intuition for the Compton wavelength of a particle. We claim that *$\lambda_{C}$ is the wavelength of a photon whose energy is equal to the rest energy of the particle.* Indeed we would have
$$
mc^{2} = h\nu=h \frac{c}{\lambda}\rightarrow \lambda = \frac{h}{mc}
$$

Suppose we are trying to localize a point particle of mass $m$. If you use light, possible accuracy in the position of the particle is roughly the wavelength of the light. Once we use light with $\lambda<\lambda_{C}$ the photons carry more energy than the rest energy of the particle.
It is possible that the energy of the photons go into creating more particles of mass $m$, making it difficult, if impossible to localize the particle. ==The Compton wavelength is the length scale at which we need *relativistic quantum field theory* to take into account the possible processes of particle creation annihilation.== 

Let us calculate the Compton Wavelength of the electrons:
$$
\lambda C(e) = \frac{h}{m_{3}c}= \frac{2\pi\hbar c}{m_{e}c^{2}} = \frac{2\pi\cdot197.33\text{MeV.fm}}{0.511\text{ MeV}} = 2426\text{ fm} = 2.426\text{ pm}
$$

![[photoelectric.pdf]]