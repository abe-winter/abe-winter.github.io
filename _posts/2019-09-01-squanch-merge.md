---
layout: post
title: Squash merge makes chaining PRs hard
description: "Get thee behind me, 'request changes' button"
author: Abe Winter
noindex: true
---

There was a period last year where I was reviewing more code than I wrote and I found myself saying things like:

* You have to ship smaller PRs
* This is too large to merge safely
* Separate the major refactors from the feature change, that will make review easier
* What's the one thing this PR supposed to be touching?

Today I'm adding one more request:

* Ignore me

## Small PRs with squash merge kill productivity

Because they will typically force a complicated merge.

Imagine I split my big PR (new library code, use that library code in features) into two medium PRs.

Even if PR 1 gets approved, I **squash to master** and try to merge master into my PR 2 branch. This is not a straightforward merge -- despite being identical content-wise, it will trigger a merge conflict or an 'approve every change' rebase experience. Git doesn't understand the provenance for squashes.

And god forbid anyone requests changes on PR 1. Now we're looking at a merge that's not just messy, it's dangerous. Things get lost. And whatever productivity you gained with smaller PRs is lost with this adventure.

Even if the merge algo weren't a problem, dealing with the impact of PR 1's review changes down the chain of 1 or 2 linked PRs is going to be a lot of work.

Am I saying don't squash merge? I'm on the fence. I'm saying the tools aren't pulling their weight.

## PR review is generally costly

I think dev teams optimize for perfection here and underestimate the cost of multiple review cycles, especially with slow CI in the picture or a release deadline. I'm very reluctant to hold up urgent work for naming nits. I've had people introduce a cycle of work for me for a whitespace change.

One reason people like `gofmt` so much is that it makes some arguments moot, letting teams focus on actual work. I've used this defense in codebases with less opinionated linters: "I don't take a side on style changes but if you want to enforce this, add a linter rule."

I'm always pro making changes as follow-on PRs rather than as merge blockers because they can be scheduled in the workstream or (fingers crossed) forgotten about because they're not important.

(I'm a huge hypocrite so I still do all the hateful things I described above).

Sometimes I review PRs that introduce high-level design changes that I don't like. There I feel very tempted to push back, but it's hard: unless I have direct ownership of that part of the product, it's not appropriate for me to throw the work in the trash. It's usually not a good idea for me to write code in someone's PR unless I have a specific objection ('this will break in prod').

From an alcoholism perspective, PRs are often the "accept the things you cannot change" part of the triad. Lacking the "wisdom to know the difference", I default to acceptance. Get thee behind me, 'request changes' button.

## Next-gen VCS

The general problem here is that pipelining work is harder than doing it linearly. There's more to keep track of. But tracking details and catching simple mistakes is what computers are good at.

Review tools / VCS can support us better by supporting splitting and identifying patterns in PRs like:

* renames
* moving something between files
* change in indentation of a block ('ignore whitespace' kind of does this)

Having a history of those things would make refactors cheaper, easier, and safer. And when review tools can compress the noise, I can focus on the signal.

Separately, review tools can do a better job of splitting PRs without splitting branches. I've never used gerrit / phabricator but I'd expect they can do this.

## Better tooling matters

It's hard to justify building new tools because the payoff is so far in the future. Even adopting new ones is costly and uncertain.

But there's a 'do we want to live like this' argument that said enough times leads to revolution.

If you're not using the best tools, that takes its toll every day. Any tools shortcoming that impacts cycle time is **very costly**, and you should be careful to analyze it honestly. My model for this is that you only have so many cycles before you get interrupted, and while marginally slower cycle time will delay delivery, significantly slower cycle time can turn 'later' into 'never'.

By 'cycle' I mean both PR cycles and develop/test/run cycles. A slow rebuild here can kill you. By 'interrupted' I mean by the day ending, by lunch, by a meeting -- we don't have large blocks of time anymore and while it's stupid & wasteful to live this way, it seems to be the new normal and better tools can help us adapt.

'Tomorrow' and 'never' are basically synonyms. I like the line [time is not important, only life important](https://www.youtube.com/watch?v=DrB9ciZTxyo) from that movie because with slow productivity at work, the two are the same -- it's your life that you're spending, so let's use good stuff.

{% include flatpixel.html tag="squanch-merge" %}
