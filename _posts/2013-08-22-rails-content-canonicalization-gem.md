---
layout: post
title: Rails Page Canonicalization Gem
subhead: Production <b>tested</b> 
excerpt: See the open source Rails helper I wrote to safeguard your application against improper content canonicalization.

featured: yes
---

At some point in my flagship eCommerce project, it became clear that content canonicalization was becoming an issue we needed to contain.

After spending some honest time researching the issue via means of various Google resources, I had an idea on what needed to be done. What came of it took the form an open source Rails gem called [Canonical Rails](https://github.com/jumph4x/canonical-rails).

The main idea behind the gem is to **give the user a safe (read: conservative) foundation to begin canonicalizing content** that is in-line with the Rails url conventions. Specifically, this means two things:

 -   generating a configurable initializer
 -   provides a template helper to insert the canonical HTML tag

## What is content canonicalization?

Google content evangelists will probably [explain](http://googlewebmastercentral.blogspot.com/2009/02/specify-your-canonical.html) [it](https://support.google.com/webmasters/answer/139394?hl=en) [much better](https://support.google.com/webmasters/answer/139066?hl=en) but here's my quick summary:

> It is a way for you to communicate with search engines regarding which pages are new, original content and which ones are duplicates or derivatives based on the former

This may not sound like a big deal; however, things like extra HTTP parameters or interchanging adding www. to the domain technically make it an entirely different URI. 

Canonical Rails will allow you to whitelist parameters, meaning it will signal to SEs that the parameter does indeed change the content. It will assume all other parameters are to be ignored. 

Additionally, it imposes a *NIX resources locator convention: it will add a trailing slash to resource listing endpoints (:index actions and such), much like the folder structure convention. End resources such as :show actions will not have a trailing slash. For maximum impact, use this with nested trimmable URIs!

Good luck on your next project.
