---
author: jarvistmoorefrost
comments: true
date: 2014-05-08 14:09:17+00:00
layout: post
slug: snippet-converting-latex-figures-to-eps
title: 'Snippet: Converting Latex figures to EPS'
wordpress_id: 366
---

Day of the deadline & you realise you need to convert all your figures to EPS format, and put them in the same directory as the source .TeX files for submission? Happened to me today with APLMater. I had 23 individual files (as the figures were full-width composites), so I wrote a script to strip the filename from the TeX, rename to a flat file format, strip any periods ('.') in the filename & do the conversion / copying.

I stopped short of actually editing the TeX automatically as well, as the idea seemed a bit crazy and in my case due to the aforementioned periods in filenames (escaped in Latex with {braces}) would have been a little bit messy.

Nb: Once you do this, you should be compiling the .TeX with Latex (to DVI) then dvipdf --> PDF as using pdflatex will convert all the figures back to PDF (giving nasty JPEG ringing artefacts to your figures).

On GitHub in case it's use to anyone else!
[https://github.com/jarvist/ConvertLatexFigsToEPS](https://github.com/jarvist/ConvertLatexFigsToEPS)
