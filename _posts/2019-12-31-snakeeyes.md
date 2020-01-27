---
layout: post
title: Kube is ~3 different things that could be split out
description: Kube is also greek for dice
keywords: cloud, strategy, design
author: Abe Winter
---

I'm not one of those luddites who thinks we shouldn't run our container workloads wherever they fit, and kube is *the* tool for that right now, but it has 32k github issues -- that's 1 for every 2 stars. It's too complicated.

## How to split

1. Binpacking containers to hosts.
	- This is both the runtime that takes care of that plus an API / database of where things are and the rules engine.
	- Autoscaling can live as an auxiliary system on top of this -- it doesn't need to be built in. Autoscaling has a lot of logic quirks and edge cases, it's too new, it should be BYO
1. Routing system
	- i.e. what's currently in kube service / ingress
	- plus the vendor-specific glue that integrates with cloud resources like load balances and letsencrypt

The third thing is everything else. The yaml config language is in a perpetual state of staleness and impedance mismatch and IMO should be thrown in the trash. Cron doesn't belong in there -- it can talk to the binpacking system but doesn't belong inside.

Storage management has always been weird in the cloud. EBS makes a network store appear to be a disk and it's convenient and backed-up but you're basically amortizing performance for convenience. It kills me that hosted DBs are running on EBS disks. My point is that for kube, it's not a huge advantage to have the orchestration layer mount network drives for you. This can happen in a general plugin system, not a storage-specific plugin system.

## Why split

1. the config language and update systems are painful and edge-case-y
1. the routing stuff is highly platform-dependent anyway and has like a zillion backends, a lot of which are broken (looking at you EKS)
1. it opens the door to competition -- which is bad for G but good for all the other participants of the CNCF. Kube wins when you say 'orchestration framework' and loosely define it. It's hard to fight its momentum.
1. pretending binpacking and network routing are a single product creates tight coupling that makes everyone sad

## Kube as cloud strategy

I've used kube on multiple clouds, both self-managed and hosted, and G's hosted kube is by far the best (although it still has surprises and quirks).

I think that for the time being G can say 'we're the only hosted kube that works' and be more or less right for a category of customer that wants all the features and has performance / density needs. And as long as the feature set continues to grow, G may maintain their lead here.

I don't think kube alone can let them pull ahead of azure or aws, but I'd believe it's accountable for some % of the teams that switch from other clouds to them. I've heard people say 'I bet we'll eventually be on G'.

Someone at G had an insight that 'there's a kind of cloud workload we do better than amazon, let's open source that and make it the new standard', and miraculously they were right, it became the standard, mesos was hardly a player, and the other cloud vendors are having trouble keeping up with the pace of change.

I'm not saying this advantage will last, I'm still surprised that docker dropped the ball so badly after building swarm and buying tutum, but for now I'm impressed.

{% include flatpixel.html tag="snake-eyes" %}
