---
layout: post
title: Docker failed because it didn't launch with DNS
description: Docker the company I mean, the tool is getting used
author: Abe Winter
---

* toc
{:toc}

## Incredible adoption curve -- what went right?

Docker was a weird paradigm shift that had a remarkably fast adoption for local machine. In retrospect it felt like it went from 0 to 60 in like 2014-2015, where zero is people didn't get it and 60 is it was the official supported thing at most of my clients. Two years is pretty fast.

That's on desktop -- cloud lags but containerized deploy feels pretty standard unless you have something like lambda or GAE that has a language-specific bundle.

It's no surprise it went fast. Running mysql directly on your laptop is like having an unflushed toilet in your kitchen. God forbid you ever needed to run two. Docker lets you do that without having to taste mysql in your food. It was a godsend, and a rare example of the community embracing a new primitive wholesale.

There's an argument that google was always going to win this -- they invented containerization, mainlined it to the kernel, and then released a usable cloud platform that used it. But docker's commands and image structure are something that wouldn't naturally be born in google -- D's obtuse, order-dependent layer caching mechanism wouldn't make sense given the scale of G's buildsystems.

Docker tried to make build caching work with [buildkit](https://github.com/moby/buildkit), which is I guess at version 0.6.1 but it's been so long and does that mean it's ready? Is it usable by small teams? Does it integrate with apt-get and pypi? Bleh. By starting at 'too simple' docker ended up at 'simple enough'. Zero chance google would *ever* get there.

Google has never been good at releasing good tools that make sense outside google, with golang a possible exception but (1) is a language a tool and (2) does it have a working package manager yet? The last three were DOA.

## The other shoe

$200m plus of venture raise plus multiple acquisitions and still nobody is sure how much they net; I suspect it's a drop in the bucket compared to the total current kubernetes market (though I'm prepared to be surprised). I can't find any public information about revenue. Could be *zero*.

'Big investment in direct sales' was the story for a while, and it led to the most important event in an F-round infra startup's life: [the hortonworks CEO takes over](https://techcrunch.com/2019/05/08/steve-singh-stepping-down-as-docker-ceo/). Hadoop IMO is a total scam where companies that don't need big data tools adopt them and then discover they can't operate hadoop on their own. The people who oversee hadoop commits earn their consulting income from it being difficult to operate, there's a conflict of interest for you.

Other than getting that one spark job working, I'm not sure what a hadoop consultant is going to do to fix the business. Do they even control their codebase anymore? If not, what are their assets?

Docker people probably didn't expect the adoption they got and may have been caught flatfooted, but they raised a ton of money and had years to get their shit together. In my opinion docker-compose has never been useful. Swarm never got adopted, buildkit is still somewhere in the great go build cluster over the horizon. Have they done anything good since their first stable release? Where were they headed?

## DNS was the missing piece even before their failed cloud offering(s)

Lack of DNS integration for docker containers is, was, and has always been annoying on the local machine. I still have to write like 10 lines of wrapper code in every new project to look up IPs for docker names in the local dev environment. My use case, as it is for a lot of people, is database / services in docker, hot reload API in shell.

Docker's strategy for this probably was names inside overlay networks but the hole there is sooner or later things need to be reachable. This is still a pain in kubernetes-land: process, container, pod, deployment, proxy, service, ingress, load balancer is a lot of turtles (even though some of them don't exist physically as a network hop). Had docker created a simple primitive for DNS/routing like they did for container builds, kube would have inherited that simplicity and docker might even have held it's own against the bigger offerings.

(Arguably binpacking is a killer feature too, but IMO DNS is more vital).

I think docker's problem was a **missing argument** for where they were going and how to get there. This is hard to detect when you're in it because not everyone in a company understands where it's going at every moment, but if you've been in your career for a few years and don't understand the links or the stops in a company's roadmap, that's a warning signal.

## Beware the missing 'then what'

The great idea at the beginning was to use containerization (existing technology) to solve the problem of running multiple things on your laptop (existing problem) by creating a good tool, build file format, and image format (incremental but real innovation).

But a great idea isn't a business. My successful and, especially, unsuccessful founder friends have tried to drill this into me. You need to have a good idea AND a way to get where you're going. That means revenue or \*gasp\* positive margins.

AWS was old already when docker was born. Jim Carville probably wrote 'cloud' on a whiteboard in docker HQ when they got serious about growth ('it's the economy stupid').

But I also suspect the team didn't agree on how to get there. They had a sales team for a while and probably had a few big accounts, but they were competing with AWS which also likes to sell things, MSFT which became the number 1 cloud mostly by converting *existing customers*, and google who, I mean I don't know what to say about them, but snapchat trusts them.

Also what's the pitch to clients? Everyone who has spun up anything in the cloud knows that docker by itself is not super useful. It's still in 2019 really hard to 'just run a container' on any cloud -- AMZN fargate requires a multi-hour investment in cloudformation and ECS before you can run anything and does it autoscale? Not sure what happened with Docker's acquisition Tutum, I think they shitcanned it. Language-specific bundle runners like lambda and GAE are somehow winning this game and I don't understand why.

Even if the smart people in your company individually have ideas about how to get somewhere, that's not the same as them all agreeing on the current goal(s) and the path(s) to get there. This isn't wizard stuff that one person can deliver on their own. I suspect, albeit w/ zero insider knowledge, there wasn't ever a sane, well-argued roadmap at big D that the sales, tech, and C teams all understood and endorsed.

![profit!]({{ "/assets/gnomes.png" | absolute_url }})

Thank you.

{% include flatpixel.html tag="android-evolvability" %}
