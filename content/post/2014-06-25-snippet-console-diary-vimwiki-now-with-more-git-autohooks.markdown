---
author: jarvistmoorefrost
comments: true
date: 2014-06-25 23:49:41+00:00
layout: post
slug: snippet-console-diary-vimwiki-now-with-more-git-autohooks
title: 'Snippet: Console diary - vimwiki (now with more git & autohooks)'
wordpress_id: 382
---

I've regularly dallied with keeping a computer / online logbook. I've tried many products, even wrote my own (retrospectively crazy) set of scripts called 'freck' (https://github.com/jarvist/freck). 

All these platforms were only ever used for a week or two before falling by the
wayside. I also don't like the idea of walled-gardens (such as evernote)
becoming a trap for my information. 

I keep paper notebooks for talks; I think it is essential to be able to sketch maths and diagrams, and I honestly think my brain is more engaged when I'm making notes by hand versus either typing or just listening (i.e. daydreaming). But they're impossible to search through, and just a bit ridiculous to use when sitting in front of a computer.

The one I've returned to vaguely reliably is 'vimwiki'
(https://github.com/vimwiki/vimwiki). I've written ~10'000 words over 4 years.
It lives in vim, and is thus only ever two keystrokes away when I'm editing
files. 
It runs in two modes, a 'diary' linked to '\w\w' which drops you into
a sensibly dated file for today, and a full blown personal wiki at '\ww'. All
files are just... files in ~/vimwiki.

My ~/vimwiki is a BitBucket private repository. The effort of changing to the correct directory & then 'git pull' or 'git add / commit / push' often led to dropping out of sync. 
I was thinking of doing something primitive such as putting it within in Dropbox, but instead I came across this blog entry:
[http://www.stochasticgeometry.ie/2012/11/23/vimwiki/](http://www.stochasticgeometry.ie/2012/11/23/vimwiki/)

I've no interest in encrypting my diary but the auto-hooks to commit to a DVCS are a fantastic idea.

Here's the hooks, translated for git:

```
$ tail ~/.vim/ftplugin/vimwiki.vim
augroup vimwiki
au! BufRead /home/jarvist/vimwiki/index.wiki !git pull
au! BufWritePost /home/jarvist/vimwiki/* !git add ;git commit -m "Auto commit + push.";git push
augroup END
```

## Freck

an obsolete word meaning nimble: [http://matadornetwork.com/abroad/20-obsolete-english-words-that-should-make-a-comeback/](http://matadornetwork.com/abroad/20-obsolete-english-words-that-should-make-a-comeback/)

'Freck' was a set of scripts I wrote essentially the day after I submitted my PhD thesis - having struggled with finding original data sources to things I only had as poorly named postscripts and PDFs, or even just hard annotated printouts from supervisor meetings.
They worked both remotely on the HPC + locally. I recall that 'freck' would take a figure as an argument, send a copy of this back to my workstation, demand a caption, and automatically add a figure to a 'labbook' Latex file, with some commented out sections '%' informing future-me where exactly this data came from, auto date stamp, where it was generated etc. Different projects were set by an environmental variable, which were then sub-directories in the local ~/freck/ directory with Latex files & figures. I think the idea was that I would have a vim session running locally, and would reload the text, now with a generated figure.

Writing it's description, it still sounds like a good idea! I'd probably now do it with more markdown (at least at the raw 'freck' end), and a DVCS.

Only surviving remnant: [https://github.com/jarvist/CoarseGrainPCBM/tree/master/2011-01_JMF_LabBook](https://github.com/jarvist/CoarseGrainPCBM/tree/master/2011-01_JMF_LabBook)
Though who knows, maybe I'll make it a Friday afternoon project to find the code & update it for something more sane / general.


