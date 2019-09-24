---
layout: post
title: Monitoring is a vampire, reporting is sunlight
author: Abe Winter
description: Set to drain
categories: pituitary-gland
noindex: true
---

An oldie but a goodie: what do you tell a devops person with two alerts queued up? Nothing you haven't already told them twice. Ba-dum ching!

Monitoring has to be looked at constantly, is hard to interpret, and can drain all your energy if you let it. Monitoring is a vampire.

1. toc
{:toc}

# Definitions

<u>Monitoring</u>: time-series dashboard that is difficult to customize. Difficult to look at more than one time-scale at the same time. You might open it because you just made an infrastructure change and are watching for problems, you might look at it because you got a statistical alert, you might look at it because your pituitary gland gives your hindbrain a little tickle every day around peak traffic time. Using custom logic to render in monitoring apps is difficult.

<u>Reporting</u>: a batch process that outputs a custom view on an interval. Reports are sent via email or are stored long-term in a web app so can be collaborated around and compared over time. Views tend to be customized to fit the team's needs. Long-form text can be patched in to explain the views. Metrics can be highly customized and can be aware of app-specific things like configuration, maximums, the exact time when a setting was changed. Reports can be triggered based on various actions in your system and the duration of their input data can be trimmed to your needs.

The two key differences are:

* Reports are batch, not continuous
* Reports run inside your codebase and include your logic

# Decision support

There's an argument to be made that monitoring is better for ops decision support because it's real-time.

In an emergency, yes, that's true. But take the example of fleet scaling. Most applications have a circadian rhythm, and to train an algorithm for scaling you want to look at a day or a week of data (or even last christmas, if you're an e-commerce app).

Unless your house is burning down, it's likely your ops decisions require at least a full day of data.

# Chunking

Reports can be timed to releases and experiments. If you've ever tried to line up monitoring charts with a code rollout or an AB test you don't need to be convinced here.

Batch & process monitoring are also badly served by monitoring. Why do we waste our time piecing together batch outputs from charts that were from 'around the time it started'? I've seen the 'success gauge' trick in every graphite installation I've used. (That's where you set a 0 or a 1 in a time series when your thing finishes). Let's just email a report.

# Non-experts

When you're monitoring something standard like ELK or a database, *sometimes* expert knowledge transfers. Bespoke app monitoring tends to be pretty bespoke.

This is an opinion, feel free to disagree: monitoring is way hard to dive into than code. Code has comments, it has call stacks, it has comments & docs if you're lucky. Monitoring tends not to come with those things and unless you built it, the odds are you don't know what good and bad looks like.

Reports (vs monitoring) are friendly to non-experts because:

* In a monitoring dash, it's not clear where to start -- which dash, which chart, which time period? With reports, you get the same view every time and can communicate around something constant.
* Reports can be packaged with explanatory information. I know this is technically possible but in real-world envs it tends not to exist. (If you come from a place where your charts have docs, email me and I'll add a paragraph about how great you're company is. For real).
* Reports can more flexibly combine different useful things: charts with different resolution (hour vs day), critical things like peaks, custom interpretation logic (all of numpy), custom alerting logic.

Having ops dashes that only one or two people can interpret is an organizational antipattern. Where possible, we should replace those dashes with reports.

# Monitoring could be a lot better

Why isn't monitoring as powerful as R / numpy? I don't know.

{% include flatpixel.html tag="reporting" %}
