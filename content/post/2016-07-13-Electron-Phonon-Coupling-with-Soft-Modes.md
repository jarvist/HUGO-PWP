+++
date = "2016-07-13T20:00:00+01:00"
draft = false
title = "Electron Phonon Coupling with Soft Modes"
+++

<!-- MathJax -->
<script type="text/javascript"
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

I've spent a lot of time over the last three years thinking about
electron-phonon coupling. Thinking, not doing, being the operative word, as
I've found the theory really quite a large mass to get my head around!

Recently I saw my way in to something that seemed vaguely useful and
interesting. I'd put together a 1D Time-Independent-Schr&ouml;dinger-Equation
solver, originally for my own amusement, then to show my second year Chemistry
tutees, then rebuilt for actual science. 
It's surprisingly easy - discretise space, place your potential energy on the
diagonal of a matrix, place a finite-difference approximation to the gradient
on the tridiagonal (the kinetic energy), and via an application of the
variational method this gives you a full set of eigenstates and eigenenergies
when you diagonalise the matrix. 

Seeing the workbook would be useful to follow the discussion in the rest of
this post:-
[iJuliaNotebook on Github](https://github.com/jarvist/Julia-SoftModeTISH-DeformationPotential/blob/master/iJulia-Notebooks/2016-06_SoftMAPIModes_TISH_electron_phonon_coupling.ipynb)

The same method is just as applicable to an electron in an electrostatic
potential, or a nuclear degree of freedom in the potential energy of
a material. 
If you have a harmonic potential, the resulting wavefunctions are Gaussian. 
The most simple anharmonic potential you can imagine, while still being even
(retaining inversion crystal symmetry) is the biquadratic Mexican Hat
\\(E(Q)=A.Q^2+B.Q^4\\).

With the Mexican Hat potential you get some important bits of undergraduate
quantum mechanics turning up. For instance, the isolated states in the two minima are
degenerate, but forced to adopt opposite parity forms by the Pauli exclusion
principle. 

So this is just in 1D, but we can consider this to be Q, a generalised reaction
coordinate within a Normal Mode of the motion of a material. 
These Normal Modes come from the eigen decomposition of the Dynamic Matrix (a
set of second-order force constants). 
These are what you get when within your favourite electronic structure package
you do a 'phonon' calculation in a periodic solid, or a 'frequency' calculation
in a molecule. 
These modes form an orthogonal set; they are implicitly separated (in the
harmonic limit) and so can be considered independently.

Our Mexican Hat potential is now a good model for a soft phonon mode, as seen
in a large class of materials, including important technological applications
in ferroelectrics. 
The potential energy surface can be recovered by walking along the normal
eigenmode associated with an 'imaginary' mode, the eigenvector pointing in the
direction of maximum curvature. I don't know how accurate this is for soft
phonon modes, the motion is large and you are going in a straight line in
a direction derived from the local curvature. 
The solution to this Schr&ouml;dinger equation is the nuclear wavefunction for
this normal mode. 

But how this does this relate to electron-phonon coupling? 
Most modern approaches to electron-phonon coupling are based on
density-functional-perturbation-theory. 
As a perturbation theory, this only holds true for small variations around the
equilibrium geometry, i.e. you assume the range of motion is small, that the
material is stiff. 
To evaluate coupling terms, you assume that the deformation
potential (how the electron energy varies as a function of distortion) is
quadratic, which allows the second order perturbation theory to pull out a well
defined value. 

Typically, the codes that calculate these parameters give up when detecting
a soft mode, giving a zero contribution. 
In some cases this is likely to be missing the largest contribution, where the
large range of motion of a soft mode makes up the majority electron phonon
coupling. 

So to try and calculate this parameter, let us start by making the
Born-Oppenheimer approximation of separating the full wavefunction \\(\Phi\\)
into a product of electron \\(\Psi\\) and nuclear \\(\chi\\) parts, within the
(assumed independent) normal mode we are interested in, Q. 

<div>
$$ \Phi(r,\,Q) = \Psi(r;\, Q) \, \chi(Q)$$
</div>

The nuclear \\(\chi\\) wavefunction depends only on the normal mode coordinate,
whereas the electron and full wavefunction depend (naturally!) on the electron
locations \\(r\\).

By solving the nuclear wavefunction in the manner above, for a potential energy
surface derived by mode following, we have a set of vibrational eigenstates
which we can populate with a Bose-Einstein distribution. The sum of the
\\(\Psi^2\\)
contributions (normalised) gives us a probability density function for the
nuclear coordinates in this normal mode, as a function of temperature.

The electronic structure we can solve (and offload all the pain of dealing with
the electrons!) by calculating, with the Born-Oppenheimer approximation (now
the frozen-phonon approximation), the
electron structure only along the same normal mode Q. 
You use your favourite code to generate \\(E_g(Q)\\), a deformation potential
along a phonon mode Q.
This includes all the electron-electron interaction (to which we can add by
including exact electron exchange, and other electron correlation contributions). 
By the assumptions used in perturbation electron-phonon calculations, you
expect this to be roughly quadratic around Q=0. 
Following symmetry, for most modes in most crystals, it should be an even
expansion around Q=0. 

This assumes that the nuclear wavefunction does not mix into the full
electron+nuclear wavefunction, which is likely to be correct if you are considering
low-frequency (i.e. soft) nuclear motions. 

We can then get back to the temperature resolved electron-phonon
coupling for this mode by calculating the following integral:

<div>
$$ E_g(T) = \left< \chi(Q,T) \,\rvert\, E_g(Q) \,\lvert\, \chi(Q,T) \right> $$
</div>

This is trivial to evaluate in 1D, it's just a matter of multiplying the
normalised probability density function for the Bose-Einstein occupied nuclear
wavefunction, by the deformation potential.

So that's grand. 
A seemingly new and very simple method to calculate electron-phonon couplings
of soft modes (of which there are many many important technological examples). 
The result is Temperature dependent, including the Zero Point Fluctuation. 
(The quantum mechanical vibrational ground state is very different to the
classical prediction.)

I am however much concerned by how easy it was, and that no one else seems to
have tried it yet! 

As a theory there are some nice features. 
It has full vibrational wavefunctions, albeit they are treated in a mean-field
way when the electron-phonon interaction is calculated by only considering the
nuclear-wavefunction-density. 
I would argue that by using a deformation-potential in Q, we are taking some kind of
zeroth-order approximation to the electron-phonon coupling. 
As the physical range of motion for a soft mode is large, this might be fairly accurate. 
For standard, harmonic, phonons, the contribution is tiny, and higher orders in
the electron-phonon interaction will dominate. 

A distinct drawback is that we're currently evaluating for just one arbitrary
location in the vibrational Brillouin-Zone of the material. There's an explicit
phase term (i.e. location in q-space) which is chosen to then generate
real-space distortions in Q to enable the calculation of the electronic
structure (and so both the electron deformation potential, and nuclear vibrational potential). 
It is well known that the electron-phonon interaction should be
integrated across the full Brillouin-Zone in both vibrational (q) and
electronic (k) phase space, and that convergence of this summation is nasty as
the electronic-phonon coupling is very spiky. 
I would argue that this method is still useful when you have a mode with
a known softness at one particular location in the Brillouin Zone; 
with Bose-Einstein statistics, this soft mode will end up extremely highly
populated at room temperature (i.e. it makes up the majority of the thermal
motion of the crystal).

I was slightly reassured  when reading this recent paper - Figure 4 seems to be
almost identical to what I am suggesting, just for a rather boring harmonic
example, and only considering the ground state, rather than a Bose-Einstein
ensemble. [Phys. Rev. B 92, 085137, 2015](http://dx.doi.org/10.1103/PhysRevB.92.085137)

So I'm very interested if anyone out there has any thoughts to the validity or
otherwise of the above method. Probably it's a terrible idea, guaranteed to
fail, or been done and discarded many years ago. 
I finish on a cheery quote:

>"The previous methods for calculating the electron-phonon matrix element in
>a metal are neither rigorously formulated nor satisfactory in their results. 
>From each method there is something to learn---usually that the method is
>unreliable in some important aspect." Ziman, 1960 'Electrons and Phonons',
>&sect; 5.7, page 197.

Useful references:
[Sham and Ziman, Solid State Physics Volume 15, 1963, Pages 221–298](http://dx.doi.org/10.1016/S0081-1947\(08\)60593-7)
