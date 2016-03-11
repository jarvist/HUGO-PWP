---
author: jarvistmoorefrost
comments: true
date: 2014-01-06 22:08:37+00:00
layout: post
slug: new-years-resolution-dvcs-everywhere
title: New year's resolution - DVCS everywhere
wordpress_id: 270
tags:
- bitbucket
- dvcs
- git
---

My one new year's resolution is to use DVCS everywhere.

With free BitBucket Academic accounts (**unlimited private** / public repos), [http://blog.bitbucket.org/2012/08/20/bitbucket-academic/](http://blog.bitbucket.org/2012/08/20/bitbucket-academic/), there's no reason not to use it for every paper, internal document, code snippet or website. From a Linux / OS X console there is very little friction in automatically using "git add + commit, push & pull". It's also a very nice + fluid way to share finalised data & code between HPC facilities, colleagues, collaborators & workstations.

GitHub seems to get more exposure for opensource repositories, but for publication it is easy both to turn a BitBucket private repo to public, and to push repos from anywhere to anywhere else (i.e. to GitHub).

The only slight issue is that the default git diff function is highly optimised for code (it has a per-line view of the world) - Latex / text files are best treated by artificially adding a carriage-return after every sentence. Otherwise even minor edits within a paragraph will fail to merge. Anyone have any suggestions for getting git to be a bit more clever (merge based on sentence? based on clause?).

Very short git getting-started guide: [http://rogerdudler.github.io/git-guide/](http://rogerdudler.github.io/git-guide/)
