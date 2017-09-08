---
author: jarvistmoorefrost
comments: true
date: 2017-09-08 14:29:00+00:00
layout: post
title: A note on Schultz 
categories: [maths]
---

<!-- MathJax -->
<script type="text/javascript"
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

## A note on Schultz

In Schultz1959 (https://doi.org/10.1103%2Fphysrev.116.526), a Feynman polaron
radius is defined from the Gaussian form of the Simple Harmonic Oscillator
specified by the Feynman solution to the polaron problem.

I rederived some of these results (and the key thing - figured out that a 0.44
'magic number' was actually 2/9, i.e. 0.4 recurring), and decided to put the info out there
somewhere. 
The core I've written up as LaTeX here:
https://github.com/jarvist/PolaronNotes

If I get time I may do some more work + put it on the ArXiv for a bit of
greater coverage.

However, I think maybe actually scans of a long-hand form would be more useful. 

Schultz uses a very early digital computer for these results. 
It's not obvious which results are analytic, and which numerical. 
(Some of this may be due to something displayed in the acknowledgements - 'Mrs.
Hannah Landsman for most of the numerical work'. If Schultz didn't actually do
the programming, he probably didn't realise what went in to it, when he came to
write this up!)
On careful reading, I think his Table I must be from numeric optimisation of
the v and w parameters, using the athermal Feynman variational statement. 
It would be well worth adding this construction to my codes (which currently
use a finite-temperature statement originally due to \=Osaka), and cross-check
these values.

https://github.com/jarvist/PolaronMobility.jl . 

