---
layout: post
title: Are startups getting value from project estimation?
description: I mean, atlassian obviously
author: Abe Winter
date: 2019-05-25
draft: true
---

I've always wondered whether project management of small projects at small companies adds value. From the outside project management looks like useful work but sometimes when I get handed a spec, it has to be redone before work can start.

I did a survey of my professional network which turned up fun results like this:

![What is your expected uncertainty for estimation? (pie chart)]({{ "/assets/expected-uncertainty.png" | absolute_url }})

Which is to say it varies.

That said, I hate being over-deadline. That situation where every unit of work I finish makes the end feel further away as I uncover new dependencies. I've had my share of these moments and I avoid them like the plague.

The startup world is particularly bad at estimation I think. We're relatively junior, the person *hiring* us is often relatively junior and evaluates on 'output' skills rather than organizational skills. (By which I mean both 'being organized' and the ability to operate within an organization). And we're impatient, which means we reward shorter estimates even when they don't play out.

Despite all this we still set deadlines and pretend we can reach them. This article is my attempt to capture the best practices I've seen and explain why we deviate from them.

Bear in mind as you read this that for a given project and team, 'should you estimate' or even 'can you estimate' are questions you'll have to answer on your own.

1. toc
{:toc}

## What is it good for

In general, estimation is useful for:

* Respecting the capacity of the team. Overloaded poeple are inefficent, do too much switching, make mistakes, and get burned out.
* Giving the team space to get the job done (time, head count, resources, political cover, whatever).
* Ordering work. NASA's Apollo program relied on a testing cadence that went from easy to hard. (George Mueller and Wernher von Braun [fought a war over the details of this](https://en.wikipedia.org/wiki/George_Mueller_(NASA)#NASA_and_the_Apollo_program))

In the case of large R&D projects: carving out large blocks of time for the team to work in peace, setting spending caps that the company can afford. Bearing that in mind, the Manhattan Project was over time (the war in Europe was over) and over budget.

In the case of large non-R&D projects: answering some of the open design questions before you start (but bear in mind that this discovery process is in itself relatively slow and expensive), allocating resources ahead of time.

In the case of client-facing work: usually cost is agreed on (in broad strokes) ahead of time. Without correct estimation, the implementer would lose money on jobs.

Repeatability matters. One survey respondent who is a project manager at an agency has high confidence in estimation because her process includes a discovery period before anything is promised, and because the work follows a repeatable rubric.

A close relative is a senior project manager at an AV installer and has the most sophisticated version of this that I've seen: gantt charts, precise costing. And they still sometimes have to crunch or swap in high-skill people. Also there's a high degree of measurability and repeatability here: they know number of rooms, cost of equipment, square footage, various delivery lead times, and person-hours required for different installations.

This work is half prediction and half course correction. When schedules slip, they start the overtime. When estimates fail as predictions, they fulfill their second function as an alarm.

## I don't understand what makes this so hard

'I don't understand what makes this so hard' is a real line I've heard from more than one person in charge of a project. It's tempting to snap back with the obvious answer. The right thing to do here is to ignore the tone, take a breath, be grateful you're in a one-on-one context, and pick the right answer from these three:

1. The easy answer. This person thinks they're saying "This is easy -- the team is incompetent or this spec is too complicated -- I can fix this in less time than this meeting takes." You can respond with "You're right, this should have been easy, we'll crunch and ship it." That's definitely a lie, so cross your fingers the project lead forgets this promise by your next check-in.
1. The true answer: "You're right, you don't understand. And keeping projects on track is your job. Therefore ..." Don't say this one.
1. The right (i.e. productive) answer: We can still get a version of this out the door. I can help you trim this down so the ICs don't panic. Then we'll pick up the pieces and figure out how to deliver the rest.

This kind of thing points to lack of trust (which is hard to fix) but also missing skills at the top. The senior manager asking this question may be (gasp) 'non-technical'.

'Non-technical' is a charged-up term these days, and I don't exactly mean someone who doesn't program. I mean someone who doesn't understand the product that they manage, doesn't understand the accupuncture of how changing X can break Y, doesn't know who works well on what, can't conceive of system or resources answers to why one change is harder than another.

I don't mean to completely absolve the ICs / tech team. When someone brings you work that hasn't been vetted, and you take it without vetting it, you're being unprofessional in a platonic sense. The essential virtue of a professional is the ability to deliver skilled work. The essential virtue of delivery is that it happens on time.

## Signs good estimation is happening

I don't think this list is controversial or surprising -- I do think a lot of companies in my space don't do any of these things. I think that's okay as long as they don't *say* they're doing estimation.

Good estimators will:

* Detect late delivery early: you know as soon as things are off the rails
* Do course correction: you can crunch (add labor) or compromise (reduce scope) when something is running late
* Pad: there's a safety gap between internal estimates and the quote provided to a client / senior manager. This also (says one of my survey respondents) makes room for refactoring and tech debt reduction
* Have a large discovery period (including de-risking experiments) before taking on the job
* Let ICs turn down, redesign or rescope the spec
* Do capacity planning / prioritization: estimates are used to support decisions about how much work to take on at once
* When discovery hands off to implementation, give an ordered task list that's realistic and doesn't surprise boots on the ground

I've had clients where *zero* of these things are true. But this list isn't a secret, everyone knows this stuff. The mystery is why teams *don't* do it. Some theories:

* Project management requires all kinds of trust; trust that you'll be allowed to finish, trust that the feature is right, trust that the team is working hard. 'Black box organization' where things get done when they get done can be easier where trust is lacking
* Project management requires significant management attention. If there are too few managers or they can't or won't pay attention to details, the forces of chaos will triumph
* The team is so overloaded that every week is triage. (But this is circular -- the team is overloaded because triage, triage because lack of planning; so more of an effect than a cause).

## Ways teams disincentivize good estimates

* Hand off 'complete designs' to ICs. If something looks finished and hasn't had eyes from technical IC, that signals to any IC who's been around the block 'do this with no back talk'. To shut this down you need a senior technical person who's been given authority to lead.
* Perfectionism or kitchen sinkism. "We can't release this without all of these things." "There's no subset of this feature that's releasable."
* Unrealistic targets
* Bad cadence -- infrequent checkins, but also too-frequent checkins where managers are shocked that no progress has been made. Or even worse, they change targets. Bad reactions to an honest assessment of progress. Every important check-in requires some amount of preparation i.e. is not without cost. This is why I don't like daily standups.
* Power structures designed to disempower technical pushback. I've seen clients where a political battle left an entire group of programmers underneath a non-technical PM with strict orders to do the PM's bidding. It got emotional when any IC pushed back on a design. The 'build a box' arc of Silicon Valley captures this perfectly and is hard to watch for anyone who has lived it.
* Changing ownership without reassessing targets (both time & design targets)

You'll note that all of those points assume assigners of work who are inflexible and authoritarian, and doers of work who are powerless sad-sacks. At sick project cultures, both are true.

## Stay within the speed limit & avoid tickets

I think ticketing systems (ugh JIRA) are actively harmful here because they:

* Can't show you whole project view and ticket details at the same time. They don't have a good 'edit view' for this case. I'm flashing back to a JIRA list where all the tickets were 'user must be able to ...' and the rest was clamped.
* Are technically able to handle task dependencies but are clunky at it
* Are rigid -- once a plan has been agreed on it's 'the plan'
* Promote distinctions between ticket-writers and doers. This is a cultural thing which isn't built-in to ticketing systems but seems to always be the case. PM (pro-ject or -duct) delivers a stack of tickets based on their too-detailed, inexpert fantasy about how the work might go. ICs are left to do interpretive dance to understand (1) what the work *is*, (2) who told the PM to do this and what that person wants, and (3) how to communicate progress when the tickets bear no relationship to the work.

When you pay someone to write tickets, you're incentivizing trouble. Convince me JIRA is better than a shared spreadsheet.

## Agile

If you respond to this article in public please don't use the word 'agile' without linking to a definition. Like all faiths, agile has points of dogma that are the subject of holy wars between the orthodox. It also sounds like mumbo-jumbo to the non-believers, even the ones that are forced to attend church.

## If you do nothing else

Write down the steps as soon as you know them. Update them when they change. That way when someone comes up to you and says 'what are you working on' you'll know the answer.

{% include flatpixel.html tag="estimation" %}
