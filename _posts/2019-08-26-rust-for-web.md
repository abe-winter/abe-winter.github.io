---
layout: post
title: Picking rust for web
description: "I'm trading in my chevy for a cadillac ac ac ac ac ac"
categories: wisdom
---

I've been staring at this [energy efficiency across programming languages](https://thenewstack.io/which-programming-languages-use-the-least-electricity/) table for days. It can't be right (why is typescript so much worse than javascript?) but a lot of it tracks with things I've observed from using these languages IRL. Also this [web framework benchmarks](https://github.com/the-benchmarker/web-frameworks#full-table-1) project.

Bottom line: I'm thinking about using rust as the backend for a small one-person web project. Here's everything I said to myself while researching reasons not to.

1. toc
{:toc}

## Go has way better libraries

Go stands out as the compromise choice of the modern web and I don't mean that in a bad way. It's fast enough, it's compiled enough (though my understanding is that certain loop operations are effectively untyped / interpreted). A massive amount of research have gone into GC speed and memory efficiency.

I read somewhere that the G team that built it intended it as a competitor to C and it ended up replacing python. Python was known early on for its good library ecosystem and I think go has picked up that torch, especially for backend web.

I think go has better core web hosting libraries than JS / python if you want to do something fancy like oauth. I've never tried to do something in go and been like 'crap my framework doesn't have sessions built in'. Ruby is probably better here (omniauth seemed like the best oauth client library in *any* language when I searched once) but I've never used it.

## Python / JS more productive

At this point I've used python as much as I've done anything else in my life. I'm *very* productive in python, and python is a productive language. I've watched learning curves for programmers and non-programmers in python and non-python codebases and everyone can learn it. I've used both python and go for backend web stuff and python is generally more powerful unless you care about speed.

I'm less certain about javascript as a productive language. My experience on frontend and backend has been obtuse tooling, language feature and version support that's as spotty as the T-mobile coverage map, more verbosity than an interpreted language can justify, weak standard library and WACKY libraries.

I suspect ruby has really good productivity for web but I've never used it and am uncomfortable with the performance compromise. I suspect also that the moment I have a performance quirk I'll have to break their architecture contract and productivity will go out the window (once again, this isn't experience talking, it's paranoia).

## JVM is everywhere

I thought seriously about java. New java is a not-bad language and like go, it's a compromise choice in a good way.

But installing java on linux has always made me sad and asked me to make weird choices. Their patent battle against google feels like a louder version of something they've been telling me via EULA since I was a teenager trying to make my applets work. Honestly, it's something I don't want to hear. Thanks but no thanks java.

Also, while the language is increasingly modern, the libraries are going to have a mix of support for ancient and modern and it was my job for a brief period to upgrade a java dependency without breaking the other dependencies in a big project. Not fun.

Ruling out java rules out other JVM languages I think as well. I'm also generally not a fan of them, especially scala which I've touched the most.

## C++ has buy-in

I know and understand the developer productivity hit for rust. Rust is probably even with C++ in this because there are fewer surprises at runtime but more fighting with the compiler. I personally prefer C++ templating to rust hygienic macros but rationally speaking I'm on the fence.

But C++ is a healthy language with cool tools and buy in from big heads in the industry. It's not going anywhere, whereas rust could; for every big co that funds or in-houses C++ language development, there's more who would have an incentive to do so if needed. C++ has many LOC in the wild that rich people want to keep working. Rust could run out of money, the bench isn't as deep.

On the library side, C++ has less stuff *but* has interest from the most perf-minded developers. But I HATE boost (not that I have to use it). And C++'s packaging tools are still bad. Rust feels like a risky bet but also like a better investment in the future. The basic primitives are better.

C++ doesn't have an import keyword, even though it was kind of on the roadmap and I think [microsoft got it working](https://docs.microsoft.com/en-us/cpp/preprocessor/hash-import-directive-cpp). (Also [I wrote an import keyword for C](https://github.com/abe-winter/cbuns)). Import matters because it's a simple way to include third party code without taking a huge hit on compile time.

## Haskell, yeah

People like haskell. Honestly the safety argument for functional programming has never totally made sense to me. I believe that haskell allows me to statically assert *some properties* but certainly not all the properties I care about.

I'm not familiar with the performance and productivity tradeoffs, and the syntax feels obtuse.

Also what the fuck is a monad. Nobody can define a monad in a way that makes sense in a non-functional language -- to me that makes it a solution to a problem normal people don't have. Like special gloves for petting a shark back to front. Who wants to do that to a shark?

People say haskell's GC is pretty fast now but go's is also fine and from my rust perspective, I *got* a man. (How long have you had that problem?)

I'm willing to believe that these problems are *my* problems. If a book hits you in the head and makes a hollow sound, it may not be the fault of the book. That said, these problems *are* my problems so haskell, or even ocaml, which I've had a crush on since mirageos, are probably not going to be a fit.

## What ended up mattering to me

**Safety**. I'd much rather fight with the compiler a little than fight with runtime.

**Good ORM**. go's ORMs (admittedly this was 2 years ago) shocked and offended me, and go's typing in general feels incomplete -- runtime-heavy, compile-time-light. Not a fan of python SQLAlchemy or node sequelize. I've written my share of SQL tools ([language-agnostic migrations](https://github.com/abe-winter/automigrate), [a \_\_slots\_\_ orm](https://github.com/abe-winter/metamod), [sql emulation for tests](https://github.com/abe-winter/pg13-py)) and the fact that I did this to myself means something is up with the ecosystem here. I'm willing to give rust's a try.

**Scalability**. I probably won't be facing the scale that I deal with in my day job, but there are lots of good reasons to use less hardware. Compact architecture is good. If I can run fewer API processes, I can use that budget for ads, or for sharding across regions. And cloud isn't cheap -- rust vs python could realistically save a few hundred dollars for a medium traffic thing every month. Being able to fit all my crap on fewer boxes matters.

**Predictable tradeoffs**. I'm tired of interpreted languages and their warts. I'm willing to pay a little more up-front to be operationally smooth. Slow webpack / babel builds are just as bad as rust (well, maybe). I might as well be compiled and save the boot-time slowness.

I'm ready for fewer surprises. Do I need to scale in an emergency? Will I run out of memory unexpectedly? (Though python is better than java/javascript on memory). This is all less likely in a non-GC, fast language.

Will the JIT be slow the first couple of times? Do I have to worry about whether a function is getting optimized correctly? JS/V8 provides you with NO WAY to answer that question in normal practice. (Send me a link to a working example and I'll correct this). rust means never having to ask that question.

Yes, I've been building for insane scale at work, but I'm tired of not having the tools with JS to answer any of my questions. Some of which I wouldn't have to ask with a compiled, non-GC language.

## Wisdom

I know the established wisdom here is to focus on developer productivity, especially pre-launch.

But I've been burned enough times in enough ways by what I think of as 'medium scale' problems: hitting low-ish connection limits on managed services, running out of memory because of limits + unreasonable use, CPU bottlenecks in unexpected places. Annoyances from things taking a long time to start or 'warm up'.

I may feel differently in three months, but for now I'm tired of my javascript problems at work and I'm ready to have a different set of problems in my home life.

{% include flatpixel.html tag="rust-for-web" %}
