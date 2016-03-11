---
author: jarvistmoorefrost
comments: true
date: 2013-12-12 22:25:23+00:00
layout: post
slug: make-for-data-processing
title: Make for Data Processing
wordpress_id: 247
tags:
- data
- make
---

I must admit that I have a lot of 'historical' (as in, before the last hour...) directories with processing scripts named usefully 'process_processed_data.sh' and such. If I remember, I often pipe a 'history' into a hist.sh file before I close the terminal + forget what I've done and how to process the data.

So I definitely should and could do better, so why not use Make? It handles dependencies & gobbles files effectively, but I just can't help but feel there should be a more elegant solution than writing clunky Make files by hand.

Why use Make? - [http://bost.ocks.org/mike/make/](http://www.datatau.com/item?id=35)

Discovered via DataTau, a new data-processing news aggregator (in the style of hackernews):-

[http://www.datatau.com/item?id=35](http://www.datatau.com/item?id=35) - see here for a link to 'drake' a make for data science.
