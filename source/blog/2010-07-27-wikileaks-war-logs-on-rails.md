---
layout: "blog"
date: "2010-07-27 04:00:00 UTC"
published: true
title: "Wikileaks war logs on rails"
author: "Tom ten Thij"

---

I assume that everybody has now heard about the [wikileaks](http://wikileaks.org) [war](http://www.guardian.co.uk/warlogs) [logs](http://www.nytimes.com/interactive/world/war-logs.html) [leak](http://wardiary.wikileaks.org). I thought this was a nice opportunity to hack together a Rails app that contains the data that was leaked. Hopefully this will be a good resource for people to play around both with the data and with Rails.

The app itself is not very exciting at the moment, all it does is read the original 76911 military cables into the database and show them on a page with pagination.

The amount of data is rather overwhelming, but there must be a lot of human stories buried in there - both tragic and heroic. I hope that with the help of others and with more spare time I will be able to dig out some of that humanity.

&nbsp;For now: just some raw stats on the total number of people killed and wounded in action:

|  &nbsp; |  WIA |  KIA |
|  Civilian |  9044 |  3994 |
|  Host Nation |  8503 |  3796 |
|  Friendly |  7296 |  1146 |
|  Enemy |  1824 |  15219 |

The source can be found on github:&nbsp; [http://github.com/tomtt/wikileaks\_wardiary\_on\_rails](http://github.com/tomtt/wikileaks_wardiary_on_rails)

An online demo can be found here:&nbsp; [http://www.war-logs-on-rails.com](http://www.war-logs-on-rails.com)

Many thanks to wikileaks for their hard work and Julian Assange in particular, for truly sticking his head out for this.


