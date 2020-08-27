---
layout: post
title: Boilerplate generators are full-stack plugins
author: Abe Winter
description: War with the spartans will come and with it a great loimos
keywords: shit, repo
new: true
---

The question of opinionated web frameworks is divisive and has surely ruined its share of family dinners.
Install django or rails and most developers fall into one of two camps:

**Camp 1**, amazing, I know exactly where everything goes, there's a right way to do everything, and the batteries are in the kitchen sink, as god and DHH intended.

**Camp 2** runs `ls`, then `find`, then googles 'django without project skeleton', then googles 'do I check all the django files in or what', then says 'who fuck shit all over my repo'.

* toc
{:toc}

## Toolbeltism

Tools like flask (or its various async clones) appeal to camp 2.
They tend to integrate functionality by importing something and then making a function call to 'wire it up'.

I'm in camp 2 but I'm starting to rethink my life choices, because I've spent 3 of the last 6 months writing and rewriting user login for different small projects.
Now at the end of it I have a small + shitty 'personal flask tools' library that has a 60% working auth / login system for flask.
(Note lack of github link -- normally I plug my small + shitty OSS projects but this one is particularly small + shitty).

The crazy part is that I've met people who have a 'toolbelt' that they randomly import to projects and have always assumed those people are stupid and useless.
When I realized mid-year that I'm a toolbelter now, I started to ask myself some hard questions.

If I'd started with django I'd be done already.
Investing in learning django comes at the cost of a messy repo but *saves time*.
And I learned from watching one of the latter-day marvel movies at 3x in the second half of a plane trip that no amount of money can buy a minute of time.

## Graphql, or ...

Someone posted an article to HN with some apples-to-nuts comparison like 'graphql is better than python' and the comments were not bad.

In particular [this one](https://news.ycombinator.com/item?id=23487072) which I hereby plagiarize most of:

> Looking through some of the code for Sourcehut, there’s an insane amount of boilerplate or otherwise redundant code[1]. The shared code library is a mini-framework, with custom email and validation components[2][3]. In the ‘main’ project we can see the views that power mailing lists and projects[4][5].

> I can’t help but think “why Flask, and why not Django” after seeing all of this. Most of the repeated view boilerplate would have gone ([1] could be like 20 lines), the author could have used Django rest framework to get a quality API with not much work (rather than building it yourself[6]) and the pluggable apps at the core of Django seem a perfect fit.

> I see this all the time with flasks projects. They start off small and light, and as long as they stay that way then Flask is a great choice. But they often don’t, and as the grow in complexity you end up re-inventing a framework like Django but worse whilst getting fatigued by “Python” being bad.

Click through and read the replies, they're useful.

## I've come around

It still bugs me that django steers me away from the single-file case.
I think that this is a flaw in every language or framework that does it --
most of all in mobile native development where focusing on single-file build would IMO fix a lot of sharp edges in the buildsystem.

But django / rails also provide key opinionated design choices that make full-stack plugins possible, i.e. plugins that 'work with the app'.
These choices are:

- standard DB connection / pool
- the framework handles migrations, so plugins can generate tables and maintain them
- user and session management are consistent so plugins can build on them (oauth, for example)

Django and rails both have heavy + powerful ORMs; I'm less sure of the necessity there.

I wish there were something like django-lite which provided only the full-stack plugin glue and let me do a little BYO to create a working app.
I think there's value in supporting one liners that correctly install sophisticated behavior in your app, maybe even beyond the backend -- like it could create cloud resources or frontend stuff.
That said, given how my year has gone, I'm 1000% invested in using the right tools, and will be shopping in the 'batteries included' aisle this christmas.

{% include flatpixel.html %}
