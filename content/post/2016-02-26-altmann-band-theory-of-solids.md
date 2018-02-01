---
author: jarvistmoorefrost 
comments: true
date: 2016-02-26 10:29:00+00:00
layout: post
title: Altmann's Band Theory of Solids 
tags: [bookreview]
---

Band Theory of Solids: An Introduction from the Point of View of Symmetry
Simon L. Altmann
Clarendon Press, 1994

This is a fairly esoteric publication. The stated intent was to provide an introductory (I guess suitable for an undergraduate course) book on solid state theory, that none the less contained a strong dose of group theory from the get go. This is an interesting idea, but I'd say that it's only partially successful. Much of the behaviour we see in solid state arises directly from the symmetry, the nomenclature of group theory allows you to make sense and describe what's going on. 
In this book, to keep things succinct,  the groups and group theory are kept as minimal as possible, while providing the mathematical machinery to attack genuine problems. So most of the time you are dealing with a 1D translation group, with six sites as crystal basis. For the most applied section, you get the FCC/BCC friends of Silicon.

Nevertheless, I was impressed with the range of applications that were found for the group theory. The first half of the book aims to demonstrate that: "the Brillouin zone is a graphical depiction of the irreducible representations of the space group of a crystal, and of the structure of their bases". This works really well, and I very much felt like I had been taught something. 
Reciprocal space was always a messy, fuzzy concept in my mind. At Undergraduate Physics level we only ever attacked it in 1D with free electrons, objects which swelled in volume within their Fermi sphere; the existence of band gaps and why they formed at zone boundaries was a fact of nature handed down from on high.

A careful and extremely information rich description of the Brillouin zone follows, and electron (and phonon) structure found therein is made, with a chapter then demonstrating these for metals and semiconductors. Introductory descriptions of how this feeds into our modern electronic structure methods then follows. The chapter on Phonons is extremely rich, with electron-phonon interaction, phonon drag; leading into Brillouin zone effects linked via Peierls instability through to Jahn Teller distortions. 

The penultimate chapter on Wannier functions and Lowdin orbitals was fantastic. The description was simple, and useful, with the explicit mathematics of how the equivalent functions and symmetric orthogonalisation was carried out. The final chapter describes impurities, and somehow takes the reader through an explicit Green's function solution in just a couple of pages.

There's a lot of information packed into a very small space in this book. The writing is not massively gripping, I often find a lot of the mathematical derivations lacked motivation, and you would often go around the houses for a couple of pages before arriving at the physical intuition. 

However, I really feel like I benefited from having read it cover to cover. It's often said that Mathematics is the art of simplifying things until you reach the general case. I found in reading this that I was having regular 'Oh, that's why...' moments with 'stamp collecting' features I'd known about, but puzzled over their origin before. 
(A trite example, but I now know why electronic structure codes only need to calculate for half the k-points you request, even when the unit cell lacks any symmetry. And also why Gamma-point only calculations run twice as fast with half the memory.)

I certainly wouldn't want this as my first solid state book. But certainly as a follow up to an undergraduate course, I highly recommend it. As an adjunct to those already working in electronic structure, who have traced band structures along the zone boundaries without being entirely certain what the magiz 'L','R' and 'X's meant, I think it fantastic.

Group theory in Condensed Matter has fallen somewhat out of vogue. Now that computers are so fast, the careful structuring of calculations to exploit every ounce of symmetry for reasons of computational efficiency is less useful.
However, the very nature of the true solution comes directly from these symmetries. Even when including disorder and broken symmetry, it's important to understand what the form the unperturbed solution would be.

