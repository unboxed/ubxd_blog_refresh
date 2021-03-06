---
layout: "blog"
date: "2012-03-11 00:12:00 UTC"
published: true
title: "Gemnastics with ActiveRecord"
author: "Christopher Patuzzo"

---

Recently, I've been building gems in an attempt to get some content out into the open-source community and learn a thing or two along the way.

![Ruby gems](http://i39.tinypic.com/fazklk.jpg)

There was one in particular that gave rise to some interesting challenges. The bulk of the gem involved parsing a complex data structure, manipulating it in some way, then composing it back to the **fathoms of complexity from whence it came**. In plainer terms; it reads a file, does all the things, then writes a file- still with me? In this instance, the domain of the problem was scheduling. Not particularly enthralling on the surface, but when observed from an architectural disposition, it had some challenging characteristics. The web of associations between data, as well as the fragility of the software pertaining to it meant that a more comprehensive solution would be required.

How would you approach a problem like this? Well, I reached into my toolb0x and pulled out modularity, validation and test-driven development, as well as various ingrained programming patterns. My thinking was that if I decoupled components stringently, **I could deal with the tangled mess of data one piece at a time.** Validation and test-driven development would ensure I didn't break anything along the way. It seemed the ActiveRecord interface would be the way to go. We use ActiveRecord almost every day at Unboxed Consulting as it is an intrinsic component of the Ruby on Rails framework that deals with databases.

**It is possible, however, to use ActiveRecord without Rails.** This meant I could make use of the 'magic' functionality it provides, such as the dynamic 'find\_by' methods and scopes- very useful for constructing complex queries. One feature that is often overlooked is the ability to build in-memory databases when utilising the SQLite adapter. This has the advantage of being incredibly fast, and doesn't require much setup. In this scenario, it was perfect because there were fixed end-points to the flow of operations. I didn't need to persist a database on disk once a file had been written.

After a huge amount of reverse engineering, I had a set of models that accurately represented the data structure. I had investigated edge-cases, leading to thorough validations and I was confident in my code as I'd undergone TDD for the duration. In isolation, it worked perfectly. I wrote a lengthy Readme and pushed version 0.0.1 to Rubygems. **Job done, or so I thought...**

It was about a week later when showing my gem to Attila, that I realised I hadn't tested it in the context of a Rails application. Rails projects tend to 'lock' their versions of ActiveRecord to ensure things don't suddenly break one day, due to incompatibilities. I'd built my gem on the latest version of ActiveRecord and now needed to test it with a large back-catalogue of different versions. Thankfully, my comprehensive test-suite allowed me to find and fix any problems with relative ease.

The final obstacle was running my gem, or more specifically, my in-memory database side-by-side with a Rails database. The general solution for this is to establish a connection on a subclass of ActiveRecord::Base. This works well for reading from an existing database, but not so well when creating your own tables. This is mostly due to how ActiveRecord determines which connection to build your schema on. Without going into too much detail; one final, relatively simple, subclass was **all that was left on my path to victory!**

At the time of writing, my gem is on version 0.0.4, and isn't a whole lot more than a minimum viable product. However, I now have the foundations in place to incorporate new features incrementally. If you'd like to read more or contribute, you can find the Github project page [here](https://github.com/tuzz/xteam_schedule).


