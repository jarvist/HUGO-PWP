---
author: jarvistmoorefrost
comments: true
date: 2015-05-22 21:03:00+00:00
layout: post
slug: embarrassing-embarrassingly-parallelism
title: Embarrassing embarrassingly parallel
wordpress_id: 444
---

I gave up OPENMP'ing my Monte Carlo code about a year ago. I was trying to do it at the level of MC moves, and there are massive issues here in that the different threads are trying to sample and update the same simulation space - leading to segfaults as the variables crash into one another.

One method I've seen used in the literature is domain decomposition - where each thread runs MC on a segment of the simulation volume. This is quite a headache to set up, and then you have issues about simultaneous updates, and the inability to exchange particles / states across the boundaries. All scary issues.

So I gave up. I am not a computer scientist. I could not understand even the terms of reference; Lambda calculus reductions and all that jazz. In Simon Peyton Jones' terms, "I am a worm."

I revisited it this evening, with the intention of seeing whether I could separate the thread of the random number generator at least. However, it instantaneously struct me what I should do. Each MC-move attempt calls 'site-energy' with the test move which has a set of for loops evaluating over nearby space (i.e. with a cutoff) to get a total energy change for the test move. 
The change in energy variable 'dE' is a natural reduction vector, none of this modifies the simulation volume, and in a production run where you are integrating out a large volume of space for accurate energies - the majority of computer time is spend in these for loops.

One: `#pragma omp parallel for reduction(+:dE)` before the start of the for-loop nest; and a recompile with `-fopenmp`, and it now maxes out the 4 hyperthreaded cores on my laptop.

Scaling will be more limited on bigger machines, and increase in speed will only be seen where this energy summation, rather than the single-core modifications to the simulation volume and random number generator, dominate the CPU required.

But still. Embarrassing embarrassingly parallel, because I could have and should have seen this a year ago!
