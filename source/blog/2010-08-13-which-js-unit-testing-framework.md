---
layout: "blog"
date: "2010-08-13 00:00:00 UTC"
published: true
title: "Which JS Unit Testing Framework?"
author: "Petr Zaparka"

---

As a ruby developer I'm used to using testing frameworks like Rspec or Cucumber. I started polishing an old project of mine recently, which is written in Ruby/js and using Sinatra. When I looked at the code I noticed that there is a lot of JS code without any tests and because I'm big fan of tests, I decided I would write some. But what JS testing framework is best for my needs? I hope that this post will answer that question.

Summarisation of my ideal Framework follows. I am looking for a browser based JS testing framework. The ideal syntax looks like Rspec. It supports nesting of "describe" blocks and installation has to be simple. It should be well documented with a lot of examples.

### Assumption:

- browser based
- simple integration
- easy configuration
- simple syntax

&nbsp;

<link href="http://gist.github.com/stylesheets/gist/embed.css" rel="stylesheet">
## FireUnit

[http://fireunit.org/](http://fireunit.org/ "Fireunit")

FireUnit is a Firefox / Firebug extension written by John Resig and Jan Odvarko. After you install the extension, all you have to do is to write the test and run it in the HTML file.

Short example of syntax follow:

<style lang="text/css" type="text/css">
.gist-syntax pre { font-size: 13px; }</style>

<script src="http://gist.github.com/519104.js?file=gistfile1.js" type="text/javascript"></script>

[![fireunit](/uploads/Image/fireunit.jpg)](/uploads/Image/fireunit.jpg)

You can also simulate browser events which is great.

<style lang="text/css" type="text/css">
.gist-syntax pre { font-size: 13px; }</style>

<script src="http://gist.github.com/519129.js?file=gistfile1.js" type="text/javascript"></script>

On the other hand FireUnit doesn't have proper documentation for the API. So if you would like to know what you can do with FireUnit you have to look at the code directly. Also the last commit at [FireUnit's github page](http://github.com/jeresig/fireunit "FireUnit's github page - http://github.com/jeresig/fireunit") is from October 2009 so there is no current developer community.

### Summary:

#### Pros:

- easy to configurate / install
- easy to integrate
- browser event emulation

#### Cons:

- Dependency on Firefox/Firebug
- Lack of documentation
- No longer actively being developed

&nbsp;

## QUnit

[http://docs.jquery.com/QUnit](http://docs.jquery.com/QUnit "QUnit")

QUnit is part of the jQuery project, but it can be used without jQuery. QUnit is maintained by Jörn Zaefferer and John Resig. After download quint.js and qunit.css from [http://docs.jquery.com/QUnit](http://docs.jquery.com/QUnit "Qunit source page") is very easy to start using it. Just link the QUnit js and css files at your HTML test and you can start. The documentation is written in jQuery style, so you can see examples too. If you are looking at the syntax, you will notice that the style is very similar to FireUnit (you can guess why).

<script src="http://gist.github.com/519159.js?file=gistfile1.js" type="text/javascript"></script>

Also it allows grouping tests into logical parts, you can use test blocks and module "scoping", similar to description at Rspec.

<script src="http://gist.github.com/519177.js?file=gistfile1.js" type="text/javascript"></script>

Output in browser:

[![qunit](/uploads/Image/qunit.jpg)](/uploads/Image/qunit.jpg)

### Summary Qunit:

#### Pros:

- easy to integrate
- well documented
- used for testing jQuery

#### Cons:

- non-Rspec-like syntax

&nbsp;

## QUnit + SpecIt

[http://github.com/joshuaclayton/specit](http://github.com/joshuaclayton/specit "QUnit + SpecIt")

QUnit looks good and the models are fine but what if I would like to use Rspec notation? No problem because there is wrapper called SpecIt written by Joshua Clayton and it looks exactly like Rspec as you can see below. To install SpecIt follow the installation of QUnit. After that, download spec.js from [http://github.com/joshuaclayton/specit](http://github.com/joshuaclayton/specit "Github page for SpecIt") and include the file into your test.

<script src="http://gist.github.com/519199.js?file=gistfile1.js" type="text/javascript"></script>

&nbsp; [![qunit](/uploads/Image/qunit2.jpg)](/uploads/Image/qunit2.jpg)

It looks almost perfect but it's still only wrapper and it's using jQuery. That means that you have to use 4 files to run it. Also some of the matchers are using object type specification for comparing. I just don't understand why I need that. I just want to compare two values and I don't want to specify their type.

### Summary QUnit + SpecIt:

#### Pros:

- easy to integrate
- well documented

#### Cons:

- too many dependencies (jQuery, QUnit)
- matchers with object type specification

&nbsp;

## JSSpec

[http://jania.pe.kr/aw/moin.cgi/JSSpec](http://jania.pe.kr/aw/moin.cgi/JSSpec "JSSpec - JavaScript BehaviorDrivenDevelopment Framework")

Alan Kang's JSSpec looks like JS clone of Rspec except that it didn't allow nesting. To install, download zip file from [http://code.google.com/p/jsspec/downloads/list](http://code.google.com/p/jsspec/downloads/list "JSSpec source page") and unpack jsspec.js, diff\_match\_patch.js and css file to proper directory. Then just link the files in your HTML and you can start writing tests.

<script src="http://gist.github.com/519203.js?file=gistfile1.js" type="text/javascript"></script>

[![jsspec](/uploads/Image/jsspec.jpg)](/uploads/Image/jsspec.jpg)

JSSpec has the handy feature of allowing the re-running only a specific test. Another useful part of JSSpec are predefined constants for rendering engine (JSSpec.Browser.Webkit), platform (JSSpec.Browser.Mac) or browser (JSSpec.Browser.IE6).

### Summary JSSpec:

#### Pros:

- easy to integrate
- re-running specific tests
- very Rspec like including matchers

#### Cons:

- Don't allow nesting of descriptions

&nbsp;

## JSpec not a JSSPEC :)

[http://visionmedia.github.com/jspec](http://visionmedia.github.com/jspec/ "JSpec JavaScript Testing Framework")

[https://rubygems.org/gems/jspec](https://rubygems.org/gems/jspec "JSpec JavaScript Testing Framework")

JSpec written by TJ Holowaychuk is different from previous frameworks. Firstly you can install it as a gem or download as a whole package. These versions are different, while the gem version didn't contain jspec's files because he copied them to /Library/Ruby/Gems/1.8/gems/jspec-4.3.2/ (might be different on your system), the package (zip or tar) version contains everything. Because running JSpec could be little bit tricky I describe the basics here.

After installing gem, create you directory for project

    jspec init name_of_project
      Jspec contains one test by default so after command
      jspec run

you should see:

[![jspec](/uploads/Image/jspec.jpg)](/uploads/Image/jspec.jpg)

but if you don't have Safari set as a default browser than you can see this error: NETWORK\_ERR: XMLHttpRequest Exception 101

to fix that just run

    jspec run --browser Safari

The test code is located at spec/spec.js or at unit/spec.js - depends on the version you have installed. JSPEC syntax is very clean and Rspec like.

<script src="http://gist.github.com/519207.js?file=gistfile1.js" type="text/javascript"></script>

You can nested "describe" blocks, use before block just beautiful.

[![jspec](/uploads/Image/jspec2.jpg)](/uploads/Image/jspec2.jpg)

There are lot of matchers from JSpec and jQuery. JSpec also allows you to stub methods, mock the XHR object, use Fixtures or JSON Fixtures. You also can add your own matchers. JSpec is the most advanced testing framework that I ever seen before. On the JSpec website there are lots of examples and some screencasts so you can learn more if you are interested.

### Summary JSpec:

#### Pros:

- basic support for method stubbing
- XHR mocking
- matchers(jQuery, your own)
- very good documentation with examples

#### Cons:

- maybe to complex?

&nbsp;

## YUI 3: Test

[http://developer.yahoo.com/yui/3/test/](http://developer.yahoo.com/yui/3/test/ "YUI 3: Test - testing framework for browser-based JavaScript solutions")

This testing framework is based on YUI 3 library from Yahoo!. First thing that little bit surprised me was that after you include script definition with YUI API URL, the YUI instance will automatically download the Test's source files and any missing dependencies for your test. You can download the source by yourself but you have to satisfied possible dependencies. For this reason YUI provide "YUI dependency configurator". Lets assume that you include the YUI API URL, now there is another surprise. You have to create YUI instance. Then everything that you are doing, is inside that instance. So to write a test you need a Test Case instance and inside this instance you can finally create tests. After you are done you have to add the Test Case into Runner object and then call the run method of the Run object. Then just specified how you would like to view the result you can select from options like: console, XML, JUnitXML, JSON, TAP (Test Anything Protocol - http://testanything.org/wiki/index.php/Main\_Page). in the following example, I selected output to the console.

<script src="http://gist.github.com/519209.js?file=gistfile1.js" type="text/javascript"></script>

And this is result in console:

[![yui](/uploads/Image/yui.jpg)](/uploads/Image/yui.jpg)

As you can see it's not really nice. In spite of complicated configuration YUI provide lot of handy features like mocking, errors handling, asynchronous tests, DOM event simulation and various types of handlers.

### Summary YUI 3:

#### Pros:

- lot of great functions
- tear down support
- good documentation

#### Cons:

- bad formatting of result
- more complicated syntax / setup

&nbsp;

## JsUnitTest

[http://jsunittest.com/](http://jsunittest.com/ "JsUnitTest - JavaScript Unit Testing framework")

This JS framework by Dr Nic Williams is based on unittest.js from prototypejs but it's not dependent on that framework, the whole JsUnitTest is one JS and one css file. You can download "getting started package" which includes the library files and example HTML with basic test template.

<script src="http://gist.github.com/519212.js?file=gistfile1.js" type="text/javascript"></script>

I was unable to find documentation so I looked at the [github page](http://github.com/drnic/jsunittest/tree/master/test "Github page")) where there are lot of examples. As you can see below JsUnitTest using standard assert syntax for tests.

<script src="http://gist.github.com/519214.js?file=gistfile1.js" type="text/javascript"></script>

[![jsunittest](/uploads/Image/jsunittest.jpg)](/uploads/Image/jsunittest.jpg)

JsUnitTest contains all the assert matchers that you would expect and it provide lot of examples how to use them.

### Summary JsUnitTest:

#### Pros:

- easy to configure
- tear down support
- lot of useful examples
- TextMate bundle.

#### Cons:

- no documentation - you have to look at the github project page

&nbsp;

## Jasmine

[http://pivotal.github.com/jasmine/](http://pivotal.github.com/jasmine/ "Jasmine - Simple DOM-less JavaScript testing framework")

Jasmine is written by Pivotal Labs and as authors says they wrote Jasmine because: "We needed something that supported asynchronous specs, didn't depend on any one framework, and didn't depend on the request/response cycle of a web application."

You can install Jasmine as a Gem or download standalone version.

### Standalone version

After unpacking files, open SpecRunner.html in your browser and you should see this screen:

[![jasmine](/uploads/Image/jasmine.jpg)](/uploads/Image/jasmine.jpg)

Example test can be found in spec/SpecPlayer.js using customer matcher that you can create in spec/SpecHelper.js

Test template: <script src="http://gist.github.com/520783.js?file=gistfile1.js" type="text/javascript"></script>Example of custom matcher: <script src="http://gist.github.com/520784.js?file=gistfile1.js" type="text/javascript"></script>

### Gem version

After installation of Gem:

    gem install jasmine
     script/generate jasmine

You can run test in browser by:

    rake jasmine

This will start the Jasmin server on http://localhost:8888/ where the output is the same as above.

&nbsp;

Jasmine looks pretty good, you can write your own matchers, you can use stabbing (createSpyObj method) and mocking (createSpy method), it's well documented but it could have more examples in documentation.

### Summary Jasmine:

#### Pros:

- gem or standalone version
- customisable matchers
- describe blocks

#### Cons:

- only few examples

&nbsp;

## Screw.Unit

[http://github.com/nkallen/screw-unit](http://github.com/nkallen/screw-unit "Behavior-Driven Testing Framework for Javascrip")

Screw.Unit written by Nick Kallen and it's used by Blue Ridge Rails plugin. Screw.Unit is dependent on jQuery. The test style of Screw.Unit is to use nested describes aka Rspec.

<script src="http://gist.github.com/521013.js?file=gistfile1.js" type="text/javascript"></script>

You can write your own matchers and specify their error messages.

<script src="http://gist.github.com/521023.js?file=gistfile1.js" type="text/javascript"></script>

Or you can extend functionality of Screw.Unit:

<script src="http://gist.github.com/521026.js?file=gistfile1.js" type="text/javascript"></script>

After running the basic test template you will see the classic result table(but in nice pastel colors):

[![](/uploads/Image/srew-unit.jpg)](/uploads/Image/srew-unit.jpg)

What is little bit sad is, that you have to download whole source code, because there is no prepared package, also I was unable to find documentation. The biggest thing is that last commit is from 2008 so this means the jQuery is out of date.

### Summary Screw.Unit:

#### Pros:

- customisable matchers
- extendable by subscribing to certain event

#### Cons:

- out of date
- missing documentation

&nbsp;

## Which one to use?

It depends very much on what are you looking for. For small simple project I would use QUnit + SpecIt. Because it's very easy to integrate and it offers everything you would expect from basic tests.

For more robust testing I would suggest JSpec or Jasmine. Jspec and Jasmine contain a more extended test environment with mocking, stubbing, etc.

And that's all. You may be asking where Env.js is. Env.js is not JavaScript testing framework but a browser simulation environment. There are lot of other testing frameworks but I select only those major ones and of course this blog post ignores the many non browser based testing frameworks which may will be more suitable for Ruby/Rails projects. If you still think that I should mention your favourite one, be my guest and post a comment.


