---
author: jarvistmoorefrost
comments: true
date: 2014-04-21 15:55:42+00:00
layout: post
slug: snippet-recompress-pdf-file-use-ghostscript
title: 'Snippet: Recompress PDF file - use ghostscript!'
wordpress_id: 360
---

Need to wrestle a large PDF (i.e. from TeX) with lots of images? Ghostscript is your friend! `-dPDFSETTINGS=/printer` seems to give good results with a perfectly legible PDF.

`gs -sDEVICE=pdfwrite -dCompatibilityLevel=1.4 -dPDFSETTINGS=/printer -dNOPAUSE -dQUIET -dBATCH -sOutputFile=small.pdf big.pdf`

[http://tex.stackexchange.com/questions/14429/pdftex-reduce-pdf-size-reduce-image-quality/41273#41273](http://tex.stackexchange.com/questions/14429/pdftex-reduce-pdf-size-reduce-image-quality/41273#41273)
