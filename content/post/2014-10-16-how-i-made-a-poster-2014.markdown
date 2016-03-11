---
author: jarvistmoorefrost
comments: true
date: 2014-10-16 04:09:51+00:00
layout: post
slug: how-i-made-a-poster-2014
title: How I made a poster; 2014
wordpress_id: 413
---

I made a scientific poster last week, for the first time in five years.

I drew it in Inkscape, a free opensource vector drawing package. I'm have quite a lot of experience using Inkscape in drawing cave surveys, but I believe it's both relatively easy to use, and has some extremely useful tools for constructing posters (most notably the alignment & distribution tool). The one gotcha is that you have to explicitly ask for it to spell check your text fields! It's native fileformat is SVG based, and it is very happy to import PDFs (i.e. figures / graphs - from gnuplot I use the colour postscript terminal, then 'ps2pdf' on the command line).

[![Crystal Kinematics Poster](https://jarvistmoorefrost.files.wordpress.com/2014/10/poster.jpg)](https://github.com/jarvist/PerovskiteKinematics/raw/master/2014-10_JMF_Korea_Poster.pdf)

Like most scientists, I am no designer. So I'm mainly winging it, and can't rely on whether things look right or not! I found a colour scheme that was close to some of my figures from Adobe's Color CC [1], and then put those five colours in a swatch just outside the page on the Inkscape. I put all the main text in a medium weight Futura clone, because I like it.

These days I make my talk slides in Google Present, viewing a certain slide and then selecting "Download as SVG", opened in Inkscape as a fairly well-behaved vector images with embedded bitmaps, to then have the slide template objects deleted & used within the poster.

I also made a tie-in website, linked from a QR code (generated with a free web service) on the poster, as a place to collate links to the YouTube videos and a reprint of the poster itself. 
This I generated with GitHub pages and the Flatdoc HTML/JS code [2], a lightweight and modern responsive web framework. You put the Flatdoc HTML file (template.html) as index.html on the 'gh-pages' branch of your GitHub repo, having edited the HTML to set the USER/REPO/Title correctly. It then pulls down the README.md from your 'master' branch of the repo, and live renders any changes on the browser. Assuming you are used to GitHub & have (fairly minimal) HTML/CSS abilities this is a really quick way to put together something that looks pretty acceptable. [3]

Overall I was quite pleased with how easy it is to put together something that looks acceptable. If you are interested - have a look at the Inkscape SVG & the structure of the github REPO. [4]

[1] https://color.adobe.com/explore/
[2] http://ricostacruz.com/flatdoc/
[3] http://jarvist.github.io/PerovskiteKinematics/
[4] https://github.com/jarvist/PerovskiteKinematics
