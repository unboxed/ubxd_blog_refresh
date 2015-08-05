---
layout: "blog"
date: "2009-11-23 00:00:00 UTC"
published: true
title: "The curious incident of the named scope and the non-existent array"
author: "Jolyon Pawlyn"

---

Rails performance tuning is often a matter of SQL tuning but we recently stumbled upon code involving a named scope that caused more SQL to run than expected.

We were looking at an SQL trace in [New Relic RPM](http://www.newrelic.com/) for one of our apps when Nige and myself noticed what appeared to be duplicate SQL. The query was a monster (a monster in this case being a beast of over 20ft in height and over 2 seconds in length) so having it run twice was pretty ruinous even with fragment caching in use. To identify the cause, we used the [query reviewer](http://code.google.com/p/query-reviewer/) plugin which is fantastic and enables you to see the SQL being run for an individual page request in the browser window. As well as identifying inefficient SQL, it also shows at what point in the code SQL is fired.

The apparent duplicate SQL was running from a partial where there was a `products` variable set to a named scope. The partial contained:

`product = products.first
...
products[1..2].each_with_index do |product, index|
  ...
end `

At first glance it looks innocuous as `products.first` is meant as an alternative to `products[0]`. If `products` was an array the two statements would be equivalent but in this example, [`first`](http://api.rubyonrails.org/classes/ActiveRecord/NamedScope/Scope.html) is a named scope. It is chained together with the the named scope defined by `products` and has the affect of adding `LIMIT 1` to the executed SQL since `products` is yet to be populated. When `products[1..2]` runs, the same SQL is executed without the `LIMIT 1`.

To ensure that the SQL runs once, we used `products[0]` instead of `products.first`. By calling `products[0]`, the named scope is populated and subsequent calls including a call to `first` does not result in any SQL.


