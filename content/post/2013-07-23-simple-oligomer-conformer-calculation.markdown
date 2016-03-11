---
author: jarvistmoorefrost
comments: true
date: 2013-07-23 14:48:13+00:00
layout: post
slug: simple-oligomer-conformer-calculation
title: 'Simple oligomer conformer calculation '
wordpress_id: 156
tags:
- confab
- gaussian
- openbabel
- quantumchemistry
- torsion
---

I was moaning to a PhD student in the group about the perennial issue of checking representative torsional conformers of oligomers. In this case it was the question about whether you'd see a large variation in oscillator strength (of a TDDFT calculation) if you change the conformation (we don't see a big variation in the energies of excited states, unless you break conjugation). This is a genuine issue as the potential energy barrier for these torsional variations are thermally accessible, and typically presents at least two local minima (head-tail and head-head), if not 4 minima (where the flat alignments are sterically hindered), so real polymers will be sampling at least some of these structures. As well as making comparison to experiment difficult without sampling the phase space, if you naively compare chemistries in whatever random configuration your optimised structure landed in, you may start to think there are systematic variations due to chemistry, which are actually just an artefact of your structural sampling.

Serendipitously I stumbled across [Noel O'Boyle's](http://baoilleach.blogspot.co.uk) [confab program that evening](http://www.jcheminf.com/content/3/1/8), and thought it sounded perfect! I build the [(older) standalone version](http://baoilleach.blogspot.co.uk/2011/03/confab-systematic-conformation.html), though it is now apparently integrated into the [development version of OpenBabel](http://baoilleach.blogspot.co.uk/2013/07/using-open-babel-to-package-chemistry.html).

Confab is designed to look for small variations (rotating methyl units & etc.) in biological molecules, but if you up the RMSD tolerance for something to be considered identical (from 0.5 to 1.5 A), you get a good sample of torsional freedom in an oligomer. Starting with a 6-thiophene Head-Tail b3lyp/6-31g* optimised structure from a DFT calculation , you quickly generate a set of oligomers with increasingly broken head-tail alignment. Notably the low energy Head-Tail conformer is identified as the first one (i.e. using confab to generate the lowest energy structure, will probably fix any broken conjugation you have, and locate the most representative structure), and the high energy Head-Head as the last.

[![Image](http://jarvistmoorefrost.files.wordpress.com/2013/07/limited_conformers.png?w=650)](http://jarvistmoorefrost.files.wordpress.com/2013/07/limited_conformers.png)

These structures are low energy within the MMFF94, but I believe it keeps all parameters other than the free torsions identified at their input structure values (i.e. you retain the optimised DFT bond lengths and angles). Therefore these would be a great starting point for further DFT geometry optimisations (the resulting conformers should only take a few steps of DFT to reach the low energy relaxed DFT structure).

However, I was interested in a qualitative answer as to whether these different conformers had different oscillator strengths, so took these geometries directly (via openbabel to split the sdf into many gaussian files, and a little script to put a sane header on each) to a Zindos calculation.

2.4417 eV 507.79 nm f=1.8101
2.2925 eV 540.82 nm f=1.7151
2.3277 eV 532.64 nm f=1.6967
2.2759 eV 544.77 nm f=1.5296
2.3493 eV 527.76 nm f=1.7850
2.4445 eV 507.19 nm f=1.6643
2.3586 eV 525.67 nm f=1.3219

So we have a mean transition energy of 2.4 +- 0.1 eV, with a mean oscillator strength of 1.6 +- 0.3 . Considerably more variance in oscillator strength (0.03 vs. 0.004!). Once we wait for the TD-DFT (b3lyp/6-31g* on the MMFF94 torsionally relaxed geoms), we have a mean transition of 2.6 +- 0.2 eV (variance 0.007), with mean oscillator strength 1.6 +- 0.3 (variance 0.03). Also note that the highest oscillator strength is for the 2/1 helix Head-Tail structure (the first, lowest energy structure), and the lowest oscillator strength is for the 'bent banana' Head-Head fully misaligned.

This little study backs up a general feeling that oscillator strength is more fragile c.f. excitation energy for bent / suboptimal structures, and suggests that care is required to check different conformers.

All in all, confab seems like a very nice way to check through different oligomer conformers, with no real extra work required than providing a 3D optimised geometry. I wish there was some way to get access to the energies it's calculated for these structures, I'm not sure whether confab outputs this however. From these data you could imagine calculating some kind of real-world abundance weighting using a Boltzmann distribution (though you'd need to carefully consider the degeneracy of the different micro states / conformers).

Files & shell scripts on figshare: [http://dx.doi.org/10.6084/m9.figshare.750677](http://dx.doi.org/10.6084/m9.figshare.750677)

[Confab - Systematic generation of diverse low-energy conformers](http://www.jcheminf.com/content/3/1/8) NM O'Boyle, T Vandermeersch, CJ Flynn, AR Maguire, GR Hutchison. _Journal of Cheminformatics_ 2011, **3:**8.
