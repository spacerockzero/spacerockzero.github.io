---
# layout: post
title:  "Web Performance Culture"
date:   2015-12-12
aliases:
- /web-performance-culture/
# categories: performance culture
# excerpt: "If you want to improve web performance at your company, creating a \"Performance Culture\" is the best way to maintain it. This video explains how to do this in the best way I've seen yet. Check it out!"
---

If you want to improve web performance at your company, creating a **Performance Culture** is the best way to maintain it. This video explains how to do this in the best way I've seen yet. Check it out! (My Summary notes below)

Video: https://www.youtube.com/watch?v=0bRLtJHo0pI

## Presenters:

- Paul Lewis (Google dev advocate)
- Lara Swanson (Etsy perf)

<div class="flex-video">
<iframe width="560" height="315" src="https://www.youtube.com/embed/0bRLtJHo0pI" frameborder="0" allowfullscreen></iframe>
</div>

-----

# Notes:

## SUMMARY

1. Gather Data
2. Get VIP Buy-In
3. Educate your team
4. Surface the data daily
5. Celebrate your victories  

## Some stats

- Percentage of total global internet traffic on mobile: ~40% in 2014 % in US: ~30% in 2013
- mobile networks add ~600ms of extra connection latency
people leave when your site is slow
- 40% abandon site when it takes more than 3s to load (find our bounce-rate stats on this)

## Options:

1. Ignore it
2. Assign performance cops (burnout, not sustainable)
3. Build a performance culture

## Culture:

- A way of identifying yourself and others.
- A way of thinking, social cueues.
- A way of doing
- A way of celebrating

Performance cultures are a team sport, everyone has to play.
culture change is scary and hard

## Real things said to Lara:

- “I don’t want to think about mobile”
- “Building for desktop and mobile takes twice as long”
- “Responsive web design is bad for performance”
- “Everything changes too fast”
- “But the important bit is above the fold!”

Determine spectrum of high-view screen sizes and shapes to determine policy  
**CHANGE IS CONSTANT AND IT IS GOOD**  

## So how do we create performance cultures?

- Gather data Know your traffic stats: devices, geography, user journeys. You can’t bring people onboard without understanding this story
- Know your load stats total load time and perceived load time (start render, speed index) use webpagetest
- Know your render stats memory usage, fps and jank

## Get the VIPs invested

- Share the data to enlist the help of your VIPs there are few things more powerful than getting important people invested in your subject
send VIPs perf conversion stats regularly
- “200ms delay = 0.3% engagement loss, etc”
know what kind of metrics the vip cares about
- “at etsy, +160kb pageweight = increased mobile bounce rate 12%”
(prefer positive stats)
- “When eliminated jank on activity feed, people favorited more often and more items (engagement metric)”
- Make an improvement, show video of difference to convert VIP to cause
compare site load locally to globally
- Get VIP to FEEL it, so they can empower others

## Performance is a team sport
- Equip team with what they need
- Team sport, get everyone involved educated
start documenting your best practices in a public place
- *“Doing things this way works because of this:”*
- Invest in a device lab
- Devicelab sandbox code is on github, pushes to all devices at same time
- **MAKE TIME FOR REAL TESTING**
- **EMBRACE RESPONSIVE**
- Teaching your team about their performance impact will empower them.

## Surface performance in people’s daily workflows

- **ADD PERF TO BUILD TOOLS**
- Automate image compression
- Get a command line tool running that runs performance tests and compares your new work to your performance budget
- (Have a performance budget). Build this into your continuous integration environment
- Use these tools to report back to dashboards
- Show start render and speed index on graphs over time (3 months)
- Use median times for load time stats
- Teams can release a feature, and then watch dashboard to see how it affected things

## Etsy's Perf toolbar
- Etsy has a perf toolbar at top of every page if you are logged in as an etsy employee. 
- It is a narrow strip, shows backend render time, start render, and something else to equal total load time.
- If one of the items fails the perf budget, it lets them know right there, with a link to the SLA that it violated .
- It provided a clear baseline for what’s acceptable.
- This is visible in dev, testing, and production environments
- **SURFACING YOUR TEAM’S PERFORMANCE DATA WILL IMPROVE THEIR WORK** (during their workflow)

## Celebrate your performance successes
- Celebrate everything that improves
- Seth Walker published Etsy’s performance on etsy’s business blog, super-public
homepage was a huge outlier, very slow
- As soon as that was published, people got excited about it, and the developers teamed up to fix it.
- By the next time they published a report, they had made a huge improvement, they dropped time from 1610ms to 480ms for home page

## SHARE YOUR FINDINGS
- Make sure you are celebrating externally the things that help you improve things along the way.
- Its important to do this internally as well. (they made a key person a performance hero for affecting the biggest change (“Baumgartner” load time drop on graph))
- Celebrate engineers and designers who make huge improvements to the products’ perf without being on perf team
- They celebrated with lots of high-5s, donuts and cake

## REWARD YOUR INNOVATORS
- Its not about coming down with a hammer, its not about being a cop or a janitor
- Its really about celebrating improvement and getting people excited and invested in performance
- **CELEBRATING WINS WILL MOTIVATE YOUR TEAM TO BE PERFORMANCE CHAMPIONS**

*This is a journey, will have to refresh the cycle constantly, it is continual*  
**WE ARE IN A PERIOD OF DRAMATIC CHANGE**

## Mobile traffic is going way up
- Performance-constrained devices becoming more popular
- Building for tomorrow/today means catering for “performance-constrained” devices
- You can only get there if EVERYONE in your organization CARES about PERFORMANCE

## TAKEAWAY: BUILD PERFORMANCE CULTURES
