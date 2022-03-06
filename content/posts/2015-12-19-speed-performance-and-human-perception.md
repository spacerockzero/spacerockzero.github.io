---
# layout: post
title:  "Speed, Performance, and Human Perception"
date:   2015-12-19
aliases:
- /speed-performance-and-human-perception/
# categories: performance
# excerpt: "“Performance” means many different things to different people full-stack perf is \
# complicated is there such a thing as “fast enough”? context matters: — 10fps matters in games, \
# 10fps matters much less in e-commerce Devs often forget about the wetware running their ui’s \
# (human brain). Notes from Ilya's talk at Fluent 2014"
---

*Notes from Ilya Grigorik's talk at O'Reilly Fluent conference 2014*

My notes on Ilya Grigorik’s talk (@igrigorik)
Video: [http://www.youtube.com/watch?v=7ubJzEi3HuA](http://www.youtube.com/watch?v=7ubJzEi3HuA)

<div class="flex-video">
<iframe width="560" height="315" src="https://www.youtube.com/embed/7ubJzEi3HuA" frameborder="0" allowfullscreen></iframe>
</div>

What follows are my notes from watching Ilya’s presentation:

“Performance” means many different things to different people full-stack perf is complicated is there such a thing as “fast enough”? context matters: — 10fps matters in games, 10fps matters much less in e-commerce Devs often forget about the wetware running their ui’s (human brain) Joked about it using some sort of IE6

## Task Oriented Reaction Times:

> Intent > Action > Response  

## Delay > User Reaction 
<table>
  <tr><td> 1-100ms </td><td> Instant </td></tr>
  <tr><td> 100-300ms </td><td> slight perceptible delay </td></tr>
  <tr><td> 300-1000ms </td><td> Task focus, perceptible delay 1s+ mental context switch </td></tr>
  <tr><td> 10s+ </td><td> I’ll come back later… </td></tr>
</table>

## Visual and audio processing have different perceptive resolutions:

### Visual
- **24fps (~40ms)** — minimum stutter-free FPS
- **60fps (~16ms)** — silky smooth experience

### Auditory
- **1ms+ jitter** — Audible sound discontinuity

## Perceived perf equation:
> **Perceived performance** = `f(Expected Performance, UX, Actual Performance) ` 

**The UX is the glue between expectations and silicon**

> Performance is not just milliseconds, frames, and megabytes. It’s also how these milliseconds, frames, and megabytes translate to HOW THE USER PERCEIVES THE APPLICATION.

## Who’s responsible for perf of UX layer? Everyone.

### Hacker news case study:

- Hacker news is fast due to its simplicity, renders reliably in under 500ms.
- Experience actually sucks on mobile. Takes a few seconds to realize the page is loaded and text is too small, then zoom in, then swiper to read the headlines.
- Actual time to complete task is around 5-10s, and I hate it.
- Fulfills technical aspects, but fails on completing task in a performant manner.

### Finally, as a community, we have moved past the onload time.

- What are the primary use tasks for your application?
- What is the time to task completion? What is the expected time to task completion?
- _**Determine primary core tasks you want user to achieve. Measure the time it takes for them to be available, and how long it takes to complete them.**_

## Blogger case study:
_There is a "too fast"_  

- Creating a new blog was almost instant, it returned almost immediately.
- Users expected important things to take a little bit of time. task was a big commitment.
- Users thought experience was broken because it returned too fast. had low user satisfaction.
- Simple fix: add a spinner on a page that does absolutely nothing, and user satisfaction went up.
- The user/wetware expectation was different from the ui result, so satisfaction is low.

## phpMyAdmin case study:
- Because the db queries take different, inconsistent amounts of time, the feedback was inconsistent.
- **_You must give users feedback, and also feedback to inform their expectations._**
- If something will take a long time, let them know.
- Give feedback in metrics, units that are very clear to intended users, IE: seconds, minutes instead of gigabytes for consumers.

## Experience Formula:

> **Perceived Performance** = `f(Expected Performance, UX, Actual Performance) ` 

> **Experience** = `f(Perceived Performance, Task Completion)`

- What is the task the user is trying to achieve?
- What does the wetwear between our ears expect?
- What is the technical performance of the components required to fulfill the task? Megabytes, milliseconds, frames?
- How can we design the app to best connect perceived and actual performance? Did it succeed in helping me complete the task?

## Main Takeaways:
- **Developers:** learn about the wetwear (user brain). Think about the user tasks. Performance is when these two meet in the middle.
- **Designers:** learn about the technical and wetwear (user brain) constraints, design for task completion.
