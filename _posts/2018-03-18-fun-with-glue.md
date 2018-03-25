---
layout: post
title: Fun with glue and reliable integration
description: Something about glue code
categories: reliable-automation
date: 2018-03-18
---

This collects some thoughts from using kubernetes and luigi to orchestrate largish systems on various public clouds. <img src="https://anti.style/flatpixel/fun-with-glue" style="display:inline">

Have you ever toggled the input sources on a modern TV, and the control delay is such that when you get a signal you're never sure which source you're using?

This post is about that except the TV is in virginia and the remote control is assembled from scripting languages and APIs.

1. outline
{:toc}

# Glue vs control

A fact to cope with as software eats the world: software systems are held together by glue.

I'm defining 'glue' here to be code that doesn't run where it's supposed to. Glue runs outside the main control loop of the system being managed. We often say 'glue language' because once our code isn't running inside a system we pick an easy language to work in.

I like the term [inversion of control](https://martinfowler.com/bliki/InversionOfControl.html) for talking about the pros and cons of the glue approach.

Glue buys me the ability to use an easy scripting language, on my laptop, with simple APIs, and without having to risk running untested code in critical control loops. This comes at the cost of being badly situated to *control* the system.

'Control' I use here in the sense of control theory: using inputs & outputs to maintain a system in equilibrium or changing its state. The goal is to do this quickly, safely, and using information that is late or bad.

# Idempotency vs control

Idempotency is a common concern as we run larger distributed systems and ask more of them from afar.

Idempotency matters *a lot* in glue languages because when a command isn't guaranteed to have the desired effect, you need to create feedback mechanisms to decide which command to run. And because glue code doesn't run inside the main control loop of your system, collecting feedback is clunky and non-atomic.

When glue code has to do a lot of checking, it begins to feel less like glue and more like tar. Glue is an easy way to stick two things together, non-toxic and safe for children. Tar is not that sticky, dries slowly, bogs you down, and if you're trapped in it long enough you become a fossil.

I want to propose three hand-wavy claims about idempotency and control systems:

1. Idempotency != control. Idempotency necessarily *gives up* control over time & change. If you want two subsystems to change simultaneously, with zero downtime, unless your config system has a primitive for that, you won't be able to. It's nontrivial to make idempotent operations overlap.
1. Idempotent operations on complex systems rely on good control systems in the next layer down
1. Systems providing idempotent primitives are not easily extensible. It's difficult to build control systems on top of complex idempotent operations because idempotent ops (a) don't overlap well and (b) don't output feedback until they're done. In other words, idempotency is a property of the highest layer of your system because it's hard to build control systems on top of it.

These are problems I've experienced while building tools to manage large-scale systems. I'm not sure if they're generally true.

I don't hate the etcd model of editing configs and letting your system gradually get the updates. It's not awesome that config changes aren't picked up immediately, but I've never worked with an imperative system that delivered really fast changes on big systems.

# Everything is non-interactive until it breaks

> No user-serviceable parts within

That's the sticker on every future-tech device in [Rainbows End](https://en.wikipedia.org/wiki/Rainbows_End). And headless systems are great until something goes wrong.

Vinge, the author of that book, is best known for inventing cyberspace. To me, his most important idea is the role of systems reliability in the long-term viability of civilizations. Fire Upon the Deep changed the way I think about history.

When we interact with headless systems, the button we use is often made out of glue, probably because interaction was an afterthought in their design. Think about the difference between a car from the 70s (mechanical linkages everywhere, carburetor instead of fuel injection). Compare that vs now where [the only way to slow down your cruise control is to open the door](http://www.scmp.com/news/china/society/article/2137662/mainland-driver-takes-white-knuckle-trip-car-wont-slow-down).

Most tools that I've used to automate batch work are difficult to manage when something goes wrong. This is everything from cron to queues to the tree-scheduler luigi. It's difficult to view the internal state of a running system, even harder to stop it, and hardest to pause and resume.

Good automation needs to be good at managing the handoff to an operator and this is hard to get right, as [Toyota](http://articles.sae.org/15207/) and [the NHTSA](https://www.popsci.com/people-are-bad-at-taking-over-from-autonomous-cars) have learned. I read a great article a few years ago about careers in supervising robots which I can't find now or I would link it here.

The French equivalent of the ATSB found that the [Air France 447 crash](https://www.thedailybeast.com/air-france-flight-447-crash-report-airbus-autopilot-to-blame) happened right after autopilot shut down because of icing. A junior pilot panicked and pulled back on the stick, thinking the plane was crashing, even though the aircraft was pitched up. The pilot in command knew the plane was pitched up but, because the joysticks aren't physically linked, didn't know why -- he didn't know that the copilot was pulling back on his joystick.

I'm no pilot but at least once I week I make a bad operations decision because of missing information. Example: stopping a process and rerunning manually because its progress monitor isn't granular enough to know if it's stuck.

447 wasn't an autopilot bug. It was the sort of complex failure that happens at the intersection of autonomous handoff, instrument quality, and operability. I hope you've already read [How Complex Systems Fail](http://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf) but if you haven't, stop reading my post and print yourself a copy of that.

Glue vs tar is relevant to the long-term reliability of civilizations. Controlling & managing complex systems is becoming a big deal.

# Reliable automation and the future of glue

What is the future of glue?

Glue is easier than ever to get ahold of and so we're using it more. I think people are generally conscious that if enough logic is dwelling in the glue layer, it's time to move some of it into the system's control loop.

A new generation of ML-based systems management tools are fast aborning, like [G's datacenter cooling manager](https://deepmind.com/blog/deepmind-ai-reduces-google-data-centre-cooling-bill-40/), and that's interesting because ML is close enough to control theory that ML tools will need to run inside systems; only relatively simple models that use minimal data to make infrequent adjustments can run through an API.

Ultimately all we want is commands and tools that work every time, and systems that manage themselves, and we'll have to achieve that with a combination of loosely-coupled glue and tightly-coupled control systems.

Better ecosystem tools may also allow us to design safer ways to integrate more tightly with systems' control loops. An example from deep in history: When Microsoft wanted to improve the reliability of Windows XP, they built a [symbolic execution system](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/eurosys2006-1.pdf) to statically analyze how drivers interacted with the kernel.

Faced with the need to solve control problems and unwilling to take the performance hit of pushing drivers out of the kernel (minix style), the XP team built powerful simulation tools to increase safety.

My fingers are crossed that we'll build more powerful simulation tools for integrating with headless systems. It's one way to move past glue in problems that are both performance and safety critical. I have no doubt that more of these problems are coming.
