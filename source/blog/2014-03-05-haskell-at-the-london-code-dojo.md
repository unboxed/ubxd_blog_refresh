---
layout: "blog"
date: "2014-03-05 19:10:00 UTC"
published: true
title: "Haskell at the London Code Dojo"
author: "Henry Turner"

---

[Sleepy Fox](https://twitter.com/sleepyfox) recently ran the London Code Dojo here at the [Unboxed](http://www.unboxedconsulting.com/) office. The evening's Dojo was based around a few parts of Day 1 of the Haskell section of [Seven languages in seven weeks](http://pragprog.com/book/btlang/seven-languages-in-seven-weeks). It was good fun and I recommend the next Dojo coming up!

One of the problems we attempted was, in my words, the following:

Given the colours black, white, blue, yellow and red, find all unique pair combinations ignoring the order of the colours within each pair.

So, examples of valid pairs are (black, black), (black, white), (yellow, red) etc. As for invalid pairs, we can have (black, blue) \_\_or\_\_ (blue, black) but not both. Ok.

Haskell syntax is pretty mind bending for my mushy human brain but the implementation for the colours problem turned out to be pleasantly readable!

let colours = ["black", "white", "blue", "yellow", "red"]

[(x,y) | x concatMap (\ y -> if x


