---
layout: "blog"
date: "2012-04-25 12:52:00 UTC"
published: true
title: "Code maintainability - is it a test thing?"
author: "Andrew Mitchell"

---

![All code is guilty until proven innocent](http://farm8.staticflickr.com/7239/7112521903_1a6df93dee.jpg)

It has come to my attention of late that there is some clear separation in the testing world about how we write our tests and the level they are written at. &nbsp;In this separation I see 2 groups of people:

- The first group enjoy testing their applications at each level of the stack; model tests for models, controller tests for controllers, view tests for views, or if you prefer integration tests to test the integration of models, views, and controllers and all your other code as a whole, in a much more high level fashion.&nbsp;

- The second group prefers a slightly more loose approach to testing; they favour the approach of testing components of their application less in isolation, comparable in some sense to integration testing alone. Let’s take an example of a simple Cucumber approach to testing to demonstrate what I mean:

```
Feature: Viewing a blog post:
  Given A blog post "post 1" exists with title: "Testing is for winners!"
  And I am on the page for blog post "post 1"
  Then I should see "Testing is for winners"
```

Some of you may consider this subtle, but by testing at this level we have already tested other components of our application implicitly. The above example already means that our application is testing that we not only have a model on which we can store the details of our post, but also that the model has a title attribute, controller show action and a corresponding view.

In the real world we all know that this kind of testing works, and by cutting out the other tests that we would have had to write for our models, controllers, and views, we may have saved a significant amount of development time in the process. It doesn't take a genius to see the advantage of this from both a client's point of view and a "making life easier" point of view.

However I do see a major flaw in this kind of testing; using the above example as a starting point. Imagine these are the only tests we have and 6 months down the line we decide to add some new models and relationships, such as a category. We may also decide to add some conditional logic in the views around displaying the category to the user. &nbsp;So, to make sure I test this logic I extend my feature as follows:

```
Background:
  Given a category "cat 1" exists with name: "TDD"
Feature: Viewing a blog post:
  Given A blog post "post 1" exists with title: "Testing is for winners!"
  And I am on the page for blog post "post 1"
  Then I should see "Testing is for winners"
  And I should see "TDD"
```

Now, those of you with a keen eye will already notice that our post has not been related to the category. Without writing any code, we run our tests and sure enough it fails, but where? First of all, nothing fails at the creation stage, but instead our tests fail at the stage where we expect to see the category name on the page. So immediately we jump to the conclusion that our view logic is incorrect. We continue to spend time working out that this is not the root of the issue, but is merely a problem elsewhere.

In reality, this scenario is simple and it’s very easy to spot the issues immediately. In fact, in a test driven fashion this would take moments to realise and our problem would be resolved.

Take the given example above, multiplied by a gazillion, and mix it in with the most complicated combination of tests you have ever seen, with a large modular application and spaghetti code all over. It may seem obvious but a simple test at the model level to say that something should be validated means that on running our tests we immediately see where the issue is actually caused. On large scale, complicated projects the benefit of these simple, "overkill" tests is invaluable. It will also save you from looking a fool in front of your peers when they realise that you just spent 3 hours trying to work out why the post category wasn't showing and you simply forgot the relationship!

So, in conclusion: Write tests at ALL levels. Just because it’s tested by way of some other abstraction does not mean that there is no use to the isolation of simple unit tests. Save us tearing our hair out over one or two missing tests as it will probably take you less time to write than it will take the poor soul who debugs it later!


