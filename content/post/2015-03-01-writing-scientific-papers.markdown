---
author: jarvistmoorefrost
comments: true
date: 2015-03-01 22:44:00+00:00
layout: post
slug: writing-scientific-papers
title: Writing scientific papers
wordpress_id: 426
tags:
- bitbucket
- gnuplot
- writing
---

(Updated 2016-03-12 to re-add the links)

I am probably the last person you would want to consult on tips to write
a scientific publication. I'm slow, I procrastinate, my English is not the
best, much work lies on the cutting room floor - skeletons of half assembled
papers. Still, 'that which we are, we are', though my skills are lacking I'm
very interested in improving, and certainly enjoy reading a well written paper.

It is an unfortunate fact that the quality of scientific writing is
decreasing as a function of time. 
Some of this can be explained by the laudable continuing expansion of
scienitific research across the world resulting in a greater number of authors
writing English as an additional language.
I believe the major reason stems from the unrelenting pressure to publish.
Many more papers are written, yet there are still only the same number of days
in the year. 
With these publication metrics deciding so much of our future careers (and thus
lives), there is also enormous pressure to 'glam up' work and oversell, as well
as to 'salami slice' and represent work that belongs together in one
paper in many. 

It used to be that scientists would work continuously on a problem, and then
publish when a 'breakthrough' had been made. 
To be honest I think we would have a better scientific corpus if this was still
the case - careful work on a hard problem for a few years until we gain some
traction, then write it up for the benefit of anyone who could take it
elsewhere.

(Along these lines, Ross McKenzie has a recent blog post '[In praise of modest
goals](http://condensedconcepts.blogspot.co.uk/2015/02/in-praise-of-modest-goals.html)'.)

So the first thing to do when writing is to overcome the cynicism! 
When I get particular disaffected I return to Simon Peyton Jones' talk on [how
to write a great research paper](https://www.youtube.com/watch?v=g3dkRsTqdDA)
. His enthusiasm and motivation is infectious. I am a worm. A worm with
a infectious mind virus, and that is good. 

Sabine Hossenfelder wrote a useful blog post on [How to write your first
scientific
paper](http://backreaction.blogspot.co.uk/2015/01/how-to-write-your-first-scientific-paper.html),
this covers the construction and sectioning of a physics paper.

I've personally found the Penguin Writer's Manual very useful for the nitty
gritty of 'that' vs 'which'. I've also read Strunk and White (The elements of
style), though I'm not sure how much I took from it. The [economist style
guide](http://backreaction.blogspot.co.uk/2015/01/how-to-write-your-first-scientific-paper.html)
(available online) is also very useful as a reference. 
(2016 update: Steven Pinker's 'The Sense of Style' is fantastic. Dispels a lot
of prescriptive myths, but also teaches how to analyse your sentences and
identify clumsy phrases.)

I much prefer to write with Latex. Sometimes I first go via Markdown (a
lightweight markup language that looks a lot like how you would naturally
format a text email), so I don't need to bother with thinking about the Latex
commands when forming a text, and then convert to Latex (with pandoc) for
inclusions of figures & all the revisions that incur thereafter. The whole
project I put within a 'git' repository and so have version control,
effectively offsite backup (to Github / Bitbucket). To get the diffs to work
well with the files, it's easiest to add a newline after the end of every
sentence (I usually hard-break my lines at 80 chars as I write in Vim).

I have contributed to papers in Microsoft Word (usually originating with
collaborators). It works OK, and the track changes / comment tool can be really
useful, though a distressing number of collaborators seem to send you back
a 'clean' document with the tracking dropped. Whether that's due to ignorance
of the tools, compatibility with different versions of Word, or an attempt to
bury any information about which of your changes they reverted, I do not know.
Certainly it makes me respect them less both academically and professionally. 
It is most incredibly frustrating to be editing a sentence, not sure
whether you're applying the same change again, undoing an important correction
or what. 

I typically plot data in GNUPLOT or XMGRACE, sometimes also in Python's
Matplotlib (though this is much less deterministic - the output depends on the
specific version you have installed, and it can be extremely frustrating to
reproduce a tweaked diagram). I've found some useful websites on tips + tricks
for plotting, useful beyond an immediate answer to resolving a problem.

### Useful general resources 
* Simon Peyton Jones talk https://www.youtube.com/watch?v=g3dkRsTqdDA
   * Hacker News discussion https://news.ycombinator.com/item?id=6989806
* Sabine Hossenfelder blogpost
  http://backreaction.blogspot.co.uk/2015/01/how-to-write-your-first-scientific-paper.html
* The Researcher's Bible
  http://homepages.inf.ed.ac.uk/bundy/how-tos/resbible.html
* Economist - Style Guide http://www.economist.com/styleguide/introduction

### Colour
* IBM paper "Why should engineers and scientists be worried about color?"
  http://www.research.ibm.com/people/l/lloydt/color/color.HTM
* Adobe's Color CC https://color.adobe.com/explore/most-popular/?time=all
* TIGERcolor, Introduction to color theory
  http://www.tigercolor.com/color-lab/color-theory/color-theory-intro.htm
* Smashing Magazine, Color theory for designers
  https://www.smashingmagazine.com/2010/02/color-theory-for-designer-part-3-creating-your-own-color-palettes/
* Colorbrewer http://colorbrewer2.org/

### Writing
* 20 Obsolete English Words
  http://matadornetwork.com/abroad/20-obsolete-english-words-that-should-make-a-comeback/
* University of Manchester academic phrasebank http://www.phrasebank.manchester.ac.uk/
* Uni of Illinois, Captilisation and dashes in Physics (PDF)
  http://www.nt.ntnu.no/users/haugwarb/Misc/capitalization.pdf
* David Marsh, 10 grammar rules to forget
  https://www.theguardian.com/science/2013/sep/30/10-grammar-rules-you-can-forget

### Plotting
* Xmgrace tips http://lptms.u-psud.fr/wiki/index.php/Tips_for_Xmgrace
* A Grace/Inkscape workflow
  https://sites.google.com/site/patrickbwarren/beautiful-figures
* Grace Forum http://plasma-gate.weizmann.ac.il/Grace/phpbb/
* Gnuplot Tricks http://gnuplot-tricks.blogspot.co.uk/
   * Publication quality example
     http://gnuplot-tricks.blogspot.co.uk/2009/05/gnuplot-tricks-many-say-that-it-is.html
* Gnuplotting http://www.gnuplotting.org/
   * Output terminals http://www.gnuplotting.org/output-terminals/
* gnuplot-colorbrewer https://github.com/aschn/gnuplot-colorbrewer

### Git / Latex / Markdown
* Word by word diffs in Git
  https://idnotfound.wordpress.com/2009/05/09/word-by-word-diffs-in-git/
* A call for scholarly markdown
  http://blogs.plos.org/mfenner/2012/12/13/a-call-for-scholarly-markdown/
* CodeCogs LaTeX equation editor (useful for talks not in LaTeX Beamer!)
  http://www.codecogs.com/latex/eqneditor.php
* Detexify - draw a symbol, find the Latex
  http://detexify.kirelabs.org/classify.html
* LaTeX Templates http://www.latextemplates.com/
* TikZ example http://www.texample.net/tikz/examples/membrane-surface/
* Top four LaTeX mistakes
  http://www.johndcook.com/blog/2010/02/15/top-latex-mistakes/
* Precise positioning in LaTeX Beamer
  http://blogs.helsinki.fi/smsiltan/2012/10/12/precise-positioning-in-latex-beamer/
* Papercore summaries
  http://papercore.org/summaries
* Making a poster with Inkscape
  http://blog.felixbreuer.net/2010/10/24/poster.html

### Ambient music for headphones in noisy offices
* Music to let you concentrate https://news.ycombinator.com/item?id=5872414
* Headphone Commute - electronic, ambient http://reviews.headphonecommute.com/
