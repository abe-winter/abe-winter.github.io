---
layout: post
title: Soft skills for parachuting into a codebase in crisis
description: These guys are the best and they specialize in the ridiculous
author: Abe Winter
date: 2018-11-27
---

<style>
blockquote {letter-spacing:inherit; font-style:normal;}
</style>

When I was in high school one of our wolfhounds turned 7 and, like big dogs do, got sick. In this case acutely. The family vet was out of town, it was the middle of the night, and we ended up in a local 24-hour veterinary clinic where they kept her for observation. I stayed there overnight. The vet on the night shift stopped by between patients to check in on our dog and chat.

I came away with my first real model of professionalism at work. I'm still fascinated by that vet's ability to balance time, emotion, and attention while managing a therapy that wasn't based on a clear diagnosis (there was no time to wait for labs to come back). I don't have a similar role model when it comes to programmers. Nobody in our field is good at this kind of thing.

This article is about soft skills that normal people learn in an MBA or from work mentors or, for all I know, on the playground at school. I learned them as an adult on the job in a series of consulting gigs where my role was variously something between IC, architect and PM.

(The dog got better -- IIRC it was some kind of infection-related autoimmune attack that resolved with fluids & steroids).

1. toc
{:toc}

## Get the lay of the land

When parachuting, you're safest in the air. Wait for optimal conditions before dropping. You have a bird's-eye view of the whole organization and the freedom to define your role. Yes this is a metaphor but it's also the way these engagements work.

![where we dropping]({{ "/assets/lander2.jpg" | absolute_url }})

It's okay to do a lot of discovery before (a) taking or (b) starting the job, even if you're being brought in to solve an urgent problem. If the client won't let you do this before defining your role, steer clear.

Interviews with the team are critical:

* they let you define the problem in concrete terms and prove to yourself that it's as-advertised
* you get to define your role so that when you come on board people are used to cooperating with you
* you can call out uncertainties. Saying 'we need more information to make this decision' will make you feel like an asshole but it's your job and it serves the client

Getting to the root of a hard problem is hard, and after the discovery stage you'll be under great pressure to stick to a timeline. Exposing uncertainty before you start lets you budget for it later.

Your discovery stage will include some tech stuff like reading code or exploring the ops side, but has to include interviews with the people who built & maintain the system.

## Trust but verify

Learn what people are good and bad at. This is tricky because your best sources will be your worst sources -- they'll have all the information you want but they'll also want to give you advice. Whether or not it's good advice, as a professional you'll have to own your conclusions so you must arrive at them on your own.

The interview process is about finding allies for the implementation stage but it's also kind of freudian because people contain a mix of good and bad.

The person with the highest [bus factor](https://en.wikipedia.org/wiki/Bus_factor) is your best & worst friend because they're responsible for a lot of your pain -- they wrote everything and some pieces of it, with or without docs, can only be understood by them. But they also have all the answers.

You won't be able to do your job without your interviewees. You're here to help them. Let them tell you what the problem is in as much detail as they're willing to volunteer.

## Roadmap

A roadmap is a document that formalizes the problem, the solution, the steps (in broad strokes), and the timeline. It's the thing that will get waved in your face if you're late, but it's two sided and you can wave it back to buy time to get real work done. Writing it will be an emotional rollercoaster in a [laws and sausages](https://en.wikiquote.org/wiki/John_Godfrey_Saxe) way.

You have to be a professional when roadmapping:

* Professionals explain themselves; be prepared to explain anything you do in terms of standards & deliverables
* Professionals win arguments. If you can't defend your plans in the room then you can't do this kind of work.
* Maintain your standards in the face of emotional appeals and misinformation
* Make conservative estimates about how long work will take to deliver & how expensive

Time is the trickiest because beyond the uncertainty inherent in the work, you also have an incomplete picture of the client's systems and will discover bad news in there -- broken, unmaintained things that need to be 'drop everything and fix' fixed. Ongoing invisible errors critical to their business that have nothing to do with you but delay your plans.

Delivering on time is a big part of the reason you're here, and it's the reason you have the power to fight for a good roadmap. Don't waste the moment.

![my god it's people]({{ "/assets/mygod.jpeg" | absolute_url }})

The roadmap process is only half technical. Shipping your design is all about the people and the emotions involved. Embrace this, it's normal.

You'll be under great pressure to overpromise how quickly and cheaply you can do the work. Trust me, stick to your guns. If the team can't order work based on a best-estimate, if they can't sacrifice a pawn (i.e. a less important feature) to hit a deadline, that's an urgent problem = a fight. Fighting to keep the roadmap simple is always worth it. Never commit to something you can't deliver or which will be unmaintainable.

If people are trying to negotiate delivery date without giving up complexity, don't think of it as negotiation as in BATNA. Instead think of it as [bargaining as in grief](https://en.wikipedia.org/wiki/K%C3%BCbler-Ross_model). The client is *actually* asking you for advice & support, i.e. what you're paid for -- just in a strange way.

My favorite example of emotional management is the [personal letter from KGB head Yuri Andropov to Brezhnev](https://digitalarchive.wilsoncenter.org/document/198187):

> Like all comrades, I clearly understand the whole meaning and the whole significance of the steps, which were urgently and energetically taken by the Soviet Union on your initiative. All of this was necessary, and, unquestionably, produced its positive results.

> But perhaps now a moment has already arrived when one will have to treat the problem of the Middle East as a long-term, multi-stage, and complicated one, which will by virtue of this require a more even-paced solution, such conduct of affairs that one’s energies are not depleted and not exhausted. By this, Leonid Ilyich, I first and foremost mean you, the extreme overstraining of your strength and your almost around-the-clock activity, which are of course very important in the solution of the Arab-Israeli conflict but which are also extremely necessary for many other important tasks and are first and foremost necessary for our party and the Soviet people.

Translated loosely from the Russian: you have other responsibilities, don't stay up all night, you're not helping. As a professional, it's sometimes your job to say 'leave this one to the professionals'.

## I'll most likely kill you in the morning

![please, I have to live]({{ "/assets/westley-wine.jpg" | absolute_url }})

One thing you get from a roadmap is signoff, which should buy you time to deliver without any sleepless nights or reworking the plan. But it seldom works out this cleanly. You'll need skills for dealing with impromptu checkins and attempts to deviate from the path.

Projects have a life-and-death relationship with time. Forward progress is critical because your client needs it to run their business and you need it to justify your paycheck. Periods without checkins are also important so that you can hunker down and get something done between edits to the spec.

Do what you can to schedule checkins instead of getting blindsided, but it may be an uphill battle. One question to always prepare for because it's always fair game: what are you working on right now and how is that related to our goals?

Most importantly don't let people rush you into replacing your long-term deliverables with short-term distractions. I like the line by Tokugawa Ieyasu who I think was shogun:

> Life is like unto a long journey with a heavy burden. Let thy step be slow and steady, that thou stumble not. Persuade thyself that imperfection and inconvenience are the lot of natural mortals, and there will be no room for discontent

## Seize ownership

![mine?]({{ "/assets/mine.jpg" | absolute_url }})

My second favorite fight scene in a movie is the [kitchen fight](https://www.youtube.com/watch?v=r2pwkI29O8A) in The Bodyguard. Half the movie is Frank Farmer pen-testing the household and imposing new, professional rules. Everything he does is grounded in his experience & expertise. Even this fight is controlled, he never escalates, and serves the high-level goal of doing his job safely and well.

He zoomed out as far as possible to do his job, and you have to do that too; don't let people continue to ship bananas just because 'they own that service'.

It's easy to fall into the trap of only fixing and understanding what's on your desk i.e. has been assigned to you. That's dangerous because often what are tractable fixes on someone else's desk (collect a new data point, for example) become insane and unmaintainable when you try to do it all in stuff you control (log aggregation plus OLS on the timestamps, in the example I'm thinking of).

Always ask for help before taking something over, but if problems in 'another silo' are preventing you from getting your job done, seizing ownership is a legitimate tactic (though gauge in advance what bridge you'll burn). If you're a consultant, your in-and-out status makes it easier for you to take these political risks. And the ability to work cross-boundary is part of the reason someone like you has been brought in and given the ear of power.

Never assume you can't get what you need to finish your work -- ask, take, do what you have to. If you really believe something is broken, you'll be able to make an argument later for why you fixed it.

Ultimately if you can't get the resources and access to do your job, you have to leave. It's in the client's interest for you to get out as early as possible so they can bring in someone else.

## [Possess the right thinking](https://www.youtube.com/watch?v=X_mTbMTAzXc)

![oh yeah]({{ "/assets/here-comes-kool-aid.jpg" | absolute_url }})

Preserving your perspective & independence can be tough in the face of tough arguments and an organization that isn't structured to help you deliver.

You have to be willing and able to engage in arguments and, wherever possible, put the burden on the other person to convince you. Be open to new information but don't derail the plan without an argument that convinces *you*. Use & preserve your authority -- until someone says otherwise, you own your project plus, within limits, whatever you need to get it out the door.

Remember you're here because the team couldn't solve the problem on their own. Listen to their information & strategies but don't internalize them -- it's okay to strike your own path.

Be brutally honest with everyone, even people who can threaten you like a senior manager who can reassign you or a peer who can use your failures against you. Being honest with others is the prerequisite for being honest with yourself, and you'll need your judgment intact if you're going to deliver under pressure. Clarity is especially valuable when it's in short supply.

Everyone is vulnerable to the temptation to exaggerate under stress. Professionalism means being the one person who doesn't. Think about electricians & plumbers -- they'll tell you straightaway if you ask for something dangerous or impossible, usually with a statement like 'that will cause a flood / fire'. Internalize that tone.

Memory matters, especially under stress when people tend to have short memories and forget long-term plans (like the roadmap). The best antidote to this is to keep a diary -- you'd be surprised how many managers do it. At first it will just be a postmortem tool for when things go off the rails, but over time you'll learn to identify pivot points and guide the work back on course.

Don't get pulled into the event horizon. Stay remote if you can a few days a week. My best work has been at companies where I was at the client part-time -- not fully-remote, but half and half.

## Don't be afraid to move the needle

![let him sleep it off?]({{ "/assets/toxic-waste.jpg" | absolute_url }})

Don't assume things are the way they are because someone wants them that way, particularly with codebase style and tools.

I've always been reluctant to change other people's code (deduplicate cut-and-paste, for example) and add tools (lint, build etc) because I assume that the team likes what they have. This is never right; people happily adapt and are excited to see new ways of doing things, especially in small doses and backed by a solid argument.

Don't let anyone force *you* to use bad tools. If your entire day is spent / wasted in a tool that you can easily replace or rebuild, it's threatening your ability to deliver = your reputation and livelihood. Don't let yourself get forced to use bad tools any more than you'd wear the wrong size sneaker -- you can hurt yourself.

Don't let normal resistance to change put you off the trail. Stay focused on the goal & your values. You'll have a lot of jobs, and you won't succeed at every one, so follow what you think is the right way to work; in the long term it's a habit that will serve you well.

I read this [article about Holly Neher](https://abcnews.go.com/Lifestyle/female-high-school-quarterback-throws-td-1st-pass/story?id=49564020), the first female quarterback to throw a touchdown in Florida. Her coach said:

> Whether it’s a female or male quarterback or a ninth or twelfth grader, you want someone who isn’t afraid to make a mistake and who knows they’re going to get yelled at from time to time.

Teammates who appear to be mad and are fighting you the loudest are actually rooting for you to score.

{% include flatpixel.html tag="parachute" %}
