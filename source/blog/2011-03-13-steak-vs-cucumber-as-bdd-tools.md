---
layout: "blog"
date: "2011-03-13 16:08:00 UTC"
published: true
title: "Steak vs Cucumber as BDD tools"
author: "Petr Zaparka"

---

When I joined the world of Ruby on Rails development and testing I was quite happy with all the tools and testing frameworks available, I was using a lot of them during development process. Words like Rspec and Cucumber quickly became part of my vocabulary, along with other 'magic' words like Kanban and Scrum. BDD, or ' [Behaviour Driven Development](http://en.wikipedia.org/wiki/Behavior_Driven_Development)'&nbsp;became a permanent part of my life!

It's crucial for a project, that the features that a customer would like to have implemented into the finished product are captured as well defined stories early on. We'll eventually use these stories as a template for our tests. Cucumber is an especially good tool for using these stories as templates for testing. So what is Cucumber and what does it look like?

Here's the explanation on [Cucumber's own wiki](https://github.com/cucumber/cucumber/wiki).

Cucumber is a tool that executes plain-text functional descriptions as automated tests. The language that Cucumber understands is called Gherkin.

Here is an example:

<script src="https://gist.github.com/868229.js?file=cucumber_feature.feature"></script>

As you can see, Cucumber allows you to easily describe the behaviour of your new feature. In fact, it's that good that some of our customers are using Cucumber descriptions as the acceptance criteria on their project's stories. So where's the catch? Well, not everything in cucumber is as easy as it may look. Even though cucumber has lot of pre-defined "phrases" to describe the behaviour of an application, you soon find out that sometimes it can be really tricky to preserve the readability of stories that are more complex than just: "And I should see 'a yellow box" for example. When it gets tricky it gets really time consuming. And even if you know that implementing the related functionality is really easy - writing the proper, readable cucumber test that makes sense is sometimes very hard.

I'm not complaining about writing tests in general. I'm complaining about how hard it is sometimes to achieve basic readability of tests! Does the average customer really have to understand the tests we use? If they do, then ok - I'm here and I'm prepared to write those nice, readable tests for them.&nbsp;

But what if they don't care? Well there is another way around: the solution is called Steak.&nbsp;

So what is [Steak](https://github.com/cavalle/steak)?

Steak is an Acceptance BDD solution (like Cucumber) but in plain ol' Ruby. This is how an acceptance spec looks in Steak...

<script src="https://gist.github.com/868232.js?file=steak.rb"></script>

As you can see, there is a Feature description and a Scenario description, but the rest is Ruby language with Capybara syntax. But why do I think this is so special, and why do I think you should use it? Well it's much, much faster to write those complex, yet readable tests, and it's easy to maintain.

Recently, I was working on a tough project where I was the only back-end developer and there was one front-end developer; let's call him Tom. At the start of this project we were using Cucumber. It took such a long time to write some of the tests, and because there were a lot of front end changes, we had to fix and re-write a lot of these Cucumber tests. Tom found he wasn't that comfortable writing Cucumber scenarios, so it took him longer to fix them. At the start of the new iteration, I decided to use Steak instead of Cucumber. I discussed with Tom how Steak works, and he preferred it immediately. We started implementing new stories and development suddenly went really well and much quicker. I was writing Steak stories much faster, and Tom was faster too. So, by the end of the iteration there was no complaining about fixing Cucumber stories, and there was a lot more delivered functionality; them were some good times.

Is it Steak final solution?

Maybe, maybe not. It really depends on you and your customer's needs, but what you really should do is to try it out yourself. You will see how much faster your development process can became.


