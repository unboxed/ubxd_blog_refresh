---
layout: "blog"
date: "2010-11-22 00:00:00 UTC"
published: true
title: "Not so cool as cucumber"
author: "Jolyon Pawlyn"

---

 **The problem**

There's just one tiny validation to add to a user model. The impact on the application code is small whereas the impact on the test code is enormous. The change takes a day to implement.

**The context**

A large code base, Rails 2.3.2, Test::Unit, Cucumber and an unhealthily long test suite execution courtesy of Cucumber.

**Possible solutions**

1. Decide that tests are so last year and scrap the lot.
2. Decide that Cucumber is too dangerous to handle and is best left for crudités, salad and Pimms.
3. Decide that Rails ain't cut out for building large web sites and start over with PHP or Python.
4. Decide that you have more [carnivorous](https://github.com/cavalle/steak) tastes with regards to testing.
5. Decide to jettison Cucumber in favour of Webrat, Test::Unit and Shoulda.
6. Accept that whenever Cucumber is used to comprehensively test a complex and large web site, problems of maintainability are inevitable and decide to address the problem with judicious use of Cucumber.

Against the interests of impartiality, I'm only considering solution 6 except to say that solution 5 addresses test execution speed and is quicker for developers to write than Cucumber (thanks to [Simon](../../../people/simon-rentzke) for pointing this out). Assuming RSpec or Test::Unit coverage is comprehensive then Cucumber should be used sparingly in such a way that you maximise the bang for your buck. Although [37signals](http://37signals.com/svn/posts/2555-podcast-episode-20-programming-roundtable-part-1-of-3) don't use Cucumber and [others](http://rubypond.com/blog/you-dont-win-friends-with-salad) are sceptical, Unboxed has found it invaluable and this difference may be in part due to the type of web sites we build and who we build them for.  
  
 If the time it takes to run a test suite can sensibly be reduced by refactoring or running tests in parallel then this is the best option. If not or it only yields limited time savings then every line of Cucumber should be treated as a valuable and scarce resource. [Ben](/people/ben-wong)'s suggestion is to limit the number of feature files or total number of lines so that a new product owner can realistically read through the feature files and gain a good understanding of an apps functionality. When the limit has been reached, any new Cucumber has to be matched by removing less consequential Cucumber scenarios.  
 &nbsp;  
 One final point to consider. A lot of Rails development involves working on a new app or enhancing existing sites that are not large scale hence it may seem irrelevant to constrain your use of Cucumber. However if your site increases in size and complexity and technology improvements do not decrease test execution time at the same rate as lines of Cucumber increase, then sooner or later pain will creep up on you. Where's the pain threshold? Well [a ten minute build](http://martinfowler.com/articles/continuousIntegration.html#KeepTheBuildFast) is a good goal to aim for.


