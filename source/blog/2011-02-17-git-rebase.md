---
layout: "blog"
date: "2011-02-17 17:41:00 UTC"
published: true
title: "Git rebase"
author: "Tom ten Thij"

---

Many people new to git wonder: "what is rebasing?" and "why would I use rebase?". Following is my attempt at an answer to those questions.

Git lets you easily mess around with branches. A branch is just a set of commits with a branch name pointer to the last one. Now if work done by another developer and your work share a common commit, at some point you'll need to bring the two together.

One way is merging which creates an additional merge commit in which all the changes are incorporated with any conflicts resolved. Note that if you do this, the branching and merging will still be visible in the history of the repository.

Another thing you can do is rebasing. My mental model for this is like a replay of commits: one by one your changes are applied, but instead of applying them to the original commit that you started from, it starts from the last commit of the other branch. At the end of that it is like there never was any branching and all the commits you made were done*after* the other dev's work.

So one difference between merging and rebasing is that merging gives you a better overview of how code was produced, whereas rebasing results in a 'cleaner' history.

Because the parent of a commit determines its SHA1, if you rebase you also change all the SHA1s of your commits. This is why you should not rebase any commits that were already pushed to a shared repository.

Why rebase? Sometimes I just like the cleaner history of my work. But also: it can be a very powerful tool to make a bunch of messy commits look like you knew what you were doing all along. The git rebase -- interactive command allows you to rearrange, join up or edit commits to your heart's content.


