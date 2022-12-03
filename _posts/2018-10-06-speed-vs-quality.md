---
layout: post
title: Speed and Quality
excerpt: Should speed and quality be mutually exclusive?
tags: [Technology, Startup, Speed, Qualty, Engineering]
comments: true
canonical_url: 'https://www.abhinav.co/speed-vs-quality'
---
Speed vs Quality is a common debate in engineering and product organizations and though it is hard to move at speed while maintaining quality, but I believe it is not completely impossible. Here are some tips (in no specific order) to balance between the two
* Understand the product vision, and then engineer MVP or first version. Aim should be to develop an extensible but not the eventual system on day one. Focus on getting an end-to-end happy flow working, then edge cases, and then new scope changes.
* Do enough but do it well.
* ABC - always be closing. Minimize number of things in flight, if given multiple tasks simultaneously, always ask for priority.
Be open about writing use and throw code.
* Know what to do on server and what do on client. Initiate cross-team collaboration from planning stage.
* Don’t over-engineer (premature optimization is root cause of all evils.)
* Know when to hack and when not to hack. Know difference between good hacks and bad hacks. Keep them modular and separated from other code to allow easy refactoring/removing.
* Understand difference between tech-debt and bad code. Tech debt is something which is stopping you from moving at optimal speed; if not, it's just non-ideal/bad code. Don't try to fix it.
* Remember, tech-debt occurs when you take shortcuts and tightly couple your code. To take shortcuts, make sure to modularize your changes as much as you can.
* Leave the campground cleaner than you found it. No big refactoring projects, but continuous refactoring. If a feature takes 5 days to build, and refactoring a piece surrounding that takes 1 day - take 6 days and refactor.
* First make system correct and then make it efficient and not vice-versa (Correctness over Efficiency.)
* Though perceived otherwise, but practices like unit testing, code reviews, architecture reviews and automation helps in gaining speed while maintaining quality. Unit-test your code, and invest in automation. Find high-quality reviewers, and take feedback from at least a couple of them.
* Use a task tracking tool, and be religious about it.
* Be pro-active, and push information to other stakeholders early and more frequently. Being on same page helps a lot both with speed and quality. On a similar note, ensure silos are not formed - they give you speed in shorter term, but slow you down in longer term.
* Do frequent releases - if there are frequent releases, it automatically helps in avoiding scope creeps. Product owners know that they will get a chance to add changes in next release if changes don’t go in this release. This also means, that release dates need to be sacrosanct and if there’s a delay, everybody involved is informed as soon as possible.

> It is a mistake to think that moving fast is the same as actually going somewhere.
> ― Steve Goodier 
