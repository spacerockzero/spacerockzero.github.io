---
title: "Learn by Projects"
date: 2022-03-21
publishDate: 2022-03-21

categories: []
tags: []
toc: false
author: "Jakob Anderson"
featuredImage: "article/learn-by-projects/cover-opto.jpg"
---

Building https://eclecticbeams.com and https://ai.eclecticbeams.com have taught me a lot.

I try to use new technologies often while making new projects, and I learned a lot about making a gatsby blog for eclecticbeams, even adding some future-scheduling functionality for articles while at it. I tended to make my content in batches on the weekend, and wanted a way to publish it regularly throughout the week.

I used [Svelte.js](https://svelte.dev/) & learned Sapper.js to make ai.eclecticbeams.com, since I've enjoyed using [Svelte.js](https://svelte.dev/), and needed server-side render capability for SEO goodness in those social shares.

I wanted to try out a new cloud backend-as-a-service, so I abused a redis service ,to use as a db for ai.eclecticbeams.com just to see how far I could push it. The canonical data still lives in the repo, and could repopulate the db any time, since redis is ideally best suited for the volatile caching of data.

I'd like to be able to query by more properties, so I'll probably move to a more typical database for the next iteration of that, whenever that happens.

This site itself is another one of those things. I chose to remake jakobanderson.com in a static site generator called [Hugo](https://gohugo.io/), which is known for crazy fast render performance, and written in the [GO Language](https://go.dev/). I'm liking it so far, and it might give me a chance to learn some Go.
