---
author: jarvistmoorefrost
comments: true
date: 2016-10-13 11:29:00+00:00
layout: post
title: Constrained geometry optimisation in Gaussian 
---

*Summary*: If you want to do a geometry relaxation around a constrained degree of
freedom (bond length, angle, dihedral, etc.) in Gaussian 09, you need two
'ModRedundant' specifications, one to `B`uild in the coordinate with the value
you set, the next to then `F`reeze this coordinate so that it is constrained
during the optimisation.

Here is an example for Biphenyl, setting the torsional angle to 90 degrees
(making the phenyls orthogonal).

```
#p opt=ModRedundant am1

Biphenyl ModRedundant - Minimalist working constrained optimisation

0 1
C                 -4.41584965    0.94482757    0.00000000
C                 -3.02068965    0.94482757    0.00000000
C                 -2.32315165    2.15257857    0.00000000
C                 -3.02080565    3.36108757   -0.00119900
C                 -4.41563065    3.36100957   -0.00167800
C                 -5.11323165    2.15280357   -0.00068200
H                 -4.96560865   -0.00748943    0.00045000
H                 -2.47118165   -0.00768543    0.00131500
H                 -2.47060565    4.31323057   -0.00125800
H                 -4.96575265    4.31329057   -0.00263100
H                 -6.21283565    2.15298657   -0.00086200
C                 -0.78315191    2.15269060    0.00088786
C                 -0.08606526    3.36121931    0.00088734
C                 -0.08548693    0.94501548    0.00335961
C                  1.30876256    3.36175187    0.00267704
H                 -0.63630428    4.31325796   -0.00061165
C                  1.30993941    0.94551682    0.00463341
H                 -0.63486990   -0.00759907    0.00399419
C                  2.00679196    2.15379382    0.00415373
H                  1.85833456    4.31416964    0.00249700
H                  1.85980667   -0.00681651    0.00652304
H                  3.10655225    2.15452197    0.00514924

2       3       12      13      =90.0       B
2       3       12      13      F

```

*Longer Version*:
Doing a constrained geometry optimisation is a common necessity when modelling
organic electronics. 
A particular occurrence is wanting to set the backbone-torsion (the dihedral) of
an oligomer fragment (representing a polymer). 
This can be due to the fact that structural measurements show a particular
packing motif, and you want to override the behaviour of your quantum
chemistry, or you are interested in studying something (transfer integral, HOMO
/ LUMO energy, potential energy) as a function of the rotation. 

The relevant `ModRedundant` part of the Gaussian manual
(http://www.gaussian.com/g_tech/g_ur/k_opt.htm) is at best confusing.

If you want a single job that scans along a coordinate, you can use `S` for
Scan. However, this has some issues: you end up with all the intermediate
geometries buried in a massive .log file; you can't parallelise the geometry
optimisations; you can get some weird effects from steric hindrance, so should
really do the scans in the two different directions to detect any 'clicking'. 

So being able to `F`reeze in a constraint is really useful, so that you can
then have a load of `.com` files named `000.com`, `010.com` etc. for the angle
along the coordinate. 
These are then trivial to use in further processing by i.e. something like
(https://github.com/jarvist/hpc-bin/blob/master/jkp_extract_geom.awk) to
extract all the optimised geometries into new `.com` files, to do single point
calculations.

So that's grand; from 2007 to 2012 I had been using `opt=ModRedundant` with
a single `Freeze` line after the atom specification, to do a constrained
geometry optimisation. 
Then sometime around `G09.B`, this stopped working! 
The jobs would run, but all geometries would optimise to their relaxed
configurations. 
I didn't really understand why this occurred; it was immensely frustrating. 
As a work-around I used the old versions of Gaussian to do geometry
optimisations.

My student was recently bitten by this bug (my fault - as I sent her one of my
'working' files from circa. 2008!). 
So we investigated properly, and eventually found out the reason. 
If you have a single `F` line such as:
```
2       3       12      13      =90.0       F
```
and then go and look for the relevant part in the output `.log` file, you will
find that the ModRedundant section echoes back:
```
The following ModRedundant input section has been read:
D       2       3      12      13 90.000 B
```

Wait a second - that's a B! I told you F!
So therein lies the rub. 
Gaussian, if you specify `F`reeze alongside specifying a value to set the
constrained coordinate to, it will silently rewrite this to `B`uild, and so set
that coordinate for the initial optimisation, but then relax away from that
coordinate. 
Previously a single line with `F` specifying the coordinate, set the
constraint, and froze it.

Another curiosity which I do not understand, is that you can't seem to do
a constrained geometry optimisation with a empirical potential (such as `UFF`)
in the above.  
Maybe it uses different optimisation routines (i.e. Cartesian)?

All in all, the new behaviour is perhaps more logical.  
Essentially Gaussian is now doing something different when encountering
undefined behaviour. 
Internally I would guess there's some absolute horror show of a series of
Fortran routines messing around with internal variables based on this flags,
rather than a sensible parser. 
It just always feels that when someone breaks something you had working
previously, that they are working against you!

