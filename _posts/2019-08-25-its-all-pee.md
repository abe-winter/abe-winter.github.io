---
layout: post
title: For security and perf, connection pools belong in the std lib
author: Abe Winter
description: This can be a solved problem
categories: primitives
---

In my recent experience, pooling behavior has been the biggest source of uncertainty in the performance of a client library, even more than language speed or the capacity of the backend server. I'm talking about:

* Whether it will start concurrent connections at all, and how many (too many and too few can both be bad)
* Error and reconnect handling
* Badly-documented configs

My daily driver is nodejs, and I've encountered widely-used client libraries for widely-used services that don't do these things how you would expect. Some client libraries rewrite their pooling between major versions, changing config fields and invalidating docs / stack overflow. (And also invalidating my application logic).

New languages should ship with a connection pool type in the standard library, and encourage library devs to use it.

* toc
{:toc}

## Performance

If a client lib has obtuse configs you can't trust, or even worse doesn't support pooling at all, your shit will get very real at scale, trust me. Every language provides a socket primitive. If every language also provided a pool, configuring and operating these would be a skill I can learn once instead of having to read code to make sure every library does what its docs claim.

The standard lib can also invest in something like coq / TLA to verify the implementation and avoid regressions. Though let me say that I've never been bitten by a legit pooling bug.

I'm tired of having to ask 'what happens to the connection when a command errors' or 'how does reconnect backoff work'. I've tailed logs where the default reconnect behavior was so chatty that it overwhelmed my shell. Dollars to donuts it was also overwhelming the thing it was connecting to, causing *other* clients to disconnect and leading to thundering herd.

## Monitoring

Standardizing the pool has a knock-on benefit of standardizing how connection pools are monitored. Connection monitoring is important because:

* You can track time spent initializing a new connection, sometimes with handshakes for several protocol layers, vs time spent processing requests. This is a useful tuning param
* Counting total connections from your whole cluster to a backend service can tell you when it's time to shard or install a proxy layer
* Disconnects / errors is an important high-level health stat which can give you information about the state of the system separate from anything app-specific. If this were standard it would enable better automation around tuning the size of your cloud

In theory 'service mesh' tools like istio can do some of this, but whatever you feel about istio it's certainly not standard yet. I'm arguing we get value out of standardizing the most common piece of this.

## Security

Connection pools are the **only** part of my codebase that needs access to passwords & secrets. I suspect that's true for a lot of people.

I like the idea of kube secrets as a way to not check in passwords, but I don't love them as a way to secure sensitive information. They amount to files or shell variables, and every line of code I deploy can access that stuff.

Having a standard connection pool object would let us build standard ways of restricting secrets access. Only a small slice of library code needs this, not all the crap that I wrote + gigabytes of npm packages.

{% include flatpixel.html tag="its-all-pee" %}
