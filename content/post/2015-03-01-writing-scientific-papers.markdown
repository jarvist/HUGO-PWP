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

I am probably the last person you would want to consult on tips to write a scientific publication. I'm slow, I procrastinate, my English is not the best, much work lies on the cutting room floor - skeletons of half assembled papers. Still, 'that which we are, we are', though my skills are lacking I'm very interested in improving, and certainly enjoy reading a well written paper.

It is an unfortunate fact that the average quality of scientific writing is decreasing. Some of this can be explained by the laudable continuing expansion of science across class boundaries, and across the world (a greater number of authors writing in English as an additional language). Yet I think the majority reason is the pressure to publish so much, we write so many more papers, and there's enormous pressure to oversell.

My parents were visiting this weekend. "How is work?" my mother asked. "I should be writing more." - the scientist's lament. "Oh, but don't you only write a paper when you make a breakthrough?" To be honest I think we would have a better scientific corpus if this was still the case - carefully work on a hard problem for a few years until we gain some traction, then write it up for the benefit of anyone who could take it elsewhere.

(Along these lines, Ross McKenzie has a recent blog post '[In praise of modest goals](http://condensedconcepts.blogspot.co.uk/2015/02/in-praise-of-modest-goals.html)'.)

So the first thing to do is to overcome the cynicism! When I get particular disaffected and want to crawl under my duvet and drift off to sleep reading Feynman, I return to Simon Peyton Jones' talk on [how to write a great research paper](https://www.youtube.com/watch?v=g3dkRsTqdDA) . His enthusiasm and motivation is infectious. I am a worm. A worm with a infectious mind virus, and that is good. (Much like his choice of font, do read: http://www.mcsweeneys.net/articles/im-comic-sans-asshole )

Sabine Hossenfelder wrote a recent blog post on [How to write your first scientific paper](http://backreaction.blogspot.co.uk/2015/01/how-to-write-your-first-scientific-paper.html), this covers the construction and sectioning of a physics paper.

I've personally found the Penguin Writer's Manual very useful for the nitty gritty of 'that' vs 'which'. I've also read Strunk and White (The elements of style), though I'm not sure how much I took from it. The [economist style guide](http://backreaction.blogspot.co.uk/2015/01/how-to-write-your-first-scientific-paper.html) (available online) is also very useful as a reference.

I much prefer to write with Latex. Sometimes I first go via Markdown (a lightweight markup language that looks a lot like how you would naturally format a text email), so I don't need to bother with thinking about the Latex commands when forming a text, and then convert to Latex (with pandoc) for inclusions of figures & all the revisions that incur thereafter. The whole project I put within a 'git' repository and so have version control, effectively offsite backup (to Github / Bitbucket). To get the diffs to work well with the files, it's easiest to add a newline after the end of every sentence (I usually hard-break my lines at 80 chars as I write in Vim).

I have contributed to papers in Microsoft Word (usually originating with collaborators). It works OK, and the track changes / comment tool can be really useful, though a distressing number of collaborators seem to send you back a 'clean' document with the tracking dropped. Whether that's due to ignorance of the tools, compatibility with different versions of Word, or an attempt to bury any information about which of your changes they reverted, I do not know. Certainly it makes me respect them less academically and professionally.

I typically plot data in GNUPLOT or XMGRACE, sometimes also in Python's Matplotlib (though this is much less deterministic - the output depends on the specific version you have installed, and it can be extremely frustrating to reproduce a tweaked diagram). I've found some useful websites on tips + tricks for plotting, useful beyond an immediate answer to resolving a problem.

I've consolidated all my useful bookmarks on the above, and put them in a shared Google Chrome bookmark folder : [Writing scientific papers](https://www.google.com/stars/yhmqn5hv65adw/profile/folio/ssf_7f2647dd238f3fb7?hl=en-GB)
