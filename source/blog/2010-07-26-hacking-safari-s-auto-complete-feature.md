---
layout: "blog"
date: "2010-07-26 00:00:00 UTC"
published: true
title: "Hacking Safari’s auto-complete feature"
author: "Attila Gyorffy"

---

Update:

The recently released update to Safari (version 5.0.1) seems to fix the security issue described below.

Jeremiah Grossman [points out](http://jeremiahgrossman.blogspot.com/2010/07/i-know-who-your-name-where-you-work-and.html) a serious security issue that he recently found in Safari.

You probably know about Safari’s autocompletion feature that makes filling in web forms a piece of cake by mapping the input names to their corresponding entries in your Address Book card.

Basically using a small piece of JavaScript anyone could essentially detect and steal your personal information, including your name, address and email. This can be done by either navigating to a website that has a script like this running a background or by injecting an external script to any website using XSS technique. (The former one is a bigger security issue, the latter one can be avoided by escaping user generated data so make sure to do this at all times.)

There is a [proof of concept code](http://ha.ckers.org/weird/safari_autofill.html) so you can see this yourself.

I’m afraid at the time of writing this blog entry I can confirm that this security hole still exists in the latest official version of Safari (Version 5.0, 6533.16), however it seems like this issue has been addressed and fixed in the latest [nightly build of WebKit](http://nightly.webkit.org/) (Version 5.0, 6533.16, r63958). You might be asking yourself if this issue affects Google’s Chrome that happens to be using Apple’s WebKit under the hood, but it didn’t expose personal data while running the tests. Mobile Safari is also unaffected because its behaviour is different.

The issue can be addressed manually by disabling this functionality in Safari’s preferences under the AutoFill tab.

![](/uploads/Image/safari-autofill.png)

![](/uploads/Image/1qoIaJ.safari-autofill.png)

This issue affects Safari version 4 and 5, with about 4% of combined market share (~83 million internet users) and has already been reported to Apple. ~~We are hoping that they are going to release a new official version very soon that contains a fix. Given the relatively aggressive automatic system update feature built into OS X, the patch should spread across most users’ computers.~~ Apple recently released an update to Safari (version 5.0.1) that has fixed the security issue.

&nbsp;


