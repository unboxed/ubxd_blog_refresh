---
layout: "blog"
date: "2012-02-15 14:40:00 UTC"
published: true
title: "Forcing Facebook to Update Your Site's Metadata"
author: "Alan Thomas"

---

Recently we launched a new site for one of our customers:

[http://www.thiswaytoamazing.com/](http://www.thiswaytoamazing.com/)

Up until the launch date we had been re-directing the URL to a different site. The only problem was that the page had a 'like' button on it, and when people clicked 'like' on the newly launched site, the post came up in Facebook with the correct URL but all the wrong metadata - i.e. the metadata there was from the site we had redirected to. This had happened as Facebook had scraped the site and stored the metadata it had found when the redirect was in place and Facebook only checks back periodically to see if the metadata has changed.

The customer was obviously complaining that their Facebook posts were wrong!

What do we do? Shrug our shoulders and say it's a Facebook thing? Ignore the customer's calls until Facebook bothers to scrape the site, crossing our fingers that it won't be long?

No, here's the solution: you can use the Facebook Linter to force the page to be scraped again, by cURLing it:

`curl https://developers.facebook.com/tools/lint/?url={YOUR_URL}&format=json `

Give Facebook a couple of minutes to do it's stuff and bingo, happy customer, problem solved.

Could be quite handy if you ever come across this situation or refresh a site in any way that will change the metadata.


