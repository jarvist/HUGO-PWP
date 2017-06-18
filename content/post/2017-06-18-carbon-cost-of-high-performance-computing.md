---
author: jarvistmoorefrost
comments: true
date: 2017-06-18 10:59:00+00:00
layout: post
title: Carbon cost of High Performance Computing 
categories: [computing]
---

ARCHER pulls 1.2 MW [1] to run it's 4920[1] compute nodes (each of which is 24 cores). That's just under 250 W power per node, 6kWhr of energy in 24hrs. A 24 hour computer job consumes 8.6 'kAU' in the internal compute units used for accounting.

So that's roughly 0.7 kwhr / kAU, or 700 kwhr / MAU. 

The UK electricity grid carbon intensity is roughly 400 g / kwhr averaged over the year. So that's 280 kg / MAU of calculation.

A relatively small research project doing hybrid calculations can easily consume 10s of MAU!

By comparison, an economy return flight from London to Boston (for Fall MRS) is 0.8 tons of CO2[2].

So flying London to Boston and back for Fall MRS, adds as much carbon to the atmosphere as 3 MAU of calculations on Archer.

Interestingly, if you were to have a 24-node server continuously running calculations, this adds to roughly 8.6 (kAU) * 365 = 3.1 MAU for the whole year. 

So my take home message was to be less concerned about the travel to
conferences to present my science, and more careful with spending HPC time
wisely!

[1] http://www.archer.ac.uk/about-archer/hardware/
[2] http://calculator.carbonfootprint.com/calculator.aspx?tab=3

