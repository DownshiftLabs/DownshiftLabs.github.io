---
layout: post
title: Monkey-patching Ruby Responsibly
excerpt: Spree Commerce had a big problem and I had a humble solution. See the open source extension that uses the canary pattern to make monkey patching durable. 
subhead: Look at <b>the source</b>

featured: yes
---

SpreeConf 2013 was an awesome time. 

However, there was an air of concern with the community as a whole. The prolific monkey-patching happening left-and-right in Spree extensions is volatile and non-sustainable. 

After a brief chat with [Brian Quinn](https://github.com/BDQ) and [Ryan Bigg](http://ryanbigg.com/) of SpreeCommerce regarding the issue, I had an approach in mind and gave everyone my word I'd go home and do my best to conjure up a solution.

Two months later I sent my first commit to a new open source Rubygem I called **durable_decorator**. It is now in production for a number of Spree powered stores and doing exactly what it says. 

## What is a durable decoration, anyways?

I had specific goals in mind and I've achieved them all:

 -   Override class-level instance-level and module method definitions
 -   Warn the user if what they were decorating has changed and requires their review
 -   Maintain a history of all overrides
 -   Have a way to invoke each of the versions of the method at runtime
 -   Make the library usable when authoring Spree extensions
 -   Have 2 modes of oepration: strict mode that rauses exceptions and a sort mode that simply issues log warnings

Check out the [documentation](https://github.com/jumph4x/durable_decorator) and see if you'd like to give it a go. If you're managing a large Spree store like me, you're going to want to see what all the fuss is about.

## SpreeConf 2014 Ligthing Talk

I delivered a brief talk about the design and benefits of this project at SpreeConf in New York and you can check out the slides [here](http://slid.es/jumph4xx/durable-decorator).

## I don't feel like it...

I know you're busy. So am I. That's why I wrote a [Rails connector](https://github.com/jumph4x/durable_decorator_rails) that does all the legwork.

Specifically, with this connector you can run a Rails generator that will generate the correct folder structure, create an override file, decorate the correct method, seal it with the correct hash and let you simply type in the custom behavior!

Additionally you can just run a rake task that will print the hash of the method definition as it is loaded into memory.


Enjoy! And may your Spree projects be more durable hereonafter.

_(Although, technically, this is usable in any Rails/Ruby project that does a lot of monkey-patching.)_
