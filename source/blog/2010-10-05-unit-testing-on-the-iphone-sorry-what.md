---
layout: "blog"
date: "2010-10-05 00:00:00 UTC"
published: true
title: "Unit testing on the iPhone"
author: "Borja Arias"

---

![](/uploads/Image/iphone_with_code.jpg)

Developing for the iPhone can be quite fun. You get very mature frameworks to work with that do an extensive use of design patterns and you also get a fancy an highly tuned platform to play with.  
  
 But there's something I'm missing from the ruby community: the must test culture. If you have a look at some of the cocoa open source projects pages on the Internet you'll find very hard to find fully or even partially unit tested apps. The community seems to lack that culture that makes ruby developers test. I don't believe this is due to language specifics. For example ruby doesn't check the types or doesn't have a compiler to look after you. That's just the blue print. You also need to test the bulk of your application. Thus, In my opinion the real and simple reason of this differences are trends, fashions, people looking at you dodgy because you didn't write tests or even people making you feel cool because you did write tests. &nbsp;Communities are big creatures with a lot of power but hard to put in motion.  
  
 Therefore, I would like to share an example on how to unit test one of the most common components in an iPhone app, a TableViewController. It's simple but illustrates a way to solve the problem. To make it more realistic, the TableViewController &nbsp;will get the data from a fetchedResultsController which uses the CoreData framework. The project includes some helper classes to abstract the Core data stack and make it easier to test.

You can find the sample at&nbsp; [github.com/unboxed/Unit\_Testing\_Controllers\_Iphone](http://github.com/unboxed/Unit_Testing_Controllers_Iphone)

&nbsp;


