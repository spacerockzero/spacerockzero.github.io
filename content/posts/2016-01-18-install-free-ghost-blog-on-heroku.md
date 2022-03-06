---
# layout: post
title:  "Install Free Ghost Blog on Heroku"
date:   2016-01-18
aliases:
- /install-free-ghost-blog-on-heroku/
# categories: blog-performance-series
# excerpt: "[video] Ghost is a blog engine built on NodeJS, that is super simple, fast, \
# and reliable. If you want a blog built with performance on the mind that is super-easy \
# to set up and fairly optimized out of the box, Ghost is a pretty good option right now. \
# You can also host your own deploy for free on Heroku's free platform using a pushbutton \
# deploy like what I'm about to show you."
---

**Blog Performance Series, Part 1**

Hi! I'm Jakob Anderson, and I'm going to show you how to install a Ghost Blog on Heroku, for free.

<div class="flex-video">
<iframe width="560" height="315" src="https://www.youtube.com/embed/P13AUfKqcsQ?list=PLWYz5kbNpmYUPTzgw8rhdAk64r4tH1Ynq" frameborder="0" allowfullscreen></iframe>
</div>

#### What's a Ghost Blog?

Ghost is a blog engine built on NodeJS, that is super simple, fast, and reliable. If you want a blog built with performance on the mind that is super-easy to set up and fairly optimized out of the box, Ghost is a pretty good option right now. You can also host your own deploy for free on Heroku's free platform using a pushbutton deploy like what I'm about to show you.

#### Requirements:

- Heroku account (will need to connect card to verify account, but free tier dynos won't cost money to use)
- [optional] Github Account (or other cloud-based git service)
- [optional] Amazon S3 bucket with API user keys (for hosting blog post images)

#### Install steps

- Go to [http://cobyism.com/ghost-on-heroku/](http://cobyism.com/ghost-on-heroku/)
- Click "Deploy Ghost to Heroku" Button
- Login to Heroku
- Select org, type appname, region, and input config vars below
	- Only `HEROKU_URL` is required. If you're putting a custom domain name in front of your Heroku app, you'll change the HEROKU_URL to match the new domain.
	- If using AWS S3 to store uploaded images, you need to fill out the S3 fields. `S3_ASSET_HOST_URL` is optional.

- Hit "Deploy for Free" button at bottom
- "Manage App" or "View"
- "Manage App" takes you to the app's Heroku dash page
- "View" takes you to the app's hosted web url, and forwards you to the admin setup page

#### Setup blog admin

- Clicking "View" will take you to something like: `{YOUR-HEROKU-URL}/ghost/setup/one/`
- Your blog's URL will be something like: `https://{BLOG-NAME}.herokuapp.com`
- Select "Create Your Account"
- Fill out info for admin account and blog title
- Click "Invite team to blog" (is optional, can pass through)
- Click "I'll do this later, take me to my blog!" at bottom

#### Create some content

Ghost made a sample blog post for you. Posts are authored in "Markdown" format, so they never need any buttons or UI to make things like headings, bold, italics, links, images, etc. This puts authoring content in center focus, with no distractions.

- You can click "edit" on the sample article to see how writing in Markdown works
- You can click "New Post" on the menu at left to make a new article
- Fill it out to your desire
  - Title
  - Content
  - Headings
  - Image
  - Links
- You can save your changes regularly by hitting ctrl-s on windows, or cmd-s on a mac, or by hitting that "Save Draft" button up in the top right
- Mess with important post meta by hitting that gear up in the top right as well
- Set a post image, change the post url, add tags, change author, edit and preview meta data for organic search results, and a couple other things
- To publish your post, click that button in the top right, and hit "Publish Now", then hit "Publish". Now it should say "Update Post" to update post with any new changes. You can also drop-down and "Unpublish" if you've made a horrible mistake.

#### Make some navigation items

- Hit "Navigation" on left side nav
- You already have a "Home" link. Follow that pattern to make another nav link to an existing public page on your blog, like the page we just made. If you need to know the urls of your current pages, it'll say under the gear menu of each blog while you're editing them.
- Go check out your blog with some content!
[https://jakob-ghost-test.herokuapp.com/](https://jakob-ghost-test.herokuapp.com/)
- If you are viewing your content page and you need to edit something, jump into edit by adding `/edit` to the page's url

#### Caveats

- On Heroku, the free tier has some limitations.
	- Your app will go to sleep when its' been idle for a bit.
	- For it to stay on the free tier, it MUST sleep at least 6 hours a day.
	- If the app is idle, it can take up to 20 seconds to wake it up.
	- It can only have one Dyno to scale. A Dyno is Heroku's name for a small micro-instance on a shared VM.
- Once your blog is pretty serious, you can upgrade to the "Hobby Tier"
- You can even attach your domain name to this Heroku app, and it works great!

#### Thank you

I hope you enjoyed this post and video, and got a pretty cool, free Ghost blog up and running. Feel free to [subscribe to this blog](/feed.xml) or to [my youtube channel and check out my other videos!](https://www.youtube.com/channel/UCMYju7_hZFd0qCN0RljjNYQ)
