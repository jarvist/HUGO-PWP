---
author: jarvistmoorefrost
comments: true
date: 2014-01-13 13:35:46+00:00
layout: post
slug: gaussian-add-densitycurrent-for-post-hf
title: 'Gaussian: add ''Density=Current'' for post-HF'
wordpress_id: 280
tags:
- gaussian
- notetoself
- snippet
---

Do your electrostatics / population analysis from some expensive post-HartreeFock calculation look suspiciously similar to the HF result? You probably forgot to add 'Density=Current' to your input stack.

I don't understand why this isn't the default, as when you are doing (hybrid)DFT calculations, the SCF density is being varied, thus the pop / electrostatics output change with functional.
