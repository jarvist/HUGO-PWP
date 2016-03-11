---
author: jarvistmoorefrost
comments: true
date: 2015-04-26 16:15:52+00:00
layout: post
slug: organising-computational-job-workflow-as-you-go-freck
title: 'Organising computational job workflow, as you go: freck'
wordpress_id: 436
---

The workflow in computational materials modelling is often highly complex, and bespoke to the particular calculations you are doing. The flow is highly derivative (results of later jobs depend on work on prior jobs), but can also be quite chaotic and multiply branching. Unsurprisingly, your files easily end up very messy, with significant confusion about what steps were required to get to the present working setup.

Version control is an absolute godsend, being able to flow down the list settings changes is extremely useful, and then being able to simply open the Git archive on GitHub as a way of archiving your research data is fantastic. However, this still leaves problems to be solved - the main one is actually constructing the folder structure sensibly. (A lesser issue is that intermediate and binary files in electronic structure calculations can be enormous (>multi gigabyte) and so far too large for git.)

To aid this I've written a very lightweight shell script called 'freck' (to move swiftly or nimbly, an obsolete English word). Each time this is run in a working directory, it generates a folder named 0001-, 0002- etc. with a user-requested file name, and then moves all the present working files into that directory. It also saves a 'breadcrumb' file with information about when and where you are writing this. I would like it to also add information extracted from your present history (i.e. all the commands you have used to work on the data), but the problem is that the shell script runs within its own shell, and it's not obvious how to easily or portably access this.
(history > history.log ; is very quick to run though)

The suggestion would be that you then typically run a 'git add' on the small input / output files, and commit these to a repository with a sensible commit history.
Then copy the necessary files to continue your job into the PWD, and continue work.
But it's flexible enough that you can also just use this to separate your work when running on a cluster.

I'm sure I'm not the only one who's ended up with a folder structure that ends up looking hellishly like this:-
~/PROJECT_FOO/geom_opt/geom_opt_restart/geom_opt_restart_higher_convergence/moar_kpoints/cation_geom/cation_geom_restart/frequency_calc/ etc.

Instead you end up with something much more sensible, time ordered and single-depthh: https://github.com/jarvist/CDFT-C2H4

Anyhow, check it out here + I'm always interested in all + any feedback!
https://github.com/jarvist/freck
