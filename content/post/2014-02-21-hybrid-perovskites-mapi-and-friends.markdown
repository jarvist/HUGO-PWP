---
author: jarvistmoorefrost
comments: true
date: 2014-02-21 12:07:54+00:00
layout: post
slug: hybrid-perovskites-mapi-and-friends
title: Hybrid perovskites (MAPI and friends)
wordpress_id: 294
tags:
- arxiv
- literature
- mapi
- monte-carlo
- perovskite
---

Our fairly prospective paper is out to review with Nano Letters at the moment, the preprint has just gone live on the arXiv. There's a massive range of calculations presented in quite a short paper - from GSGW (MvS), periodic plane wave DFT (FB) & CCSD quantum chemical calculations (JMF) to classical electrostatic calculations (JMF). We make suggestions as the to the likely effect of these results on device operation, and route for degradation in the presence of water via the Grotthuss mechanism (CH) (and the suggestion that an aprotic cation should alleviate this).

"Atomistic origins of high-performance in hybrid halide perovskite solar cells" - [http://arxiv.org/abs/1402.4980](http://arxiv.org/abs/1402.4980)

We are also pooling our group literature survey in a Mendeley group. If you are new to Hybrid Perovskites, this might be a good place to look for papers to read (and clickable links!). Some really quite interesting papers have been found stashed away in the SIs of papers. One issue we've had in searching the older literature is what to call these perovskites. 'Hybrid perovskite' is the modern moniker whereas 'ammonium chlorostannate' is how Wyckoff refers to the tin analogue in the 20s, and searching by chemical formula usually confuses & fails for old scanned papers.

[https://www.mendeley.com/groups/4178551/hybrid-perovskite-solar-cells/](https://www.mendeley.com/groups/4178551/hybrid-perovskite-solar-cells/)

What next? Well - there's always more to try and understand! With have a hypothesised mechanism generating built-in fields which may explain the observed hysteresis in JV curve measuring, an on-lattice Monte Carlo code (written in C, and parameterised with enthalpies from DFT) that outputs pictures in a pleasingly 1970s palette. This is already generating qualitatively sensible temperature-dependent behaviour, now we need to figure out our prefactors (in typical physics way, everything is internally in units of kBT, dropping all the _ε_0 terms).

Most of all I really think that this field is being held back by the lack of good basic characterisation data. Capacitances, dielectric constants, doping concentrations - all this basic stuff still needs to be done (or at least published!). I appreciate that the material isn't that stable, but I just don't understand why after several years there isn't more data out there (to be fair a lot of the interpretation really needs planar junctions - a recent development). I do wonder there's too much focus on chasing the Power-Conversion-Efficiency dragon, and too little focus on the bread and butter understanding of the material properties. Which is a pity, as they seem quite puzzling.

![](https://lh4.googleusercontent.com/TNk24pQxTqmKs-RR84ky35G4DRe_TQ8xIsd4KRLNOTOzNb_pBO1WoK6OXV_XYKlMnw_AbpMhBcA1niYXX8iXlLujFTasmcLAttDnuWtnr6Gl_TtP4b33SNGklysO)
