---
layout: post
title:  Instead of containerization, give me strong config & deployment primitives
date:   2017-04-27 19:08:00 -0400
categories: blues
visible: true
top: true
---

## A modest proposal

These are the things I want out of my cloud management layer.

* define resource access in a config file
    - my app will use this to know where to look for things
    - the OS will use it to determine access rights
    - kind of like a fancy chroot
    - includes network interfaces, ports, file paths
    - should include logging sinks (yes, the OS should provide a logging layer)
    - should allow command line overrides and have an offset feature (port X+N)
* standardize the way we deploy to load balancers. when I deploy to a load balancer it should:
    - register a name
    - lock a resource (network ports, max processes, names, that sort of thing)
    - optionally, load balancers should also manage tracebacks and performance monitoring
    - optionally support serverless here (deploy a program to a load balancer with a 'hook')
    - load balancer selection algorithms must be user-programmable in language of choice. have useful defaults, but recognize that special needs are going to be *very* special in this space. When instagram migrated to FB hardware, they [built a python tool to manipulate iptables](https://engineering.instagram.com/migrating-from-aws-to-aws-f4b16a65e13c) called [neti](https://github.com/facebookarchive/neti)
* cron is a necessity too; I haven't used chronos or minicron and I've also never used a scheduler that didn't surprise me in a bad way

## What did containers ever do to you?

Complaints:

* worst complaint: multiple different 'network layers' (swarm et al) show that docker didn't understand my deployment needs (or anyone else's)
* like it or not docker is a buildsystem and it's a bad one (see below)
* my iterative dev setup often isn't that similar to my 'under docker' setup
* as container formats approach maturity documentation remains bad, particularly for docker
* has docker fixed security? getting docker to run as reduced privilege required passing a UID last I checked. A lot of docker deployments are still stuck in the 'root by default' doghouse, with (I assume) various container breakout exploits? Really not sure.
* storage is inflexible

The 'repeatable builds' argument is the most interesting to me, in part because this is the same promise that java made in the 90s (write once run anywhere).

If you develop on linux and run on linux *and* you're in a deploy-as-source language, you may not care that much about repeatable builds.

If you're deploying C programs that rely on system libraries, things may get tricky if you cross flavors or versions of linux. But you can probably deploy static-linked executables more easily than setting up docker.

The dev experience for incremental builds on docker is really bad. If you've had a positive experience with this, write an article and I'll link to it here if you convince me.

## What about kubernetes?

<style>blockquote {font-style:normal; letter-spacing:normal;}</style>

> Warning: the HN discussion on this article leads me to believe my kubernetes knowledge is stale. A lot has happened since summer 2016 when I played with it. If you're going to read this section, close one eye.

> I still don't love the kube model. It seems like a many-headed monster in a use-case where clean, orthogonal primitives are called for. In particular, requiring a cluster & a container registry as a floor seems like a lot to ask. **But** the tools have come a long way in a year so try them yourself and draw your own conclusions.

Kube configs seem shitty and rigid to me but all configs are so that's not a valid criticism.

When I used kube in 2016 the cluster turnup support was bad; it seemed like you could use it managed in the G cloud but not anywhere else.

It also gave me a duct tape feeling or batteries not included -- like the critical pieces (docker support, DNS, load balancing) weren't integrated into the original design.

I realize all of the above are 'bad feelings' rather than arguments. I've been reading the build releases and would be willing to try it again, but my takeaway from last time was 'too complicated' and 'bad at testing'.

## What will it take to build this?

6 months x 3 smart devs who understand the linux kernel. So like $600k.

Getting it running in a distributed fashion would take 3x that. (But distribution & scale aren't the be-all and end-all; a lot of small teams want heroku workflow, are willing to host / manage it themselves, and don't need 100% uptime).

{% include flatpixel.html tag="config-vs-container" %}
