---
title: Thoughts on LLMs as glue
description: Or as glue factory I guess
new: true
layout: post
---

I started thinking about this after trying a demo of AI dungeon and noticing 1) it isn't remembering state very well and 2) it doesn't know the map.

My other impetus was math;
like everyone else last fall, I asked it the 'bat and a ball cost five cents different' problem.
It was wrong, but if you told it to use a system of linear equations, it got it right.

My point in both of these examples:
LLM is a tool user.
Even if big models with big token memory can make some tasks better, the scaling approach doesn't scale as well as giving it the actual tools it needs.

1. toc
{:toc}

## Dual-process model

I didn't read that book, but the dual-process model of cognition says that humans solve problems using two approaches:
1. inference, where you use an analogy or a statistical hunch to find an answer that seems correct
1. modeling, where you carefully think about the problem using structured methods to increase the odds you're right

In LLM terms this means the LLM has a hunch, based on stuff it has read online, that the bat is 0.55 and the ball is 0.5.
But if you tell it to build a system of equations, it **translates** the problem into a model.
And it still uses a hunch to evaluate the model, but this often works better than using a hunch directly on the question.

(**Translates** is in bold because I want you to believe that LLMs are good at style transfer or translation tasks, because my whole argument below depends on that).

Also: once you have a system of linear equations, the LLM doesn't need to be the one to evaluate them.
You know what software is better at linear equations than an LLM?
If you're thinking BLAS, yes fine, but I'll accept 'literally any other software'.
Why not delegate to a system that is provably correct?
[Why is it that you don't want faster speeds](https://www.vice.com/en/article/4x3a53/comcast-investigating-customer-service-call-from-hell).

One-liner: let the artificial brain run its computer tasks on a tiny actual computer, rather than emulating[^emulate] them on a huge network trained on cognitive effluent.

[^emulate]: For interest: someone seems to have found out [where math lives](https://www.alignmentforum.org/posts/N6WM6hs7RQMKDhYjB/a-mechanistic-interpretability-analysis-of-grokking#Modular_Addition) in the neural net.

There's an approach called [chain of thought prompting](https://arxiv.org/abs/2201.11903) which provides an LLM with examples of how to reason, which causes the LLM to follow that model of reasoning.
Asking for a system of linear equations is slightly different, because with COTS, the 'question prompt' doesn't need to specify a method.

Meta has a demo called [Toolformer](https://arxiv.org/abs/2302.04761), where their LLM 'taught itself' to use a bunch of APIs.
'Taught itself' here means 'was force-fed' and is a clever gloss on what is essentially the same process as foie gras.
One of the APIs was a math engine.
Two things to note about Toolformer:
- They got good results with a much smaller LLM than you would need to do this pure-LLM
- The tool invocations ('API calls' basically) are human readable and checkable

'Smaller LLM' matters because these are expensive to train, your laptop can't run the big ones, and your phone definitely can't.

The remaining 3 sections are about external systems that should harness well to LLMs, and could pay dividends in capabilities, correctness, and small size.

## Research plans, plans generally

> I cut a longer section here about knowledge bases and SQL.
If you're reading this article, you've probably seen GPT's ability to emit SQL, and the law / finance integration that openai released.
The LLM factoid to know wrt knowledge bases is that they 'hallucinate' plausible answers and can't tell you what's in their index so can't cite;
querying external data is a way around this.

Querying an existing knowledge base is great, but creating one that doesn't exist is valuable secret sauce for your nation-state / ad platform / small business.
An interesting starting point is querying a database of all databases to figure out what databases to use to solve a problem.

Timely example of this:
how would you estimate the exposure of every bank to rate hikes.
Public datasets here include:
- Yield, term and asset quality hints in SEC EDGAR filings of public banks
- Source a list of all banks, including non-publicly-traded ones, from [FDIC data](https://www.fdic.gov/resources/data-tools/) or the fed
- Duration risk by asset class

(Like many 'create a dataset' problems in finance, this to some extent exists in [government filings](https://www.fdic.gov/resources/bankers/bank-financial-reports/), and probably exists in a private source).

I have yet to use an LLM with internet access, but friends say they've had bad luck getting sophisticated 'find and build dataset' queries to work.
Innovation researcher Ethan Mollick has been posting good thoughts about Bing as research assistant, and probably has tried a dataset construction project.

This is slightly beyond the curve today, but 'ingest and merge' feels near-horizon.
If you get it right, you can do a join query on the entire internet.
(If you use SQL a lot, though, you know joins can get expensive).

Research, of course, isn't limited to summarizing what is already known.
It may involve collecting new information, like with lidar cars, consumer surveys[^surveys], or lab-type R&D.
Let's say instead of 'find risky banks', your query is 'run the manhattan project':
manage the chemistry experiments and assembly lines, do portfolio management across multiple uncertain pathways, and come out with a working device at the end of it.

[^surveys]: LLMs are an interesting way to do consumer surveys for a lot of reasons:
    - they can ask follow-up questions to make sure you're paying attention
    - they can code freeform answers
    - they can capture exception cases ('you left out none of the above' is the most common in real life survey design) and evolve themselves based on complaints or feedback

    <br>Consumer surveys are sort of important and sort of bad. Doing this better is worth a lot to companies that use consumer research for anything. For me personally, the ability to 'scientifically' create marketing personas and learn about them is potentially useful, but for sales + partnership stuff this is harder to do; I'm not going to ask a high-value partner to chat with a robot for ten minutes.

There's no standard code-like output format for 'JIRA for big experiments' (or JIRA for experiments, or JIRA period).
If there were, LLMs would gain superpowers around projects that weren't just 'fetch and merge data', but involved R&D with try-fail and hard problem solving.
(This isn't to say they'd be the best tool for this 'R&D management' job).

## Actual reasoning

At least with 3.5, it's obviously not reasoning from knowledge; if it is reasoning at all, it's doing it from immediate context using the 'textural' features of GPT's attention -- its ability to make things make sense that are next to each other.

A simple example of it's failure to reason -- it has no problem uttering statements that are mutually exclusive, and has a hard time feeling shame when you call it on this.

But as with the linear equations above, you can tease it into doing better.
Asking it to **translate** a statement[^stmt] into predicate logic can sometimes kick it into doing actual reasoning, instead of the 'textural' correctness it does by default.

[^stmt]: My predicate logic example was if a loose cannon cop from a 90s action movie made an arrest in the google antitrust case, and the arrest went wrong, and google ended up fleeing using their driverless car fleet as decoys, would the pursuing officer incur liability? (GPT had previously implied they would).

    GPT did not like this example at all.
To even get it to consider this case, I had to say it was for an HR training.
It was a good GPT and I was a bad user.

Predicate logic is a tool that 'seemed like AI' in the dark ages before deep learning.

If you're imagining that predicate logic is rigid and can't handle ambiguity, it can these days.
Markov logic is a 'try your best' semantic graph method that resolves the logic relationships for a situation to tease out consistent and inconsistent statements.
Some more recent work uses LLM-like embeddings in the context of logic graphs, but the downside of embeddings is they're not human readable / checkable.

In the olden days these systems relied on carefully constructed knowledge bases in a form that the rule engine could process.
But LLMs can use their semantic understanding of a situation to build a small semantic graph.

## SIMULACRA AND SIMULATIONS

> After writing this I found the janus [GPT as simulator](https://www.lesswrong.com/posts/vJFdjigzmcXMhNTsx/simulators) post[^lesswrong]. It seems to be concerned with GPT accidentally developing the ability to run sims internally, rather than *emitting* auditable simulation code, but hits many of the same themes.

[^lesswrong]: This links to lesswrong, which is a kind of zany place and which, from the outside, seems increasingly concerned with AI alignment which, again from the outside, may be better than the stuff they previously talked about. I think / hope they're a hammer with an overzealous nail detector. The alternative is they're a nail cult that has been building nail detectors and nobody took them seriously before, like the ghostbusters.

    The lesswrong post also talks about wrapper minds which are, I gather, dumb optimizers built around smart AI. For clarity, LLMs emitting simulations is probably not a wrapper mind per their definition.

Knowledge base integrations can improve the machine's ability to fetch and store existing knowledge.
Reasoning middlewares can improve the machine's ability to draw correct conclusions from that knowledge.
But simulation can create *new* knowledge.

The pre-AI example of 'knowledge from simulations' is scenario planning, where big companies hire domain experts to write up possible futures.
My old go-to was the [long-term studies group at royal dutch shell](https://hbr.org/2013/05/living-in-the-futures), where they weathered the 1973 oil embargo better than competitors because they had run a supply shock scenario.
My new favorite is [El-Erian's retro on the Lehman collapse](https://www.nytimes.com/2022/12/09/podcasts/transcript-ezra-klein-interviews-mohamed-el-erian.html), where pimco prepared three scenarios, their 3% likelihood one came to pass, and they were still more prepared than the competition.

The goal of these isn't to predict the future but to do cheap (ish) preparation for expensive problems.
As with other knowledge work, 'cheap' is relative and AI makes knowledge work much cheaper.

Simulation is used almost universally in reinforcement learning (a different type of AI training from what is used in LLMs).
LLMs emitting sims can certainly use them to train RLs, but even without RL, simulations can be used to provide plausible, checkable answers to questions.

Because of their ability to bridge semantic and quantitative descriptions, LLMs can also 'role play' aspects of the system that it doesn't know how to model numerically, while still simulating the rest.
I heard a defense one podcast a while ago which said tabletop simulation is powerful because it brings together different types of expert.
LLMs aren't experts exactly, but they do contain some degree of domain-specific common sense.

In principle, simulation design is the same as emitting any other kind of code or specification.
The [Mesa agent sim tool](https://mesa.readthedocs.io/en/stable/tutorials/intro_tutorial.html) is python, as is [Hash](https://hash.ai/blog/reinforcement-learning-in-hash-simulations), as is the game theory environment [Axelrod](https://github.com/Axelrod-Python/Axelrod).
The [GAMS modeling system](https://github.com/DREAM-DK/MAKRO/blob/main/Model/pricing.gms), and its offspring GAMA, use a sort of declarative programming language.
The various gyms are programmable, and [integrate well with reinforcement learning libraries](https://docs.ray.io/en/latest/rllib/rllib-env.html#configuring-environments).
(You would probably want to fine-tune a model because these are not as widely used as, say, express-js).

I wish there were a standard declarative DSL for agent sims --
I would use it personally, but especially as an AI codegen target, I have a hunch DSLs will lead to more powerful and reliable superpowers.

Why:
LMs are good at translation, and DSLs are intentionally similar to the domain-specific problem statement.
Declarative specs, vs imperative code, decouple description from execution, which means the AI only has to write the 'situation specific' piece; it gets to leverage well-tested, probably-correct execution logic.
DSLs often lead to short, low-boilerplate code snippets that emit a predictable data format, rather than text output that must be parsed.
Also, as long as token width is limited in these models, terse is better.

Types of problems that are tractable to simulation but hard to solve analytically:
- The answer depends on a network structure; for example supply chain questions that depend on geography. Google maps even -- you need to use something a lot like simulation to figure out whether to take the tunnel or the bridge
- Effects emerge after multiple steps, with knock-on effects between heterogeneous systems, and price and demand dynamics. For example people leave cities in the pandemic, and cause a suburban real estate boom, and lumber futures go up
- Problems with stochastic shocks
- Analogy on existing knowledge isn't sufficient to get the information, or there is no existing knowledge, but physical simulation can do the trick
- Behavior of a system is modeled, and output data is available, and you want to predict inputs. For example, given that Russia invaded Ukraine, what does that tell us about their armament or leadership structure

My favorite *fictional* simulation is 'personality retrieval' from Dan Simmons.
(I'm not going to fully spoil it, so ignore this paragraph if it makes no sense).
Not the cybrid detective, who was an abnormal retrieval, but Fedmahn Kassad's training constructs.
I think Simmons was just trying to mix Teilhard-era psychic mumbo jumbo with high-compute AI and quantum mysticism, but he somehow produced an idea that is wonderful beyond any fair expectation.

FWIW the standard retrieval personas eventually went insane.

The real-life simulation problem I care most about today:
given what I know about my marketing personas and channel performance, model the paid and viral growth of my social platform, and help me do portfolio management across my growth levers: partnerships, paid acquisition, and feature development.

(Sorry for the anticlimactic end. [Subscribe](https://tinyletter.com/abe-winter) would you?).

## Notes
{:.no_toc}

{% include flatpixel.html %}
