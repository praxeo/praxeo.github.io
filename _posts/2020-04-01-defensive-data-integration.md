---
title: Five Rules For Defensive Data Integration
layout: post
---

A lot of the work I do when I'm wearing my developer hat is scheduled jobs that transfer data
from one system to another. Usually a customer within the organization has found a helpful
third party tool, and wants it to be populated with relevant data from our organization without
having to schlep Excel files on their own or hand-enter thousands of records.
Instead, an automated task, maybe written in Python or with the help of Talend Studio, can
get the job done on a regular schedule and save them a lot of time and agony.

Having done this kind of thing about a dozen times or more, I've noticed a few patterns and
anti-patterns, so I'll share them with you here. Hopefully this lets you learn these lessons
the easy way -- from someone else's example -- rather than the hard way.

### Rule 1 -- Understand the expectations and must-haves as early as possible.

### Rule 2 -- Assume the data specification will change before you're done.

### Rule 3 -- Intercept failures before the end-user notices them.

### Rule 4 -- Deal with them automatically if at all possible.

### Rule 5 -- You *do* have time to build a testing harness.

The book *Code Complete* has an excellent chapter on what they call "defensive programming."
