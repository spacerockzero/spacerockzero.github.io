---
# layout: post
title:  "Run Baseline Performance Tests"
date:   2016-01-19
aliases:
- /run-baseline-performance-tests/
# categories: blog-performance-series
# excerpt: "Welcome to part 2 of my blog performance series. I'm Jakob Anderson, \
# and I'm going to show you how to run some baseline performance tests on your blog. \
# This is where we find out how your initial performance is, so we can tell where you \
# currently stand, and whether performance has improved after we've changed things."
---

**Blog Performance Series, part 2**

<div class="flex-video">
<iframe width="560" height="315" src="https://www.youtube.com/embed/G795RIE317s?list=PLWYz5kbNpmYUPTzgw8rhdAk64r4tH1Ynq" frameborder="0" allowfullscreen></iframe>
</div>

Welcome to part 2 of my blog performance series. I'm Jakob Anderson, and I'm going to show you how to run some baseline performance tests on your blog. This is where we find out how your initial performance is, so we can tell where you currently stand, and whether performance has improved after we've changed things.


### Which metrics?

Well, the first thing we need to know is:

*Which metrics to measure.*  

- There are TONS of performance metrics floating around, all with various levels of connection to the user experience.
- Which metrics should we use?

*It all depends on your users.*  

- What kind of experience do you want to give them?

#### Let's Figure It Out

- Who are the blog's intended users?
- What do they want from it?
- How will they consume it?
- What metrics best reflect user success with that in mind?

#### Who are the intended Users?

- My blog is about H.G. Wells, and has some articles about the author.
- So, I have a pretty general audience, it could contain pretty much anyone at this point. 
- From High Schools students cramming for book reports, 
- to adults cramming for a book club, 
- or just wanting to know more about the "latest" in H.G. Wells news.

#### What do they want from it?

- They want informative content about H.G. Wells, I would assume.

#### How will they consume it?

- mobile phones, tablets,
- desktops, laptops, 
- home wifi, library wifi, 3G on the way to class. 
- It could be lots of things, many of which are low-bandwidth and high-latency.


### What metric connects best to a good user experience, given these scenarios?

- Given that we will have some low-bandwidth, high-latency users, we will want to be sure that our pages are light in total transfer bytes, and start and complete render of our critical content very early.
- Performance Budget Guru Tim Kadlec has a great article about the different types of performance metrics here: https://timkadlec.com/2014/11/performance-budget-metrics/
- The **Speed Index** metric from WebpageTest will tell us how quickly the visible content renders. For text articles, that should tell us when the article is ready to read.
- **Time to First Byte** shows how early the first byte of HTML is downloaded. With blogs, we don't often have control of things that affect the response time of the server, though.
- **First Paint** shows how early render begins, which is nice, but Speed Index covers the start to finish of the visible content, so it may be better.
- **Load Time** shows how early the document's window is ready for presentation. Non-visible elements, such as analytics and such can actually inflate this metric without the user being very affected.

#### Metric closest to User Experience?

- So, which metric connects best to a good user experience?
- I would say *Speed Index*, from WebPagetest is the closest.
- According to the WebPagetest docs: 
> "The *Speed Index* is the average time at which visible parts of the page are displayed.  It is expressed in milliseconds and dependent on size of the view port." https://sites.google.com/a/webpagetest.org/docs/using-webpagetest/metrics/speed-index

#### Where to test for Speed Index metric?

So, where do you go to see your page's current Speed Index score?

- For a Manual one-off test: http://www.webpagetest.org/
- For a Bulk test, you can go to the github address here: https://github.com/andydavies/WPT-Bulk-Tester


### Perform initial tests of baseline performance in production

[tech demo]

- (Show different Pagetypes: home, 1, 2, 3, 4, 5)

Let's have a look at the blog we are testing

- I found cool-looking photos from creative commons stock photos sites and put them on the blog, including the blog's icon in the top left
- Here are the different pagetypes i created, and all of the fake content I put into them

#### Use Chrome Devtools > Network tab

- Throttle to Regular 3G, disable cache, see what sticks out
- Most content has arrived and is usable fairly early, but the main homepage image took 45 seconds to download 7MB.

#### Easy image mistakes
- I explained how I got the images from the web and then immediately re-uploaded them the way they were, which explains how this happened. This was to show how easy it is for someone to let this easy but performance-disastrous mistake happen.

#### Baseline Tests

[WebPagetest One-off test demo]

- Examined filmstrip and network waterfall, watched load video

[WebPagetest Bulk Tester demo]

- Ran bulk test on cable and mobile-3g, waited for results
- The numbers aren't that great. The baseline (no content) page is over 1600 on cable, and over 6000 on mobile.


### Let's have a talk about Performance Budgets
- If I want to draw a line in the sand that I can't get worse than, I'm gonna want to make a performance budget.
- What metric should I measure? We already decided on Speed Index.
- What pagetypes do I really have? Blank pagetype and General pagetype. Blank is the blank page for a baseline type, and General is any other page with some content.
- I choose to have performance budgets for cable and 3g connections on each of the two pagetypes.
- I committed to some performance budgets on all 4 scenarios:

```
Metric: Speed Index

Blank:
	cable: < 1000
	3g: < 3000

General:
	cable: < 2000
	3g: < 4000
```


### Identify Performance Issues
- Images are too big (7MB)
- May not need jQuery (38.5K), fitvids.js (1.5K)
- May not need webfonts (34K)
- Should minify CSS file
- Should minify js files


### Create Action Items
- Resize images down to size they are actually used on screen
- Recompress images to reduce filesize further
- Minify all js files
- Remove fitvids.js from shared code ( videos won't resize to match content width anymore )
- Replace jquery menu open/close animation from index.js with vanillaJS alternative code
- Remove jquery request from shared code
- Investigate removing webfonts from shared code
- Minify css file


### Thank you.
I've shown you how to do some baseline performance tests on your blog. I hope you got a lot of value out of it. Look forward to future videos where we pin down and fix these action items. I hope you liked watching this video and found it very informative. Please Subscribe to see many more great performance videos in the future.
