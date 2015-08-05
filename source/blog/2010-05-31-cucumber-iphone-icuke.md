---
layout: "blog"
date: "2010-05-31 00:00:00 UTC"
published: true
title: "Cucumber + iPhone = iCuke"
author: "Rob Holland"

---

Ever wish you could write Cucumber stories for iPhone applications the way you do for web apps? Well now you can, thanks to Unboxed's [iCuke](http://github.com/unboxed/icuke).

[iCuke](http://github.com/unboxed/icuke) allows you to write integration tests for your iPhone applications without changing your existing code (as long as your application makes proper use of the accessibility APIs).

Usage is pretty much as you'd expect, install the gem and load the iCuke step definitions in a cucumber support file:

<style lang="text/css" type="text/css">
.gist-syntax pre { font-size: 13px; }</style><script src="http://gist.github.com/373728.js?file=iphone.rb"><noscript><a href="http://gist.github.com/373728?file=iphone.rb">iphone.rb</a></noscript></script>

Then you can write scenarios like:

<script src="http://gist.github.com/373729.js?file=iphone.feature"><noscript><a href="http://gist.github.com/373729?file=iphone.feature">iphone.feature</a></noscript></script>

iCuke builds on work by Matt Gallagher and Ian Dees to make integration testing iPhone applications as painless as possible. Applescript is used to drive XCode to launch your application under the iPhone Simulator. An embedded webserver is used to determine what is showing on the iPhone's screen and to emulate taps/swipes etc.

For an application which adheres to Apple's accessibility guidelines no changes to the application's code are required, and there is no need to make any changes to configuration in XCode.


