---
layout: post
title: Bad cache design can be a thorn as you grow
description: "This is the man, a lion's doctor"
categories: cloud cost
author: Abe Winter
noindex: true
---

Have had interesting conversations with a bunch of friends in the last few months about their
mis-architected cache that was creaking at the seams and needed to be replaced.
My observation is that the solution is generally simple when someone puts pen to paper,
but also that people wait waaay too long to start fixing these because they undercount the cost of inertia.

I'm not sure how interesting this will be to a wider audience; my particular bubble understands these problems well (though not well enough sometimes).

But the 'wait too long' piece caught my attention because it's at the intersection of management and technical planning,
so here I go.

* toc
{:toc}

## These problems last a long time

There are real organizational reasons why these problems don't get solved.

Part of it is that migration is hard, and can be demotivating for teams if not individuals.
These opposing forces can be parallel -- there's the one person who's constantly bringing their language or infra migration to team syncs, and everyone else is grumbling.
Migrations bring up 'not broke don't fix' arguments that are impossible to resolve without napkin math and a thorough understanding of how deeply the system in question has penetrated your codebase.

Small teams with good access to money but limited butts in seats have a specific version of this problem:
they're cash-rich, time-poor, and so infrastructure expense has to be egregious before a refactor seems justified.

I think this interpretation is often short-sighted, but there are ways to make it work out on paper.
Companies in this situation read their incentive as 'don't fix' so they can maximize feature work.
In my opinion the underlying issue here is that you have a large infrastructure payroll but nobody on the team dedicated to ops.
It probably means that you're under-accounting for the amount of weekly pain and maintenance your feature devs are doing on your shaky infra.

## Wrong tools for jobs

You start using the wrong tool for the job because:

- You had one datastore and the dev who needed a cache didn't have AWS permissions to add a second (most pathological case of this: have seen people -ahem- me check data into git for this reason)
- Team or dev not familiar with caching (less common these days)
- Someone doesn't want to have a design / cost discussion with the team because of urgency to get this out or workload
- It made sense when you were small

Here's the *non* defensible reason to use the wrong tool:
you didn't do napkin math to price out your workload.

Napkin math feels like a superpower to me sometimes;
it can get a room out of bikeshedding mode,
it brings experts from different domains together,
and you even learn from it when it's wrong.

## Lots of good reasons to fix

Because under-accounting plays such a big role in creating and maintaining stack / architecture problems,
I think people underestimate the value and urgency of fixing them.
You can be in a mode where all hands are on deck for feature work, which is fine.

But ask yourself these questions:

- Is there a future breaking point where this fills up and causes downtime and urgent maintenance? if you don't know where that is, you're in trouble
- Has it failed more than once due to over-use
- Does your awkward architecture lead to more complicated application code to work around it?
- In particular, is there something awkward about your TTLs -- you never expire, or you have a manual vacuuming job
- Does your architecture cost more than a developer at your current scale, and are you growing?
- Could architecture savings move you from losing money to breakeven

If yes to any of these, it's worth at least doing your homework + napkin math-ing the plan to fix.
Waiting for a failure that you could have predicted is bad strategy.

{% include flatpixel.html %}
