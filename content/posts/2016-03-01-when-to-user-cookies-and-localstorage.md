---
# layout: post
title:  "When to Use Cookies and LocalStorage"
date:   2016-03-01
aliases:
- /when-to-use-cookies-and-localstorage/
- /when-to-user-cookies-and-localstorage/
# categories: best-practices
# excerpt: "There are good practices and bad ones when it comes to persisting data \
# across parts of a web stack, whether you want to use cookies, localStorage, \
# sessionStorage, or whatever else. I go through some of the use cases, and their best practices."
---

Problem: I need to persist data.

## When to use localstorage:

- I need to persist data for just my client-side code. This will always be stored at domain-global scope.

## When to use cookies:

- I need to persist & share data with my server-side code. This can be from client to server or server to server. This can be page, app, or global-mounted scopes.

## Local-storage Best Practices:

- A global domain (https://mysite.com) has to share [less than 5MB of localStorage on the devices with the lowest quotas](http://www.html5rocks.com/en/tutorials/offline/quota-research/). Be a good neighbor. 
- LocalStorage doesn't have its' own expire system, so embed storage/expire timestamps in the objects your store and set up a mechanism for garbage-collecting it when it is old. 
- Use the API correctly. To store things, store objects or strings with `window.localstorage.setItem('myKey','myValue')` or `window.localstorage.setItem('myKey',myObject)`

## Cookies best-practices:

- Browser limits on cookies per domain are as low as 4KB. It's easier than you think to hit this limit when using global cookies for lots of things. 
- We need to use these bytes more wisely, especially because they are transmitted as headers on every request per domain. 
- Always use the existing cookie methods to get, set, and unset cookies, to avoid obliterating any other mission-critical cookies or writing excess code to solve the same problem

## Mount on tightest scope you can. 

- Cookies are transmitted on every request that shares its' domain. If all the cookies are set on the "/" domain, they will be transmitted with EVERY request that browser makes to every app and endpoint also mounted on that same domain. 
- If you only need to persist the data on a page, mount the cookie to the page's scope ("/photos/people"). If you need to persist the data across multiple pages of your app, mount it to your app's scope ("/photos/"). If you need to persist the data across multiple apps/routes, you can mount the cookie at the domain root "/"

### Shortest Expires.

Set expires for as short a time as possible. If possible, use session cookies (expire after tab close or navigation off). This will help the cookie disappear once it is not being used anymore, taking it's performance cost along with it.

### Store only when you really need it.

Default states and most common settings should not set cookies, we should only store the exceptions. If 99% of users have `frog=true`, you should only set and check for a cookie when `frog=false`, so that only 1% of users incur the performance penalty while the cookie is being used.

### Store as few bytes as possible.

- Your cookie names and keys should be short and unique. Save space on character length, but when mounting in the global domain, be sure your cookie name won't collide with someone else's. 
- You should use a library to condense and unpack the cookies if you have any complex data, so you're transmitting as few bytes as possible, while not manually handling the formatting each time.
- Do not use json, use form-encoding (a=1;b=0) or querystring (a=1&b=0) format. JSON is extremely wasteful on character length once you have encoded it properly. The other formats use far fewer characters, and are easy to encode/decode and read without the size ballooning. 
- When storing true/false values, use 1/0, to save bytes. 
- Combine multiple similar settings into one cookie, rather than having a cookie for each key/value pair. This also helps with organization and DRY code. For example: exp: a=0;b=1; 

