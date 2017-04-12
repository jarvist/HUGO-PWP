---
author: jarvistmoorefrost
comments: true
date: 2017-02-20 12:29:00+00:00
layout: post
title: Experimental measures of photovoltaic materials 
---

Starting my PhD in 2007, I spent many many years in seminar and conference
talks on Photovoltaics being confused by the enormous array of experimental
probes for photovoltaic materials. 
This is an attempt, stimulated (as always!) by questions from a student, to put
down a list of standard experimental photovoltaic (or other optoelectronic)
device characterisations. 

High energy theorists often ape Gell-Mann in describing solid-state physics as
the 'squalid-state'. Certainly there is an awful lot going on at once. 
This is reflected in the experimental probes, which are similarly diverse, and
though they are often supposedly measuring the same observable in the same
material, come to contradictory conclusions.

In terms of device physics, almost all measures are optical,
electrical or optical-electrical. 
This forms a rough hierachy of techniques which are applied sequentially to
a new material, as the purely optical probes can be done with 'a flect of
dust', whereas contacts requires another level of complexity. 

It only makes sense to start doing this on
relatively pure samples (i.e. whereas structural characterisation by X-Ray
Diffraction [XRD] just needs *some*  crystalline material).
Similarly short-time (picosecond) optical measures may need 99.99% materials,
whereas electrical measures (where the charges have to live for micro or
miliseconds) needs 99.999%+ pure materials.  

## 1 - pure optical / non contacted) 

**The key thing** to remember with optical characterisation is that even
a standard bench-top solid-state laser is *INCREDIBLY* bright. It's very easy
to do a measure at the equivalent of a million or a billion Suns.
This is well outside the regime where any solar cell (even under light
concentrator) will be operating, and this can massively change the photophysics
in operation. If the authors do not tell you what equivalent number of suns
they are at, try and calculate it yourself from the laser spot size, absorption
coefficient, laser intensity / pulse energy, etc. 
Experimentalists don't measure at such crazy intensities out of spite or
foolishness, but because they need to have sufficient signal-to-noise ratio
to measure a signal, i.e. the volume is turned right up to be able to hear it.   

* 'UV/Vis' (where does the material absorb?); better measures are with an integrating
sphere / total scattering, use of a scattering medium to get the SNR to find
the Bg; 
* Photoluminescence (PL) (once it absorbs, where does it emit?);
* Time-resolved PhotoLuminescence (TRPL) (what are the dynamics of this
  emission? --- note this often means sacrificing ability to resolve by energy of emission);
* 'quench-studies' (where you kill the light emission by adding an electron donor
/ acceptor to probe how long lived / mobile the excitons / generated charges
are); 
* Time-resolved Microwave Conductivity (TRMC) / time-resolved terahertz
spectroscopy - see changes in conductivity as a function of time, infer
mobility from estimating number of free charges; 
* Hall-effect measurement
(identify whether material is n or p type, and approximate doping), infer
mobility;
* work-functions via Cyclic voltammetry (in electrolyte, easy experiment) or
UPS/XPS + Band gap

## 2 - pure electrical - needs contacts, usually capable of injecting charges: 

* Mobility measures via: 
  * Field-Effect-Transistor (a semiconductor deposited on a patterned substrate), tends to overestimate mobility and only probe first few nm of material; 
  * Space Charge Limited Current (form a diode out of the device + push charge through it); 
* Kelvin Probe / Four-point probe (measures something ~akin~  to workfunction; and conductivity); 
* Shubnikov–de Haas (similar but different to Hall, less common)

## 3 - optoelectrical measurements - essential needs a device, contacted top and bottom: 

* Time of Flight (directly probes the bulk mobility, requires non-injecting contacts, the higher the mobility the larger the thickness of sample required - so it's mainly good for low mobility materials); 
* Transient-photo-voltage, Transient-photo-current (as a solar cell, what happens when you abruptly turn the light off); 
* Electro-luminescence (inject charges, look at frequency of light emitted. SNR is ~10^6 higher than PL, so you can look at emission from defect states / deep within gap);

## From the point of view of a new PV material, the ordered set of questions to answer are:
* Does it absorb? (Is it black? Where is the Bandgap?) --> UV/Vis, optical measures
* Once it absorbs, does it generate charges?  --> TRPL (emission beyond a ps indicates seperated charges then finding each other)
* These charges, can they get to the contacts? --> mobility measure; defect recombination rates
* Can we get charges in and out of the device? --> Workfunction measure
* Can we build a device architecture (injecting contacts, control of doping) --> Efficiency, and then all the actual device physics

A common and very unfortunate (for the science) situation is that editors and
reviewers obsess over the final bottom line of 'power conversion efficiency',
not wanting to publish even very good science if the particular devices used are not
world leading. Though arguably you do want a similar order of magnitude
efficiency, so that you know the same physics is present, this leads to the
perverse incentive of scientists being motivated to burn effort and time on
incremental improvements, and to neglect deep study of the underlying processes
and device physics from which true breakthroughs come.

