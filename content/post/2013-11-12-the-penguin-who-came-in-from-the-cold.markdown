---
author: jarvistmoorefrost
comments: true
date: 2013-11-12 19:04:54+00:00
layout: post
slug: the-penguin-who-came-in-from-the-cold
title: The penguin who came in from the cold
wordpress_id: 211
---

Coming to Mac OS X from over a decade on Linux is quite a change! Here are notes of things I've found useful in making the transition, starting with more general and ending at things rather specific (and esoteric!).

**Homebrew** is sort of a Gentoo ports - http://brew.sh/, it's pretty swish and pulls directly down from GitHub based 'recipes'. There's a 'science' 'tap' (PPA) with lots of useful software. But install Latex via **MacTex** http://tug.org/mactex/

**iTerm2** is a nice terminal client. The true-type font (TTF) Inconsolata works well. Cmd + T for a new tab, Cmd + Arrow to change tab. Cmd + D to split the window vertically, Cmd + Shift + D to split horizontally, Cmd + [ or ] to shift between splits.

**Skim** is a sophisticated PDF viewer, with annotations - ideal for scribbling on literature.

Ctrl + Arrow to change virtual desktop, look in top right of Wing Commander screen (F3 magic button) to add desktops.

~/.profile rather than ~/.bash_rc. Colour ls via " alias ls='ls -Gp ' "

Install a modern vim from homebrew (+ relink the old one so /usr/local/bin takes precedence).

Disable the horizontal scroll of your Magic Mouse (+ turn on right click while you're there), so you can scroll PDFs + etc without sideways distraction: https://discussions.apple.com/message/10879820#10879820

And turn up the repeat-rate for your keyboard.

Disable all the shearing animations before you start to feel sea sick: http://apple.stackexchange.com/questions/14001/how-to-turn-off-all-the-animation-effect-on-mac-os

iTunes is clearly a terrible idea. MOCP works - but only via having to install Jack! https://gist.github.com/AzizLight/6045338
