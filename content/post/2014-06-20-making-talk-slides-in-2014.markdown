---
author: jarvistmoorefrost
comments: true
date: 2014-06-20 18:43:15+00:00
layout: post
slug: making-talk-slides-in-2014
title: Making Talk Slides in 2014
wordpress_id: 375
---

These days I almost exclusively make my talks in Google Drive / Present. It just works, I can work on my talk from anywhere (my laptop is Linux, my work machine is Mac OS) the modern interface is really quite nice (at least in Chrome). Most importantly for me it has very sensible auto-hints for placing items (a feint alignment lines pop up when you are centre / left / right aligned with other elements on the page).

I download the Talk as PDF for actually putting on my laptop / USB stick. This used to sometimes cause really irritating behaviour with lines reflowing compared to what you saw on screen (sometimes disappearing a word / reference off the page or under another element) but it seems to be ~pixel perfect recently.

I use the codecogs Latex renderer for bits of maths and physics (18pt / 300 / white background with Latin Modern), simply copy and pasting the gif into the slide & then copy + pasting the Latex into the Google Drive 'speaker notes' at the bottom of the screen, for future reference / adaptation for another talk or paper.
[http://www.codecogs.com/latex/eqneditor.php](http://www.codecogs.com/latex/eqneditor.php)

I often find myself dragging and dropping .pngs directly from a directory of post-processing codes to make up a talk. All my Python codes which plot to Matplotlib now automatically save figures they generate as PDFs and PNGs, with a name that ensures they don't overwrite each other & you can cross reference to commit versions in the future. This I have found so incredibly useful, barely remembered runs of old codes and datasets are sitting there with 'talk ready' images.

` import datetime
now=datetime.datetime.now().strftime("%Y-%m-%d-%H%M") #String of standardised year-leading time
fig.savefig("%s-LongSnakeMoan.pdf"%now) #Save figures as both PDF and easy viewing PNG (perfect for talks)
fig.savefig("%s-LongSnakeMoan.png"%now)
`

Previously I made talks with OpenOffice / LibreOffice (Horrible, buggy experience) and Latex/Beamer (too slow to include figures, horrific / absent control about where to place elements. Leave it for the mathematicians!)

My only two issues with Google Present are no videos (if not online - it will link to YouTube), and no Futura font (I use Open Sans in its stead).

There's a few quirks in the user interface, most particularly if you're making a derivative talk, you must use 'Insert / Import slides...' rather than trying to copy+paste a load of slides from a different browser window - this makes it unhappy! (I guess because it's bringing them to the local clipboard and then trying to push them back up to Google?)
