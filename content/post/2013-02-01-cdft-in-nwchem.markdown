---
author: jarvistmoorefrost
comments: true
date: 2013-02-01 19:45:53+00:00
layout: post
slug: cdft-in-nwchem
title: CDFT in NWCHEM
wordpress_id: 69
tags:
- cdft
- nwchem
---

I've been struggling recently to get CDFT jobs to converge in NWCHEM. Rather than continue to play with ~100 heavy-atom structures (of relevance to organic electronic materials) I went to a very simple system of C2H4 / C2F4. This is sometimes studied as a very simple system showing charge transfer.

I had many issues getting this job to run successfully, before realising that I needed a suitably diffuse basis set for the constraints to be applicable! It still has issues at large separations, and I'm not even sure I'm pushing the charge around in the 'correct' way, but these run files may be of use to others.

[https://gist.github.com/4673243](https://gist.github.com/4673243)
