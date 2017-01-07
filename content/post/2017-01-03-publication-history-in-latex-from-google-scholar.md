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
broken-package, what on earth have I done to Debian kind of way.). So using the
more traditional `bibtex`, you are left with using an unsorted bibliography and
enforcing the order by hand. 

From inspection, the Google `.bibs` are mostly chronological (pre 2010 seemed
less ordered, I guess recent entries have been appended as they were
published), so it didn't take me too long to reorder it correctly. (I needed to
delete some spurious entries anyway.)

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

