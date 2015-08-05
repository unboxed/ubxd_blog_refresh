---
layout: "blog"
date: "2011-03-09 08:45:00 +0000"
published: true
title: "Kanban in the Cape - Part 1"
author: "Kevin Pedersen"

---

<p>After reading the book &#39;Kanban and Scrum - Making the most of both&#39; (Henrik Kniberg &amp; Mattias Skarin, 2010), I was quite eager to give Kanban a try on a project. All I needed was a project that had fantastic clients that understand the kanban process, and a fantastic development team who are willing to go crazy and give the process a chance.</p>
<meta content="text/html;charset=UTF-8" http-equiv="Content-Type" />
<meta content="text/html;charset=UTF-8" http-equiv="Content-Type" />
<p>Fortunately for me, I work for Unboxed Consulting! The guys here in the Cape Town office are often called crazy, and are definitely willing to give new processes a chance, especially when I told them for this project, there will be no planning involved, but more on that later.</p>
<p>The project could have been more of a problem, but as it happens, we had a couple of weeks break between paying clients on which we planned to do some work on our own internal Timesheets application. Perfect! An internal client who understands what we want, and is willing to give kanban a try.</p>
<p>So how did we do it? Well, kanban is very similar to scrum in many ways with the main difference being that you restrict the amount of stories in each column on the task board.&nbsp; I started out with the &lsquo;In Spec&rsquo; column where all the stories start out. This column has no limit as when a story is first written it goes here. Next to that column is a &lsquo;Ready for Dev&rsquo; column.</p>
<meta content="text/html;charset=UTF-8" http-equiv="Content-Type" />
<meta content="text/html;charset=UTF-8" http-equiv="Content-Type" />
<p><span class="Apple-style-span" style="font-size: 10px; line-height: normal; "><img alt="kanban board" src="/uploaded_assets/inline-images/000/000/003/display_size_IMG_0258.JPG?1299661499" style="width: 380px; height: 284px; " /></span></p>
<p>For this project we had 2 teams of paired programmers that swap partners every day, so for the &lsquo;Ready for Dev&rsquo; column I put a limit of 2 stories, 1 for each pair. This means that as Scrum Master I can decide which of the stories in the &lsquo;In Spec&rsquo; column should be developed next and put 2 of them in the &lsquo;Ready for Dev&rsquo; and the developers can choose which of those 2 to do next. This cuts down on the cherry picking of stories and helps the more important stories to get done first.</p>
<meta content="text/html;charset=UTF-8" http-equiv="Content-Type" />
<p>After a story failed a test we also saw the need of having a &lsquo;Needs a Fix&rsquo; area. This area is where stories can be put ready for a developer to pick up and fix, so it made sense to make it a sub column of the &lsquo;Ready for Dev&rsquo; column, and if a story is put there, adhering to the &lsquo;2 stories max&rsquo; rule of &lsquo;Ready for Dev&rsquo; you have to move one of the stories out of that column back into &lsquo;In Spec&rsquo; as fixing a story takes priority over starting a new story.</p>
<p>Next up was the &lsquo;Development&rsquo; column. This column was also split up into 2, &lsquo;In Progress&rsquo; and &lsquo;Done&rsquo; sub columns. When a developer starts a story, they move it from the &lsquo;Ready for Dev&rsquo; into the &lsquo;Development &ndash; In Progress&rsquo; column. Once they have finished the story, shift it across to &lsquo;Done&rsquo; and pick up the next one. It&rsquo;s the testers job to move it from the &lsquo;Done&rsquo; column into testing. As we want the developers to be as active as possible, I put a limit on the &lsquo;Development&rsquo; column to 4, to allow for an ideal 2 items in progress and 2 done. If a developer finishes a story and there are still 2 stories in &lsquo;Done&rsquo; then there will be 1 &lsquo;in Progress&rsquo; and 3 in &lsquo;Done&rsquo;. This means they cant pick up a new story, as there is no more space allowed. &lsquo;What&rsquo;???? You might cry, &lsquo;that&rsquo;s stupid&rsquo;!! Ah, but no, that&rsquo;s the whole beauty of kanban, we&rsquo;ve just discovered a bottleneck at testing and found out where our process is being held up. So instead of the developers starting a new story, they should help out the tester and get some stories passed! Then once a free slot has been made, they can start the next story ready for development.</p>
<p>Next up, testing! The testing column is a mirror of the &lsquo;Development&rsquo; column, but as there was only 1 tester on the project, I put a limit of 2 stories allowed in test at any one time. After the testing column is a &lsquo;UAT &lsquo;column, which again is an exact mirror of the &lsquo;Development&rsquo; and &lsquo;Testing&rsquo; columns. Finally there was a &lsquo;Done&rsquo; column where all the stories happily reside once they have passed UAT.</p>
<p>Planning, it all comes down to planning, unless you use kanban! One way of implementing kanban is to not estimate a story, yes, that means no horrendous planning poker sessions! This means that we don&rsquo;t assign an amount of points to a story. How then do you get your velocity? How do you know if you are going to finish your allocated stories on time? Well the way it works is to mark a date on when a story first gets moved to the &lsquo;Ready for Dev&rsquo; column, and then mark the date when it is completed. This gives you an idea of how long it takes for a story to be completed. If you do this for say 3 stories, then you have a rough idea of how long on average a story takes to complete, and then obviously how long it will take for all the stories to finish.</p>
<p>So that&rsquo;s how we organised our first kanban project in the Cape Town office. The project is still ongoing, and when its finished I&rsquo;ll blog about how it went and what we learned, and especially what we will do differently next time!&nbsp;</p>
