---
layout: post
title: FOSS must abandon privacy to survive
description: And set sane norms on data sharing
author: Abe Winter
date: 2018-10-01
---

1. toc
{:toc}

## Privacy-first FOSS can't compete with consumer products

The free and open source library ecosystem is thriving, but the app space is languishing. Libreoffice is shaky, gimp and inkscape have never been perfect, ubuntu has made big bets that didn't play out. <img src="https://anti.style/flatpixel/public-privacy">

Commercial software privacy policies typically preserve the right to use your data to 'improve their product offering', and if you've been on the inside you know companies really do use aggregate behavioral stats to inform feature design & maintenance.

The exception is FOSS. In general, free & open source software doesn't have the ability to:

1. use stats to understand how features are used and identify broken user flows
1. collect crash dumps so they can fix them
1. collect rich corpuses of behavioral and sensor data to develop whole new feature categories (like 'busy times' on google maps)

The reasons for this are various. Early open-sourcers like GNU's Stallman with a pro-privacy slant founded the community with their values. In the mobile space, things like crashlytics are verboten in the [f-droid inclusion policy](https://f-droid.org/docs/Inclusion_Policy/?title=Inclusion_Policy).

Culture aside, a lot of open source projects just don't have the infrastructure to collect usage and crash dumps, either because they're libraries rather than full apps or because they can't / don't run any infrastructure.

Ubuntu collects some kind of 'problem reporting' (presumably crash dumps) and has [started surveying basic system data](https://www.omgubuntu.co.uk/2018/02/ubuntu-data-collection-opt-out). I totally hate this **but** I'd also hate a world where their UX crashes so hard people start using windows again.

## FOSS data collection, unlike commercial / closed-source, is nominally prosocial

All else being equal I'd rather have FOSS collecting my data than a closed source / freemium product. Reasons:

* I can be more certain about what's being collected. No dark patterns or 'oops our bad' about what the privacy settings do.
* The data is more likely to end up in a public corpus that I can access and benefit from.

What's more, FOSS can lead the debate the about when and how data should be shared, and develop norms and tools to help build privacy-conscious software. A privacy linter developed for OSS would be used by self-conscious commercial software, and if we're lucky it would bring its norms and expectations with it.

## First steps

Someone should write up an open source license that:

1. is compliant with the law in major venues (looking at you GDPR)
1. establishes sane norms around anonymization, disclosure, consent and public use of the collected data
1. explains what happens when a library's privacy policy conflicts with the whole app's
1. is plug-and-play with respect to the obligation to open-source derivative works (i.e. you can BYO MIT/GPLv3)

The community should develop something github-like for collecting and sharing these stats.

Some privacy-related linting & static analysis would be nice too.
