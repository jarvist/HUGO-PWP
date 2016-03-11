---
author: jarvistmoorefrost
comments: true
date: 2013-06-18 11:51:38+00:00
layout: post
slug: pymol-ray-tracing-without-wasting-time
title: Pymol Ray Tracing without wasting time
wordpress_id: 70
tags:
- pymol
- snippet
---

I often use the nice built in 'ray' raytracer in Pymol. These ray traces can take minutes to hours, and during that time I of course want to use my computer! Unfortunately, the Pymol window freezes during the ray trace, so when I switch virtual desktops it sometimes looks as if there's a frozen terminal or similar there, which I click on, sometimes inadvertently, sometimes because I am a fool. This click gets queued up to Pymol and promptly delivered as the ray trace finishes - making the window redraw with the built in opengl, wasting all the time ray tracing, arg!

After doing this today during a 30 minute ray trace, I sat and thought for a few seconds and did the sensible thing:

 

PyMOL> ray; save ray.png

Chain the commands together so that it immediately saves the ray trace image, no matter what you do to the GUI in the meantime! I wish I'd taken the few moments to think this through back in 2009 or so.[![Image](http://jarvistmoorefrost.files.wordpress.com/2013/06/ray.png?w=650)](http://jarvistmoorefrost.files.wordpress.com/2013/06/ray.png)
