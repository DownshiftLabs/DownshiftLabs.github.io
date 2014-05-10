---
layout: post
title: Talk on Tuning Frontend Performance for UX
excerpt: I delivered a talk on improving the overall user happiness by speeding up the slowest part of any webapp - the frontend.
subhead: The audience <b>loved</b> it

featured: yes
---

After attending the [first ever SpreeConf in NYC](http://spreecommerce.com/blog/best-spreeconf-ever) and listened to the presenters, I told myself "I can do this". But I didn't act on that impulse until much later.

When the time came to submit talks to SpreeConf 2013, I looked at what I was working on and submitted an abstract about raising the technical bar of the frontend markup we put before our users.

The 2014 version of this talk was filmed at the NYC SVA threatre and is available online for free:
<iframe width="853" height="480" src="//www.youtube-nocookie.com/embed/nXD9DycK4gY?rel=0" frameborder="0" allowfullscreen></iframe>

The slides used are available on [Slid.es](http://slid.es/jumph4xx/frontend-things).

## Summary

 -   Getting the most from your frontend, in my cases will mean tuning for performance. 
 -   Steve Souders is THE frontend performance evangelist and has written great books on the topic
 -   I take performance seriously in my projects
 -   Use these tools to benchmark your progress: [Pingdom Full Page Test](http://tools.pingdom.com/fpt/), [Chrome's Network Inspector](https://developers.google.com/chrome-developer-tools/docs/network) and [Google Pagespeed Analyzer](https://developers.google.com/speed/pagespeed/)
 -   CSS selectors play a role in frontend performance and are actually parsed right-to-left
 -   The fastest selectors user #ids or .classes as the far-right-most piece, which is called the **key selector**
 -   Each additional selector beyond the key one requires the traversal up the DOM tree
 -   The fewer elements match the selector, the faster it is
 -   Use [CSS Explain](https://github.com/josh/css-explain) to develop good CSS selector intuition
 -   Be careful how you [mis-]use SASS, always check the end output to make sure it is generating sane selectors
 -   JavaScript performance is important but not as simple to optimize
 -   Asset delivery and network topics play the biggest role in the perceived performance of a webpage
 -   Load layout/presentation-critical CSS as the very first thing in your HTML HEAD
 -   Load scripts asynchronously using the 'async' attribute and load them as late as possible in the HTML
 -   Minimize the nnumber of HTTP requests to cut down on DNS resolution and network latency times
 -   Use built-in Asset Pipeline features to concatenate and compress otherwise separate assets
 -   Use image sprites to reduce number of served images
 -   Embed (that's right!) images directly into your CSS files by using the **asset-data-url** helper
 -   Use SVG fonts to embed icons that can be losslessly colored/sized using CSS
 -   Use asset domains to save on the cookie overhead and trick the browser into opening more concurrent http connections
 -   Use CDN services to reduce HTTP latency and cache assets at critical pipeline locations
 -   [advanced] Reduce time-to-first-byte by enabling streaming responses in Rails
 -   Use prefetch (and even pre-render) meta HTML tags to give browsers hints on what is coming next
 -   Instead of taking paid SEO advice at face value, spend the time reading Google's Webmaster Academy
 -   Make URL's trimmable, take advantage of RegEx matching in the Rails router to make URLs look great
 -   Canonicalize your content! Hint: [I wrote a gem for that](/2013/08/22/rails-content-canonicalization-gem.html)
 -   Mark up your content semanticallyand test it using the [Google Rich Snippets Tool](http://www.google.com/webmasters/tools/richsnippets)
 -   Use content pages with high existing SEO and build a topnav that distributes the visitors (and PageRank) back through the rest of the site

Remember, you can always hire me to implement any of the ideas above.

Good luck with optimizing your front-end, your users will love you for it.
