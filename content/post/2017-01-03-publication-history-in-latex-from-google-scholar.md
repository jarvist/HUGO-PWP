---
author: jarvistmoorefrost
comments: true
date: 2017-01-07 23:29:00+00:00
layout: post
title: Publication history in LaTeX from Google Scholar 
---

Having your publication history in a LaTeX document is not the worst idea in
the world. Updating a `.bib` file is natural and easy when making incremental
changes (for the next, seemingly inevitable, academic application in 6 months
time). 

A recommendation though---don't decide to do this two hours before a submission
deadline!

1) Get the data. I only discovered this mass-export by accident.

* Go to your [Google
Scholar](https://scholar.google.co.uk/citations?user=qNlfsFEAAAAJ&hl=en) page 
* click on all the publications on the first page, using the header-checkbox.
* Click on Export / BibTeX
* A pop-up box should ask you "Export selected articles" or "Export all my
  articles", 
* You should now have well formatted  `.bib` file with all your articles.

2) In an ideal world, you should probably be using `biblatex` and associated
helper program `biber`. This allows you to specify the ordering (i.e.
chronological). 

See `sorting` and `style` options here: (https://www.sharelatex.com/learn/Bibliography_management_with_biblatex)

3) However, my TeX installation was missing `biber`. (In a sort of
broken-package, what on earth have I done to Debian kind of way.) 

So I decided to use the more primitive `bibtex`, with an 'unsrt' (unsorted) bibliography. 

This then just lists the items in the order they are present in the `.bib` file.

My Google Scholar `.bib` was mostly chronological (pre 2010 seemed
less ordered, I suppose recent entries have been appended as they were
published). 

This meant it didn't take too long to reorder it correctly. 

(I also needed to delete some spurious entries.)

4) My LaTeX file listing the journal articles, was piece together from bits of
tex.stackexchange, and the important bit read as follows (my bib file was
`PublicationsFull.bib`):

```
\subsection*{Journal articles}

\nocite{*} % cite all bib items, without text

\begingroup % stops printing 'references';
%   http://tex.stackexchange.com/questions/22645/hiding-the-title-of-the-bibliography
\renewcommand{\section}[2]{}%

\bibliography{PublicationsFull}{}
\bibliographystyle{unsrt}

\endgroup
```

