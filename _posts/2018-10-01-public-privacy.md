---
layout: post
title: To survive, FOSS has to steal my data like the adults
description: Time to leave the sidelines
author: Abe Winter
date: 2018-10-01
---

1. toc
{:toc}

## Privacy-first FOSS can't compete with consumer products

Most software privacy policies preserve the right to use your data to 'improve their product offering', and if you've been on the inside you know companies use aggregate behavioral stats to make all kinds of decisions. <img src="https://anti.style/flatpixel/public-privacy">

The exception is FOSS. In general, free & open source software doesn't have the ability to:

1. detect when a user flow isn't working
1. use stats to understand which features matter
1. collect crash dumps so they can fix them
1. collect rich location and behavioral data to develop whole new feature categories (like 'busy times' on google maps)

The reasons for this are various. Early open-sourcers like GNU's Stallman with a pro-privacy slant founded the community with their values. In the mobile space, things like crashlytics are verboten in the [f-droid inclusion policy](https://f-droid.org/docs/Inclusion_Policy/?title=Inclusion_Policy).

Culture aside, a lot of open source projects just don't have the infrastructure to collect usage and crash dumps, either because they're libraries rather than full apps or because they can't / don't run any infrastructure.

Ubuntu collects some kind of 'problem reporting' (presumably crash dumps) and has [started surveying basic system data](https://www.omgubuntu.co.uk/2018/02/ubuntu-data-collection-opt-out). I totally hate this **but** I'd also hate a world where their UX crashes so hard people start using windows again.

## Data for improving FOSS isn't the same as data for monetization

All else being equal I'd rather have FOSS collecting my data than a closed source / freemium product. Reasons:

* I can be more certain about what's being collected. No dark patterns or 'oops our bad' about what the privacy settings do.
* The data is more likely to end up in a public corpus that I can access and benefit from.

That said, why isn't it better for open source software to be strictly private?

Because the ecosystem relies on people using the software, and without data nobody will want to use it. The experience will be *so much worse* than the magic you can get from a highly tested, high-feedback device / app.

If OSS doesn't have users, it won't exist, and you'll have no alternative to the completely opaque market leader you use now.

Data-sharing with FOSS has at least a chance of not ending up in a massive consumer database, and of being anonymized enough to not upset the balance of power between private citizens and law enforcement.

FOSS can lead the debate the about when and how data should be shared, but not if it stays on the sidelines.

## Next steps

Someone should write up an open source license that:

1. is compliant with the law in major venues (looking at you GDPR)
1. establishes sane norms around anonymization, disclosure, consent and public use of the collected data
1. explains what happens when a library's privacy policy conflicts with the whole app's
1. is plug-and-play with respect to the obligation to open-source derivative works (i.e. you can BYO MIT/GPLv3)

The community should develop something github-like for collecting and sharing these stats.

Some privacy-related linting & static analysis would be nice too.
