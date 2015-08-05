---
layout: "blog"
date: "2011-03-09 08:45:00 UTC"
published: true
title: "Kanban in the Cape - Part 1"
author: "Kevin Pedersen"

---

After reading the book 'Kanban and Scrum - Making the most of both' (Henrik Kniberg & Mattias Skarin, 2010), I was quite eager to give Kanban a try on a project. All I needed was a project that had fantastic clients that understand the kanban process, and a fantastic development team who are willing to go crazy and give the process a chance.

<meta content="text/html;charset=UTF-8" http-equiv="Content-Type"><meta content="text/html;charset=UTF-8" http-equiv="Content-Type">

Fortunately for me, I work for Unboxed Consulting! The guys here in the Cape Town office are often called crazy, and are definitely willing to give new processes a chance, especially when I told them for this project, there will be no planning involved, but more on that later.

The project could have been more of a problem, but as it happens, we had a couple of weeks break between paying clients on which we planned to do some work on our own internal Timesheets application. Perfect! An internal client who understands what we want, and is willing to give kanban a try.

So how did we do it? Well, kanban is very similar to scrum in many ways with the main difference being that you restrict the amount of stories in each column on the task board.&nbsp; I started out with the ‘In Spec’ column where all the stories start out. This column has no limit as when a story is first written it goes here. Next to that column is a ‘Ready for Dev’ column.

<meta content="text/html;charset=UTF-8" http-equiv="Content-Type"><meta content="text/html;charset=UTF-8" http-equiv="Content-Type">

![kanban board](/uploaded_assets/inline-images/000/000/003/display_size_IMG_0258.JPG?1299661499)

For this project we had 2 teams of paired programmers that swap partners every day, so for the ‘Ready for Dev’ column I put a limit of 2 stories, 1 for each pair. This means that as Scrum Master I can decide which of the stories in the ‘In Spec’ column should be developed next and put 2 of them in the ‘Ready for Dev’ and the developers can choose which of those 2 to do next. This cuts down on the cherry picking of stories and helps the more important stories to get done first.

<meta content="text/html;charset=UTF-8" http-equiv="Content-Type">

After a story failed a test we also saw the need of having a ‘Needs a Fix’ area. This area is where stories can be put ready for a developer to pick up and fix, so it made sense to make it a sub column of the ‘Ready for Dev’ column, and if a story is put there, adhering to the ‘2 stories max’ rule of ‘Ready for Dev’ you have to move one of the stories out of that column back into ‘In Spec’ as fixing a story takes priority over starting a new story.

Next up was the ‘Development’ column. This column was also split up into 2, ‘In Progress’ and ‘Done’ sub columns. When a developer starts a story, they move it from the ‘Ready for Dev’ into the ‘Development – In Progress’ column. Once they have finished the story, shift it across to ‘Done’ and pick up the next one. It’s the testers job to move it from the ‘Done’ column into testing. As we want the developers to be as active as possible, I put a limit on the ‘Development’ column to 4, to allow for an ideal 2 items in progress and 2 done. If a developer finishes a story and there are still 2 stories in ‘Done’ then there will be 1 ‘in Progress’ and 3 in ‘Done’. This means they cant pick up a new story, as there is no more space allowed. ‘What’???? You might cry, ‘that’s stupid’!! Ah, but no, that’s the whole beauty of kanban, we’ve just discovered a bottleneck at testing and found out where our process is being held up. So instead of the developers starting a new story, they should help out the tester and get some stories passed! Then once a free slot has been made, they can start the next story ready for development.

Next up, testing! The testing column is a mirror of the ‘Development’ column, but as there was only 1 tester on the project, I put a limit of 2 stories allowed in test at any one time. After the testing column is a ‘UAT ‘column, which again is an exact mirror of the ‘Development’ and ‘Testing’ columns. Finally there was a ‘Done’ column where all the stories happily reside once they have passed UAT.

Planning, it all comes down to planning, unless you use kanban! One way of implementing kanban is to not estimate a story, yes, that means no horrendous planning poker sessions! This means that we don’t assign an amount of points to a story. How then do you get your velocity? How do you know if you are going to finish your allocated stories on time? Well the way it works is to mark a date on when a story first gets moved to the ‘Ready for Dev’ column, and then mark the date when it is completed. This gives you an idea of how long it takes for a story to be completed. If you do this for say 3 stories, then you have a rough idea of how long on average a story takes to complete, and then obviously how long it will take for all the stories to finish.

So that’s how we organised our first kanban project in the Cape Town office. The project is still ongoing, and when its finished I’ll blog about how it went and what we learned, and especially what we will do differently next time!&nbsp;


