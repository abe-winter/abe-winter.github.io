---
layout: post
title: I've wanted enumerable classes for *so long*
author: Abe Winter
date: 2019-01-19
noindex: true
---

First class language support for iterating the storage fields of a struct is *so useful* and nobody is supporting it in their language.

It's 2019 and you shouldn't need to write an AST to operate generically over a class. I pray my coworkers don't read this blog but real talk, I've written like two AST walkers for javascript in the last 12 months and a dataflow tool for call graphs because *I felt like I needed them* and then never told anyone or checked them in because I was too embarrassed.

I have to imagine I'm not the only one in this boat.

1. toc
{:toc}

## State of language support

I feel like I read a draft of 'enumerable classes' support for C++1x but I can't find it now so I'm guessing it was a rare happy dream about C++.

Python can presumably do it with dataclasses as of the latest release, but python approaches this problem from the opposite side -- python class instances have never strictly speaking had attributes (`__slots__` was never really embraced).

```python
>>> class C:
...   def __init__(self): self.a = self.b = 1
...   def x(): return 'y'
... 
>>> dir(C())
['__doc__', '__init__', '__module__', 'a', 'b', 'x']
>>> # which are the attributes?
```

Javascript is in some ways similar to python on this. They're getting more serious about class properties as a feature, but if you use flow for JS typing fat chance getting your type system working reliably with code that operates over types at runtime. There's `ObjMap<>` I guess, and typescript has a slightly better one?

In rust you can do it but the rust macro syntax is impenetrable and insane.

I *guess* you can do it with `go:generate` but once again, good luck. Last time I looked at this (admittedly 18 months ago) the level of integration between go:generate and the rest of the buildsystem was somewhere between alpha & aspirational. Also it was easier to write a parser for go in python than to make do with whatever go was providing from the native library.

I'm assuming java reflection is rock solid and full-featured at a serious performance penalty. I've used scala reflection, which I'm assuming is built on java reflection, under protest and I recall it being a beast.

This is *such an easy feature to write*. The language knows what shape classes are at compile time. Looping polymorphically over class elements is not a huge ask.

## Use cases

The obvious use case for this is at the serialization boundary.

ORMs are everyone's least-favorite swiss-army knife attachment but they're also the only tool that opens their particular can of worms. Enumeration of class properties would make ORMs *so much easier* to write for library authors, and more importantly easier to use for consumer-developers.

## Misc thoughts on future language features

[Graydon Hoare also wrote an article about this](http://graydon2.dreamwidth.org/253769.html) and is an expert on this topic -- read his first and then come back and read mine.

I think we're at peak JIT. I always feel like I have to be smarter than the JIT to get it to work for me. And it's completely nontransparent. I still don't know how to audit deopts in nodejs, and it seems like every time someone releases a tool for this the v8 team deprecates it.

I'm looking forward to compiled languages with typesystems and buildsystems that are more featureful, if not necessarily more sophisticated. There are relatively few shops using ocaml & haskell in production I think? But more people are getting on board for code generation, especially when the code gen is maintained within a 3rd-party library.

Array bounds are important. Type-systems should allow the user to express constraints like shorter-than and same-size. I think this opens up new options for static safety as well as malloc optimization.

Enforcing rules across the whole codebase, i.e. sophisticated call graph linting and ordering constraints. 'No mallocs below this call' would be interesting, or 'lint on amount of IO beneath this call'. 'Must be within a lock' can be enforced statically instead of at runtime.

Business logic and the type system will blur together. Serious teams view linting as part of the task of delivering safe code at scale from complex codebases. That's why as JS took over the web, google wrote closure, facebook wrote flow and msft wrote typescript.

(These JS type layers are great tools and I don't think it's a coincidence that they came out of a language that someone designed over a weekend at netscape -- this isn't a dis, it's just an observation: flowers bloom in crap).

Most companies can't afford to develop their own static checkers for dynamic languages, so I see the next generation of industry languages providing pluggable typesystems so that big codebases can enforce the rules that matter to their authors & operators.

{% include flatpixel.html tag="enumerable" %}
