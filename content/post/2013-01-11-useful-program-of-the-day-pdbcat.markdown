---
author: jarvistmoorefrost
comments: true
date: 2013-01-11 13:34:35+00:00
layout: post
slug: useful-program-of-the-day-pdbcat
title: 'Useful program of the day: pdbcat'
wordpress_id: 3
---

http://www.ks.uiuc.edu/Development/MDTools/pdbcat/

A tool to convert from the nasty column / fixed-width 'fortran like' PDB fileformat to a more reasonable unix-like whitespace delimited fields, and back again.

I had to add 'using namespace std; ' to line 24 of pdbcat.C to get it to compile (otherwise "error: 'cerr' was not declared in this scope").
