---
author: jarvistmoorefrost
comments: true
date: 2014-02-24 22:15:35+00:00
layout: post
slug: pushing-the-boat-out-to-github
title: Pushing the boat out (to GitHub)
wordpress_id: 322
---

In academia you often want to keep code in a private repository (such as a free BitBucket repo), then push out to GitHub for greater opensource exposure when you've mostly finished the first paper etc. This is easy to do with Git while retaining full commitment history by adding an extra remote. I just did this today, and leave these simple commands here as a bookmark for when I next need to do it.

`> git remote add github git@github.com:jarvist/LongSnakeMoan.git`
you can then explicitly push out to GitHub via
`> git push github master`
Check on the status of your remotes with
`> git remote -v`
