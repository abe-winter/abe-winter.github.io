---
layout: post
title: Apple's privacy brag should ring false to open source people
author: Abe Winter
date: 2019-06-23
description: Minimize, deny, justify, blame
categories: brags
---

1. toc
{:toc}

## Trust but verify

Apple is pursuing this public shtick of 'apple makes you safer' and it may even be true. Here's a [relatively recent thread](https://mobile.twitter.com/Snowden/status/968222371764195329) between maciej ceglowski & edward snowden asking whether android has caught up for 'low tech, high risk' users. 'Not quite' seems like the answer.

But from an open source perspective, neither system is delivering **any** guarantees. Whatever they say with their mouths, you have no idea what's really running on the device. Keeping your device up to date is good security advice probably, but if you don't trust your vendor (either from an intent perspective *or* competence), updates are a big pile of steaming software supply chain risk.

When the FBI wanted in to a phone, an obvious thing they tried was [compelling apple to send a software update](https://daveverwer.com/blog/saying-goodbye-to-app-review-times/):

<style>
blockquote { font-style: normal; letter-spacing: normal; }
</style>

> The government sought an order compelling Apple to write a software update undoing the security protections Apple had built into the iPhone 5c. These included eliminating the limit of ten PIN tries to unlock the phone—after that, the phone’s data would be erased—and speeding up the ways the PINs could be entered.

There are ways to mitigate this vulnerability in cases where the phone is locked, but the only general defense against this is open source. The linux community is [getting serious about reproducible builds](https://www.coreinfrastructure.org/announcements/the-linux-foundations-core-infrastructure-initiative-renews-funding-for-reproducible-builds-project/) as a final farewell to anyone claiming closed software is safe.

It wasn't that long ago that every phone came with spyware or at least crapware from the mobile network. The situation is even more complicated in the android world, where some no-name device makers were [bundling an 'advanced backdoor'](https://arstechnica.com/information-technology/2019/06/google-confirms-2017-supply-chain-attack-that-sneaked-backdoor-on-android-devices/) from the factory.

Has apple ever sent a 'bad update'? They [handicapped devices via software updates](https://www.ifixit.com/News/batterygate-timeline) to hide the fact that their hardware sucks nuts. Sure the update was technically a fix. To me this is [standard institutional behavior](https://youtu.be/MBD6e6mmjp8?t=14) and ["conduct that you would not let your children do"](https://www.defenseone.com/ideas/2019/06/ep-45-former-defense-secretary-ash-carter/157871/) (circa 18:50).

## Who benefits from the walled garden

Apple's public arguments about privacy ('on android you're the product not the customer') ultimately come down to them saying the consumer's incentives are more aligned with them than big G.

I guess. But you know who apple really hates? *App developers*. I'm not exaggerating. The app store review process is full of gotchas that 'keep consumers safe' by protecting apple's revenue. Like every complex set of rules administered by an institution, it's easy to adjust the degree of vetting. Various apps and SDKs get stuck in review or (in the case of SDKs) banned completely when apple is working up to release their in-house version. I suspect I could prove this given a DB of delays & rejections for top-500 apps.

On the apple platform, consumer vs app maker is a key distinction. But in the OSS world it's a continuum. If you want to embrace your identity as a [tube that consumes WWDC demos and excretes IAP margin](https://en.wikipedia.org/wiki/HumancentiPad), great. If you want to make or install anything that apple doesn't approve of, or even worse, install something without *asking* their approval, dark skies ahead.

When facebook sinned against these principles, apple retaliated by [breaking the lunch menu](https://www.cultofmac.com/603734/apple-breaks-facebooks-internal-apps/) and also probably slowing down some work at FB. For all their platform dominance, FB doesn't own a mobile platform and relies on the good graces of the big 2. FB's sin: paying users to sideload an app. Apple hates sideloading.

Also I don't understand how a company can have a reputation for privacy and simultaneously give an encryption key to facebook and act surprised when it gets misused.

I don't believe the walled garden = consumer safety. In my opinion, any argument about an app's safety has to come from the robustness of the OS's permission system, and potentially also from vetting the code / trusting the author. A strong OS-level permission layer has nothing to do with the walled garden.

## Can an open phone platform succeed?

It's 2019 and there's [finally a linux phone coming to the market](https://puri.sm/products/librem-5/). 

Both apple and google are using their market power to prevent competitors from innovating on top of their platform. This is more visible in the android world where device makers are threatened with losing access to the closed-source layer (i.e. maps, gmail, play store) that lives on top of the open source OS.

The linux phone will be hard to use, have limited apps, and a small audience initially. It will also be the only mobile phone hardware that doesn't give you a hard time when you want to run software on it. (It's not just apple -- installing android studio makes me want to take a shower. The build tools for linux will be so small and nice by comparison).

There's an argument that consumers won't want this, but mobile has been dominated by two chubby players since the app store dropped in 2008. We don't know what consumers will want given a viable alternative. App quality in general is not great and consumer complaints are often met by 'deny & subvert' style responses. In OSS, your voice (in the form of a PR) really does matter.

Why haven't the [ubuntu phone](https://ubuntu-touch.io/), copperhead, grapheneos, [cyanogenmod](https://en.wikipedia.org/wiki/CyanogenMod) (backed by microsoft) or their various cousins succeeded at scale? My guess is hardware compatibility and supply issues, bad job getting the word out, big scary diffs vs trunk, and unclear commitment to free software ideals. Purism has successfully launched 2 laptop lines and isn't just touting privacy to hear themselves blog -- they believe they've identified a market that wants a trust partner.

App availability is a concern, but (1) early adopters are willing to carry two devices and (2) if purism gets the buildsystem right, any product with an open API will have an app on this platform overnight.

Retaliation by major players is also a concern; apple and google have [colluded against a common threat before](https://www.businessinsider.com/steve-jobs-smiley-face-email-2014-3). They can use their market power to prevent major apps from launching on a third platform, or to scare their supply chain partners off from building open hardware. But it will be a while before any open platform is big enough to be a threat.

## Bottom line

I'm looking forward to the day when I can write software for mobile without (1) having to use ancient, heavy SDKs / buildsystems and (2) being treated like a criminal by the distribution platforms.
