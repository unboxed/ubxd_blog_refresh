---
layout: "blog"
date: "2009-10-22 00:00:00 UTC"
published: true
title: "Less is More"
author: "Attila Gyorffy"

---

At Unboxed we are continuously checking the latest tools which enhance Rails application development.  
  
 Being a front-end specialist I am always keen on different approaches which make front-end development easier and more enjoyable. In recent years, the science of CSS and the need for semantic XHTML has become much more complex but the CSS specifications don't provide enough for large projects.

### The problem

CSS is the language for everyone, and therefore does not provide some of the key features of programming languages used in large teams/on complex projects which help quick and bug free development, such as constants and expressions. CSS is great, but after a small time working on large projects, you quickly learn its limitations. CSS files can easily become bloated and hard to maintain unless extreme care is taken.

### The solution

One of the best things about being a Ruby/Rails developer is that you are part of a community which never rests. Every day someone comes up with better tools to enhance web development. "Extending" CSS through a pre-compiler really is not a new concept. If you've worked with CSS and pre-compilers before you've probably come across [SASS](http://sass-lang.com) ('Syntactically Awesome Stylesheets') which is meant to serve the purposes mentioned above.

SASS really is a great tool, but its syntax differs so much from the original CSS that it is unfamiliar and results in a high learning curve for new developers.

There is a new kid on the block. [Less](http://lesscss.org), created by [Alexis Sellier](http://twitter.com/cloudhead), is a new attempt at a CSS pre-compiler. Less allows you to do the same as SASS and more importantly its syntax **resembles CSS** , which you are already familiar with, making it exceptionally easy to pick up.

Less is exactly what CSS would be if it was a programming language. It extends CSS with constants, mixins, operations and nested rules adding a big boost to your CSS development. It provides **constants** to define widely used values which you can re-use. Making global changes across your style definitions becomes a matter of changing one line of code. It's saving us from a lot of headaches!

    @brand_color: #4D926F;
    #header {
      color: @brand_color;
    }
    h2 {
      color: @brand_color;
    }

You can also apply the same philosophy to whole classes using **mixins** to embed all properties to another ones. That is quite handy if you are applying behavioural definitions to multiple elements.

    .rounded_corners {
      -moz-border-radius: 8px;
      -webkit-border-radius: 8px;
      border-radius: 8px;
    }
    #header {
      .rounded_corners;
    }
    #footer {
      .rounded_corners;
    }

Adding **expressions** into the mixture makes Less even more fun. Expressions come in handy if certain elements in your stylesheet are proportional to others allowing you to deal with complex relationships between properties. You can add, subtract, divide and multiply different values:

    @the-border: 1px;
    @base-color: #111;
    #header {
      color: @base-color * 3;
      border-left: @the-border;
      border-right: @the-border * 2;
    }
    #footer { 
      color: (@base-color + #111) * 1.5; 
    }

Less is also really great at code maintainability. Rather than constructing long selector names to specify inheritance, in Less you can simply **nest selectors** inside other ones. This makes inheritance clear and style sheets shorter and well-constructed.

    #header {
      color: red;
      a {
        font-weight: bold;
        text-decoration: none;
      }
    }

Less is under heavy development and there is also a [Rails plugin](http://github.com/cloudhead/more) for it which automatically parses your applications .less files through Less and outputs CSS files.

Head over to [github](http://github.com/cloudhead/less) and start experimenting with it. At Unboxed we've already started making some changes to Less to reduce its dependencies and made it more robust when included in an application. You can check out [our changes](http://github.com/unboxed/less) to Less on our github account.

As you can probably see now it is really a great tool and makes CSS development a piece of cake in Ruby/Rails applications. One small caveat, though; Less won't deal with your IE6 problems. You still have to sort them out yourself.


