---
layout: "blog"
date: "2010-05-30 00:00:00 UTC"
published: true
title: "CSS id and class naming"
author: "Simon Rentzke"

---

I'm a developer, I like structure, I like clean code, I like DRY code. I find writing CSS incredibly painful.

CSS1 was first published in December 1996, so I ask, why in 2010 does it feel like CSS is just as painful as it was 14 years ago?

[![](http://farm3.static.flickr.com/2461/3970138375_3e68095deb_o.jpg)](http://www.flickr.com/photos/popandshorty/)

A few great CSS tools exist to make the process of defining layout and structures much easier. &nbsp;A few different examples include; [Baseline](http://baselinecss.com), [Sass](http://sass-lang.com/), [Less](http://lesscss.org), [960](http://960.gs), [Yahoo! grids](http://developer.yahoo.com/yui/grids/)&nbsp;and [Blueprint](http://blueprintcss.org). Unfortunately nothing quite cuts the mustard. &nbsp;We've tried a few of these at Unboxed, but they still fail to some degree on the bigger projects.

Where are the standards? &nbsp;You can't lay all the blame on IE6 can you? Recently Jason Cale dedicated a fairly lengthy blog post to&nbsp; [why you should hit return whilst writing your CSS](http://jasoncale.com/articles/5-dont-format-your-css-onto-one-line).

A very simple problem I often find is what I should name different elements, and if I should use ids or classes. After often hearing the two [@ubxd](http://twitter.com/ubxd) CSS heroes Attila and Will have lengthy debates on the best way of doing things, &nbsp;I think the real answer is that there isn't one.

So I decided to look around the web, see what other people are doing, see what the top websites of the world were doing. &nbsp;I downloaded the top 1 million websites from [Alexa](http://www.alexa.com/topsites), and wrote a quick app that scrapes these sites, and tracks the top names used for ids and classes.

So here are the results (I stopped at 20000 results):

|  Top class results |
|  # |  Class |
| --- | --- |
|  3090 |  clear |
|  1946 |  logo |
|  1879 |  title |
|  1818 |  content |
|  1743 |  last |
|  1613 |  footer |
|  1582 |  right |
|  1582 |  text |
|  1562 |  left |
|  1471 |  first |
|  1467 |  button |
|  1331 |  header |
|  1187 |  more |
|  1179 |  search |
|  1131 |  copyright |
|  1124 |  menu |
|  1098 |  clearfix |
|  1000 |  active |
|  &nbsp; |  &nbsp; |

|  Top id results |
|  # |  ID |
| --- | --- |
|  5789 |  footer |
|  4622 |  header |
|  3170 |  content |
|  2555 |  logo |
|  2019 |  container |
|  1640 |  main |
|  1640 |  search |
|  1367 |  wrapper |
|  1268 |  nav |
|  1146 |  menu |
|  867 |  login |
|  865 |  top |
|  858 |  sidebar |
|  851 |  cse-search-box |
|  842 |  page |
|  817 |  copyright |
|  700 |  \_\_VIEWSTATE |
|  628 |  navigation |
|  &nbsp; |  &nbsp; |

&nbsp;

[![](http://farm2.static.flickr.com/1296/3424929417_b83f4bd2f8.jpg)](http://www.flickr.com/photos/stephenhackett/)

So, not that interesting I'm afraid. &nbsp;But what is interesting?

- Some of top ids are elements in HTML5 for example "footer", "header" and "nav" so we're making some progression in standards.
- The use of _id_ and _class_ seems to be used interchangeably, there really is _no_ common standard.
- We see heaps of sites using "footer" and "header" as a class name. Is that ok?

So even though the results are not too interesting, I think they serve as a little reference guide, so that in the future I can name things similarly to other people, so that other developers will be able to&nbsp;easily&nbsp;read my code.

&nbsp;

For more results check it out&nbsp; [here](http://severe-mist-97.heroku.com), thanks to the heroes at [heroku](http://heroku.com) for their servers that did all the grunt work.


