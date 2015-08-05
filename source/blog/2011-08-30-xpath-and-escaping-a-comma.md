---
layout: "blog"
date: "2011-08-30 09:00:00 UTC"
published: true
title: "XPath and escaping a comma"
author: "Jolyon Pawlyn"

---

For those of you looking for the answer to how to escape a comma in an XPath text match, I'm sorry but I just don't know it. But if you are using Capybara, have no fear, there is a way round.

It was Friday afternoon and I was cleaning up some tests, and had the XPath:

`//ul[@id='stories_page']/li[@class='story_headline'][1]//p[2][text()='Posted by Clint Eastwood on Wednesday, 9 September 2009']`

The comma appearing after 'Wednesday' was causing all manner of havoc. Using the [XPath Checker](https://addons.mozilla.org/en-US/firefox/addon/xpath-checker/) Firefox add-on, I tried escaping it with backslashes, ampersands, a forty-four magnum (I was desperate) but no go. It was only when I can across this [capybara spec test for has\_xpath](https://github.com/jnicklas/capybara/blob/master/lib/capybara/spec/session/has_xpath_spec.rb) that the solution became apparent:

`have_xpath("//ul[@id='stories_page']/li[@class='story_headline'][1]//p[2]", :text => ``'Posted by Clint Eastwood on Wednesday, 9 September 2009'``)`

Although there was the [same solution](http://www.unboxedconsulting.com/blog/steak-vs-cucumber-as-bdd-tools) much closer to home. If anybody knows the answer to escaping a comma without Capybara, then please let us know. For once, Google failed me.


