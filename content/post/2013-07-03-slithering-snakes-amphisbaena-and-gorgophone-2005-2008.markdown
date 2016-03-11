---
author: jarvistmoorefrost
comments: true
date: 2013-07-03 14:31:37+00:00
layout: post
slug: slithering-snakes-amphisbaena-and-gorgophone-2005-2008
title: Slithering Snakes; Amphisbaena and Gorgophone (2005...2008)
wordpress_id: 130
tags:
- c
- monte-carlo
- reptate
- snakes
---

[![Image](http://jarvistmoorefrost.files.wordpress.com/2013/07/attrac_annealed_short_hop1.png?w=490)](http://jarvistmoorefrost.files.wordpress.com/2013/07/attrac_annealed_short_hop1.png)

I finally got around to (minimally) cleaning up my code from the [2006 Nanoletters paper](http://dx.doi.org/10.1021/nl0608386) and put it up on github ([https://github.com/jarvist/Amphisbaena](https://github.com/jarvist/Amphisbaena)). This simulates coarse-grain on-lattice morphology generation of polymers via a slithering snakes / reptation model [amphisbaena], and then also enables you to carry out mobility simulations via Time of Flight (ToF), drift velocity or diffusion [gorgophone].

It's coded in C and is rather sneaky in some ways (have a look at the oroboros data structure!), and rather ugly in other ways (hand unrolled loops, switches rather than ifs, recompile to change experimental parameters, hard coded colour codes for the terminal) to get maximal performance.

May your snakes reptate in a manner truly divine.

[![Image](http://jarvistmoorefrost.files.wordpress.com/2013/07/console.jpg?w=650)](http://jarvistmoorefrost.files.wordpress.com/2013/07/console.jpg)
