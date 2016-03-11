---
author: jarvistmoorefrost
comments: true
date: 2014-07-14 12:36:09+00:00
layout: post
slug: links-from-julia-land
title: Links from Julia Land
wordpress_id: 389
tags:
- Julia
---

Julia 0.3 Release Candidate 1 has quietly appeared on the [nightly builds page](http://julialang.org/downloads/); release notes in the [very active GitHub repository](https://github.com/JuliaLang/julia/blob/master/NEWS.md) - improvements to the REPL (tab conversion of 'latex maths' to unicode), and a lot of interesting linear algebra improvements.

The inaugural JuliaCon has been held, and the presentation slidedecks are already online: [https://github.com/JuliaCon/presentations](https://github.com/JuliaCon/presentations); videos are coming but the upload date has been pushed back as they are edited and transcribed.

On the Julia users email list, there was a link published to a very interesting essay on the history of programming languages: [https://groups.google.com/forum/?fromgroups=#!topic/julia-users/T6f9hCkDW6g](https://groups.google.com/forum/?fromgroups=#!topic/julia-users/T6f9hCkDW6g). It ends on a very pro-Julia note! 

I've personally just been using Julia 'for real' in preparing some data for a publication (rather than just using iJulia as a glorified unicode-capable calculator for physical identities). Here I used Julia to calculate the partition function on the fly (by Monte Carlo integration) for an arbitrary torsional potential in a polymer, then form a tight binding Hamiltonian & evaluate the density of states extremely quickly with the Sturm sequence method. If I hadn't discovered Julia, I would have been trying to do this with Python, and though totally feasible I'm not sure I would have got here. You are perpetually operating at the absolute limit of your cognitive capacity in scientific theory (and for me, I'm pretty limited); the more powerful the tools you have the more you can achieve, and Julia does indeed seem a very well geared 'bicycle for the mind' in scientific computing.

[https://github.com/jarvist/LongSnakeMoan/blob/master/Sturm-DoS/Sturm_Drang.jl](https://github.com/jarvist/LongSnakeMoan/blob/master/Sturm-DoS/Sturm_Drang.jl)
