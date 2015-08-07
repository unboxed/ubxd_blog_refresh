---
layout: "blog"
date: "2013-05-15 09:32:00 UTC"
published: true
title: "Max attempts for a single delayed_job Job"
author: "Pawel Janiak"

---

[Delayed\_job](https://github.com/collectiveidea/delayed\_job), the asynchronous priority queue system has a well documented configuration for setting the max number of attempts a worker will run for jobs in the queue:

# config/initializers/delayed\_job\_config.rb Delayed::Job.destroy\_failed\_jobs = false silence\_warnings do Delayed::Job.const\_set("MAX\_ATTEMPTS", 3) Delayed::Job.const\_set("MAX\_RUN\_TIME", 5.minutes) end

There is also a way to get more granular control over attempts at a job level instead of the worker level. This is defined in the [base class](https://github.com/collectiveidea/delayed\_job/blob/master/lib/delayed/backend/base.rb) of the gem.

Delayed\\_job first checks to see if the payload\\_object of a job has a max\\_attempts value and if it doesn't it falls back to the max\\_attempts value defined in the worker.

So all you have to do is to define an instance method in your payload\\_object's class for the max number of attempts for a job:

def max\_attempts; 1; end

 Voila!


