---
layout: post
title: ORMs are backwards
description: Not bad just backwards
author: Abe Winter
---

ORMs are something that seem cool until you have to do anything with them, and then they just get in the way. Their promises (backend-agnostic, write type-safe native code, less boilerplate) sometimes have a catch and sometimes are just false.

The reason for this is that ORMs are backwards: they force you to design schemas in your implementation language (python, javascript, java) and then export them to SQL 'somehow'. (The 'somehow' is usually a half-baked migration tool). This is bad for a lot of reasons and horrible if you want to access your data from another language.

I think all ORM users have a journey from 'there should be a way to' to 'this is saving me so much work' to 'I have to reach into the vending machine to get my change out'.

* toc
{:toc}

## SQL should be the source of truth

SQL is a common skillset that includes most programmers and some business analysts, has been around since the 70s, and gets more useful every few years.

I worked with a smart data contractor who loved and was good at SQL and who *quit* over trying to work with a large aggregation query in SQLAlchemy. It was more verbose, difficult to get right, and he correctly observed at the time that SQL was designed for this in a way that SQLAlchemy isn't.

More generally, SQL is one skill and an ORM is three: you have to know SQL, the implementation language, and how to set up / debug the ORM.

The ability of ORMs to target multiple DB backends *isn't* an asset. You pay for this with performance (when you're trying to use a native feature on a single backend), velocity (hard things are harder) and correctness (testing on sqlite when you target postgres is risky).

New feature support has to travel up multiple layers. Fancy new things like arrays & JSONB took time to filter from the DB to the language DB driver (e.g. psycopg2) to the ORM (e.g. SQLAlchemy).

Some ORMs offer to 'mirror your live DB' into a schema. That's insane to me. It makes any type-checking or linting impossible. You have no idea what you're getting. Your test suite will be useless because your local DB probably *is* getting spun up from a schema. If not, then you have another hard problem of doing regular prod dumps to your dev environment. Yuck.

ORM-light tools that coerce responses into native structs and allow for type-checking are less offensive to me.

## ORMs take over connection management and migration

There's always some surprise about the connection or pool type. It's never straightforward, it's always badly documented, it has twice as many layers as necessary because it has to manage bespoke session tracking and table registries. Transactions are undocumented or mysterious, autocommit is implied or hidden.

Migration is a hard problem. It's made harder by the fact that our sql migration expertise is fragmented across multiple implementation languages (py, js) when it should be specific to DB engines (mysql, postgres).

Sqlite ships with something called sqldiff that can diff two sqlite databases. I think it runs on actual DBs, not schemas, which is weird, but still that's a good first step.

## Especially bad in a polyglot codebase

And *every codebase* is polyglot now. Is there any company that sells 'just code' now? Everyone has a SaaS or a website or a mobile app or something.

Siloing schema definitions in each implementation language is a major obstacle to onboarding a new language.

My experience of working on backend / mobile teams is that sometimes teams communicate well about message specs and sometimes not, and the 'not' times ship real errors. You may say 'mobile apps don't hit SQL directly, and message schemas are a different problem from storage schemas', and that's true, but many teams have polyglot backend codebases (or want them), or use python or scala just for data.

'Full stack' schemas would be so awesome. They would statically catch those surprises when the layers of your system don't agree on the shape of an object. Beyond that, they could accelerate UI development by providing programmatic / default views for certain kinds of objects.

We can't have nice things until we move our schemas out of our app languages and into declarative spec languages like SQL, proto, or even jsonschema / swagger (though I'm not a great fan of the last two).

## What am I doing about this

This article is at least 50% out of desire to plug my alpha-stage anti-ORM, [automigrate](https://github.com/abe-winter/automigrate).

Automigrate starts with `create table` statements in vanilla SQL and can use those to generate:

* ORM specs in various app languages (currently just python SQLAlchemy)
* migration commands based on the git history

Schemas and migrations are generally a difficult thing in a new codebase and a problem that teams solve in different ways. My goal is to standardize that, improve my life, and make it easier for people to add new languages to their stack when necessary.

<hr>

## Appendix: things people said online

I got various feedback about this from internet people. Some of it was:

* "Simple CRUD operations are annoying to write without an ORM." I mostly agree with this, especially on the read side, potentially less on the insert / update side.
* "My ORM *does* use SQL as a source of truth" (from users of various ORMs). If you said this and mean that your class methods translate well to SQL, we're not saying the same thing. If you said this and mean that you can mirror a running DB to a class hierarchy, I'm talking about SQL statements checked into git, not a live DB.
* "ORMs enable composability." I'm interested in this argument -- in theory you can create a generic RBAC system or something and use it everywhere. In practice clunky join syntax is one of the things that ORMs do that puts ants in my pants, *but* this article is mostly about schema defs and not about querying so I'll say 'no comment'.
* "Service oriented architectures shouldn't be looking at each other's data directly, so the polyglot use case doesn't matter." I half-agree, but I don't agree in the data processing case. Also, SOA means different things to different people and there are advantages to having a common datastore when you're small.

{% include flatpixel.html tag="smro" %}
