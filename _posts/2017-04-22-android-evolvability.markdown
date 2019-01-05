---
layout: post
title:  Android, evolvability & comcast
date:   2017-04-23 12:00:00 -0400
categories: evolvability
visible: true
---

One of my best friends in college decided to get all his calories from chocolate-chip-cookie-peanut-butter sandwiches for a whole quarter. In case you're imagining bread in there, no: it's just peanut butter between two cookies. As an experiment, he also went all quarter never, or seldom, washing his hands. We lived in the same dorm and you could tell where he'd been by an oily glitter on banisters and doorknobs.

The visceral reaction you're having to that image? That's how I feel every time I interact with the java ecosystem, and android has been even worse.

(Scroll down to 'Constructive criticism' at the end to skip the argument and go straight to the punchline, which is that we need single-file builds in android).

### This doesn't feel like programming

Earlier this year a project needed an android app and because it didn't have to look good or work well I elected myself to build it. It was traumatic so I took copious notes, summarized here:

* **Day 1**: I get that I'm new at this but it doesn't feel like programming.
* **Day 3**: What does it feel like? Signing up for an institutional account like a bank or health insurance. There are terms with special definitions, everyday words that take on a special meaning. If I get them wrong I may be accused of lying and lose my coverage.
* **Day 4**: It feels like something that's difficult by design, like terminating service on a comcast account. Most of the errors and warnings from the buildsystem are unnecessary. This feels like ['help me understand why you don't want faster speed'](https://soundcloud.com/ryan-block-10/comcastic-service). It wouldn't be hard to make this better; I don't understand why it's not.
* **Week 2**: Making my second ListView. I should be hitting my stride by now. But I'm more frustrated than before. The second time isn't easier. I know how to do this now, so I'm seeking optimizations, ways to turn boilerplate blocks into one-liners, but android is resisting me. The toothless declarative layout language inserts itself into everything but can't be used without plentiful code support as well.

### Evolvability

Around the end of this experiment I read an article about life, physics and the concept of 'evolvability'. Evolvability, as I understand it, means that a single token (or single base-pair) change in a set of instructions can produce:

* A non-viable organism
* A highly similar organism
* A viable organism that's different in a big way (extra set of legs, bigger wings, sees in the dark)

The third option is the 'most evolvable'.

A web-oriented example: changing one byte of a PNG will change a color, create visual artifacts, or create an unprocessable file. Changing one byte of an SVG file could change the radius of a circle.

If you're new to this concept read this 2013 paper on [producing modular gene networks in simulated environments](https://arxiv.org/abs/1207.2743).

### One liners matter

Java is pretty bad at producing portable one-liners. In my opinion that's because of the public/private feature (completely unnecessary), a fixation on classes being somehow related to files on the filesystem (who cares what file something's in), and a cultural preference for hard-to-use, one-off constructors.

Android, which is the combination of java, gradle, android studio, the android libraries, and the layout system, is even worse. Tying everything to contexts / fragments / activities makes android constructors even less reusable than POJO. Harnessing the XML layout system to code is also way too hard -- creating a custom widget, for example, requires several files.

This is half technology and half culture. For some reason when I write a line like `WhateverClass wc = new WhateverClass();` android studio wants me to split it onto 2 lines. wtf.

Switching back to evolvability -- needing to paste in several lines of junk to use a feature in a new context has two bad side effects:

1. <u>Cost to change</u>: the reason java has relatively good refactoring tools is because better languages can do the same job with find-and-replace or indirection
1. <u>Compatibility / reusability</u>: highly-customized, expensive-to-instantiate (in terms of lines of code) classes are more likely, in my opinion, to rely on some special member or local and be unusable in other contexts. Leading to over-specialization.

I don't think one-liners is a realistic short term goal for android -- there's too much kruft in the standard library. What **is** a realistic goal? Keep reading.

### Constructive criticism

When I get the call from G's android team to build a better buildsystem, what will I do in month 1?

We need to be able to build apps from a single file. That's the low-hanging fruit for android improvement. Bonus points if a small app (< 500 lines) can build in under a second.

Why is this important?

* <u>Docs and forums get easier to use</u>: most of the android docs I copied don't build, most examples are incomplete, the others are *too* complete (i.e. too long)
* <u>Usable defaults</u>: removing config files as a required input forces us to have usable defaults. Android insiders might argue that there are usable defaults encoded into android studio or gradle, which get applied when you initialize a project. Okay, but now I own 15 config files and have to maintain them.
* <u>Enable experimentation</u>. I have a pretty fast laptop and relying on gradle / android studio for anything is still slow. If I could create a usable android app in 10 lines without relying on a project template generator, XML files, and autocomplete, I could learn things and get them right 'in the small' and then incorporate to my project.

{% include flatpixel.html tag="android-evolvability" %}
