---
layout: post
title: JITs are un-ergonomic
author: Abe Winter
description: "I lift my LAMP beside the github door. Keep ancient Fortran your storied numeric libs cries she. Give me your interpreted, your slow, the wretched refuse of your (insert pun for 'teeming shore')."
new: true
---

I mean the world has worse problems,
but lockdown for me = thinking back on 2 hard years of high-performance (cough) server-side JS,
and my relationship with javascript as a tool.

Performance work in 2020 can be as much about caching and smart RPC design as about straight-line performance of a function.
But straight-line performance still matters.
And the ergonomics of measuring how a piece of straight line code will perform in prod are bad.

I blame this squarely on the JIT.

I like the idea of JIT, but the tooling is underdeveloped.
The hype says 'competitive with C for short numeric functions',
but the reality is 'somewhere between python and java'.
It's like a bus that drops you off halfway home and doesn't let you carry a bike.
Faster to bike all the way than walk half.

(If you don't know what a JIT is skip to the appendix or better yet, pick up Nim or something and never learn).

* toc
{:toc}

## JS JIT makes testing perf impossible

I don't know how to do these things in javascript:

* Know if a function is being optimized in a given run
* Know if a function *will be* optimized in prod
* Statically require that a function will be optimized in prod
* Get notified about deopts in hot paths

Absent some subset of those tricks, I have no way to perf-test my JS code without loadtesting at full scale.
This ends up being a huge waste of my time, and is the reason people rewrite JS services in other languages when they grow.

## Benchmarks lie

Is maybe a strong way of putting it.
But JIT languages make it difficult to use microbenchmarking to predict the performance of the same piece of code in prod,
for a few reasons:

* benchmarks (which run the same function with the same inputs 1 zillion times in a row) are very friendly to the jitter
* the function you're testing may be called with different inputs in prod. In JS, even the order of keys in an object can confuse the JIT typer
* if you benchmark a JIT/native function and your prod setup ends up using interpreted code, you've learned nothing

Not being able to know how long anything takes in reality leads to voodoo and gymnastics.

Yes, compiled languages have their own version of this with cache coherency.
Yes, jitting can lead to better performance than precompilation in theory because of the statistics collector.
But none of these things are under my control.

Call me an over-optimizer but this is a case where I prefer to have the *option* to drive stick.
Even if I switch to automatic in heavy traffic on the LIE.

## Writing performant code in (pick your poison) is easier

And more importantly, *maintaining* peformant code.
Don't get me wrong, I'm not saying (C++ / go / java) is a more productive language than JS.
But if your economics are such that servers are a bigger cost than payroll, keeping your core high-scale logic in an interpreted / JIT language is trouble.

For two reasons:

* optimizing hot paths: there will come a point where you need a code path to be faster and the JIT will make that work like picking up jello with tweezers (stop reading now to go try it)
* perf regressions: someone will at some point make a medium-to-large code change that subtly degrades performance and hurts product quality, and unless your monitoring is excellent, you *won't know*

People used to joke about 'writing crankshaft' (some V8 internal representation) rather than writing JS.
The idea that you need to understand something that is invisible and non-debuggable in order to write performant code is hard to live with.

## I'm not saying abandon JIT

I'm saying improve it.

All I'm asking for is information and control (details in the feature matrix below).
The basic premise of JIT of only compile parts of your program is fine with me.
I want to control which parts & when.

I want efficient stats collection about deopts in prod so I know which functions to treat as hot paths.

Compiled languages have a bag of tricks that are kind of on this topic:
statistically guided optimization, whole program optimization.
JITs will get there.

## Feature matrix

Things I want:

feature | exists in V8
---|---
compile short bits to native code quickly at runtime | yes
identify whether a section is getting optimized | no
know anything about the native code that's being run in a benchmark | no
statically require that a given section can & does get optimized | no
compile likely sections in advance to skip warmup | no
bonus: ship binaries with fully-compiled programs | no

## Appendix: what are JITs and why bother

If you opened this you probably know so I've put this at the bottom, but I've gotten complaints about using jargon in my writing.

Computers don't run the source code we write in programming languages, they run machine code.
Under normal circumstances, there are two ways to get from programming languages to machine code:

* Compilers, which create a machine code blob from your source code once, and you can run that blob over and over again. Slow compile, fast run.
* Interpreters, which read the program line by line as it runs and runs *another* program that executes those lines. Slower startup, slower performance, but no slow compile step after changes.

Compiled languages are faster and safer. Interpreted languages are more flexible, productive, and easier to learn.

JIT = 'Just in time' compilation, a method of compiling small pieces of interpreted languages while the program is running. It gives you the best of both worlds (or that's the sales pitch).

## Appendix: qualifications

I'm thinking more about the role of expertise in society and trying to emit less bullshit, so here are my qualifications on this topic for your review:

* I have years of professional experience as a programmer with various language paradigms (static, dynamic, JIT)
* I worked in a performance-constrained javascript codebase for 2 years and did some optimization work
* I've shipped projects in various language interop tools, including cython, C extensions to python, and a java plugin for react native
* I wrote a working [parser / interpreter](https://github.com/abe-winter/pg13-py) for a programming language
* I went to college for this (not that that means much)

{% include flatpixel.html tag="jitu-brutus" %}
