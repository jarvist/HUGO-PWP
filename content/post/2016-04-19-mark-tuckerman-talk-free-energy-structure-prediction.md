+++
date = "2016-04-19T14:44:34+00:00"
draft = false
title = "Mark Tuckerman talk: Free energy based structure prediction"
+++

Mark Tuckerman (MET) visited London on the 31st March 2016, and gave a highlight seminar
to the TYC at UCL. 
I had been really enjoying his recent (2010) Computational Stat Mech book [1]. 
I know very little about structure prediction, but it is of general and
captivating interest, and an essential step in truly predictive computational
materials science. 
Here are a summary of my notes from his talk, written up mainly for my own
reference, and for clickable citations. 

A point Mark made at the start and repeatedly was that we need to go beyond the
static structure picture - we need the entropic contribution, and we therefore
need to be able to calculate free energies. 

## Small molecular crystals

The first area discussed was predicting structure of small molecular crystals,
the example for them was having taken part in the CCDC Blind Test [2], but
focusing on a single molecule & attempting to explore the polymorphs. 
The motivation here is that for Pharma research, knowing the existence of
energetically accessible polymorphs is of utmost importance due to highly
varying bioavailability of different polymorphs. 

The method started off fairly standard. As general force fields are too coarse,
and quantum mechanical calculations too expensive, a customised force field was
developed. QC calculations on dimers were used to parameterise, with a fairly
normal `PBE0+TS; 6-311g**(d,p)`. 
Unit cells were generated with `UPACK`, a software package I had not heard of,
but which seems pretty extensive [3]. 

MD (I think just vanilla) on the packed structures lead to trajectories where
interconversion from one structure to another could be seen. Eventually they
settled down to 50 leftover structures, plotted on an energy vs. density plot. 
Their 4th lowest energy structure agreed with the 'blind' experimental
structure. 

So far so good for an interesting seminar, and a laudable result - but this is
where it got really interesting.

Mark linked from structure prediction to protein folding via a 2004 PNAS [4],
which proposed that both problems are essentially the same. 
In both cases you have a rough energy landscape, and you need to determine the
occupancy of the basins. 

## Collective variables

To do this, Mark suggests targeting collective variables - something that
distinguishes different conformal states. 
These are selected 'by hand' with 'insight' and 'chemical intuition' to fit the
problem studied.

* The most simple example are the Psi and Theta angles of the Ramachandran plot [5] for amino acid residues.
* For crystals you can take the unit cell vectors and stuff them into what Mark
referred to as the `h` matrix. 
* For packing, you can take angles and distances, or use `Q`, `W` Steinhardt
bond-order parameters. 
  * [Incidentally, I recently learned thanks to another seminar that these
    seemingly mystical parameters are really quite simple - they're just
    spherical harmonics!  You consider only even-l versions of these, making
    them invariant under inversion. [6] ]

## Temperature accelerated MD

Temperature accelerated MD was then introduced. 
Mark described it as essentially being an additional (standard) equation of
motion being simultaneously solved, in the collective variables. 
A very large fictitious mass is used for the collective-variable centre, and
a separate thermostat (~32000 K was an example). 
This means that the collective variables have the energy to hop potential
barriers between minima, and the momentum to smoothly move between them. 

I did not realise that temperature accelerated MD was this conceptually simple. 

Metadynamics is an alternative way to explore the free energy landscape, but
relies on the simulation dropping little Gaussians in the potential energy
where they are currently, so requires a certain amount of time to fill up the
basins and escape to the next one. To get the free energy, once you've filled
all the basins you invert the Gaussians and this gives you the free energy
surface. 

## Protein folding: Alanine Decamers between alpha helix and beta hairpin

Accelerated MD on this as a model system (I think with the CHARMM forcefield),
with the Ramachandran variables (20 collective variables).
Running this produces lots of structures, with the transition paths identified [10]. 
Using a Berendsen thermostat with added noise [7], defining a path as the
collective variable, you can integrate along to get free energy. 
This gives you a smooth energy along the coordinate, and thus a well found
value for the free energy difference. 

I found a 2014 YouTube video containing the MD, but the extraction of free
energy seems a bit different:
https://youtu.be/WKpe8fzATr4?t=21m38s

## Polymorphic benzene

Separately they studied polymorphs of benzene. 
The 'h' matrix (lattice basis) was explicitly evolved in the EoM, dragging
atoms instantly with it. 
With benzene at 100K (atomic thermostat) and 32000 K (collective variable
thermostat), 5 ns of MD was sufficient for all free energies, 0.5 ns of MD
found all the polymorphs. 

This is explored in [8], and MET references thereafter. 

## Melting Copper

Melting Cu, with collective variables on the diagonal of `h`; and
a Q4, Q6 spherical harmonic 'bond order'. 
The EAM potential was used.

Here they looked at classical nuclear theory. 
The simulations showed a more complex story - the hot solid had defects which
were highly mobile. Defects formed clusters to minimise their free energy

## Navigating on a high dimensional surface

You can't visualise the surface - it is too high in dimension. But you want to
see the 'interesting' minima and saddle points. 
You can use a Parrinello-group sketchmap [9], which appears to be a clustering
graph representation. 
Here [11] they used these ideas, and the `START` method where the free energy
gradient and the Hessian were constructed in terms of collective variables, to
give you the weakest eigenvector to walk along with steepest descents.

Some very recent and unpublished data investigated Anthracene crystals,
defining the Euler angles (though a later figure mentioned an 'absolute
quaternion') and cell parameters as collective variables. They found the
experimental structure, and loads of near-energy polymorphs

## Conclusion

It was an extremely thought provoking talk. The explanation of temperature
accelerated molecular dynamics was the first time that it made sense to me. 
The power of integrating the EoM for a collective variable & so ride roughshod 
across a rough potential energy landscape with the ability to extrapolate free
energies is clearly fantastically powerful.

However, I felt that everything presented seemed a little clunky. 
Certainly the science was fantastic, but every example seemed to have been set
up slightly differently and individually by the researchers. 
There was no mention of these codes or methods being made available. 

One thing obviously missing from a scientific point of view was a algorithmic
way to define the collective variables, rather than relying on intuition. 

In a paper I've been reading recently [12], the authors of VoroTop introduce
a method to identify local structure independent of radial distribution
functions and bond orders. Instead they define the 3D Voronoi cell for individual
atoms, and then compare the isomorphism (or not!) of the 2D Schlegel diagram
(i.e. a graph of connectivity of the Voronoi vertices) to identify
topologically distinct local bonding. 
I wonder if some ideas from here, could be borrowed and used to construct
collective variables automatically.

Once you can identify the collective variables automatically, the exploration
of rough potential energy surfaces, while retaining the free-energy of
structures, will be practically pleasant.

With a bit of Googling I found a Tuckerman slide deck from 2014 which
overlapped with this talk a fair bit:
http://conference.mipt.ru/img/conference/material-design-2014/talks/Hybertsen-talk.pdf

Mark has a Google Scholar page, for if you want to dig through more of his
literature [13].

## References

[1] Mark E. Tuckerman (2010), Statistical Mechanics: Theory and Molecular
Simulation. Oxford Graduate Texts.
(https://www.amazon.co.uk/Statistical-Mechanics-Molecular-Simulation-Graduate/dp/0198525265)

[2] https://www.ccdc.cam.ac.uk/Community/initiatives/cspblindtests/

[3] http://www.crystal.chem.uu.nl/~vaneyck/upack.html

[4] 
"Exercises in
prognostication: Crystal structures and protein folding". 
Jack D. Dunitz and Harold A. Scheraga (2004). 
PNAS 40(101),
14309-14311. http://dx.doi.org/10.1073/pnas.0405744101

[5] https://en.wikipedia.org/wiki/Ramachandran_plot

[6] "Bond-orientational order in liquids and glasses"
Paul J. Steinhardt, David R. Nelson, and Marco Ronchetti (1983). 
Phys. Rev. B 28, 784. 
http://dx.doi.org/10.1103/PhysRevB.28.784

[7] 
"Canonical sampling through velocity rescaling". 
Giovanni Bussi, Davide Donadio and Michele Parrinello (2007). 
J. Chem. Phys. 126, 014101 (2007); http://dx.doi.org/10.1063/1.2408420

[8] 
"Temperature-Accelerated Method for Exploring Polymorphism in Molecular Crystals Based on Free Energy"
Tang-Qing Yu and Mark E. Tuckerman (2011). 
Phys. Rev. Lett. 107, 015701; 
http://dx.doi.org/10.1103/PhysRevLett.107.015701

[9] 
"Simplifying the representation of complex free-energy landscapes using
sketch-map". 
Michele Ceriotti, Gareth A. Tribello, and Michele Parrinello (2011). 
PNAS 32(108), 13023-13028. 
http://dx.doi.org/10.1073/pnas.1108486108

[10] 
"Sampling saddle points on a free energy surface"
Amit Samanta, Ming Chen, Tang-Qing Yu, Mark Tuckerman and Weinan
J. Chem. Phys. 140, 164109 (2014); http://dx.doi.org/10.1063/1.4869980

[11] 
"Locating landmarks on high-dimensional free energy surfaces"
Ming Chen, Tang-Qing Yu, and Mark E. Tuckerman (2015).
PNAS vol. 112 no. 11 (2015); http://dx.doi.org/10.1073/pnas.1418241112

[12]
"Topological framework for local structure analysis in condensed matter"
Emanuel A. Lazar, Jian Han, and David J. Srolovitz (2015).
PNAS vol. 112 no. 43; http://dx.doi.org/10.1073/pnas.1505788112

[13] Mark E. Tuckerman, Google Scholar. 
https://scholar.google.co.uk/citations?hl=en&user=w_7furwAAAAJ&view_op=list_works&sortby=pubdate


