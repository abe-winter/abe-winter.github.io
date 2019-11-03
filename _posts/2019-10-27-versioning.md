---
layout: post
title: Version numbers are meaningless and horrible and so is xcode
description: The upgrade treadmill is bad for all market participants except one
author: Abe Winter
noindex: true
---

1. toc
{:toc}

## I just wanted to change one line

![moving xcode to applications]({{ "/assets/xcode-moving.png" | absolute_url }})

Last week I needed to get a feature out that required a truly simple change to a mobile app. But the ios tools ecosystem is *so bad*. It took an hour to write my change, but two days of tinkering and updating before that to sanctify my laptop to the point where it's a suitable vessel for 5+ gigabytes of xcode.

My laptop is two years old. That's *not that old*.

Let's roll the tape:

* xcode 10.x had too old of a swift version; time to upgrade
* I tried installing xcode, but the app store showed me a grey button and said (elswhere) 'restart to finish installing updates', so I did
* The update turned out to be for garage band, consuming more of my dwindling disk space. Garage band rearranged spells 'and garbage'
* Fine, I'll install your long-pending mojave update. The last one of these broke the laptop for a day. I'm starting to feel uncomfortable.
* The OS update somehow wiped my mac app store token so I had to go home to get my password
* I tried installing xcode 11.x from the app store, but the mac app store install hung at seven eighths full. Just hung. Later I found out this is the mac app store's way of telling me that the OS version is incompatible
* Found out my coworkers are using xcode 10.3, so had to log into some other apple system to get at the old version. Apparently you don't need a paid developer account to get at these, just an apple ID? But why are they paywalling a free product?
* Installing xcode 10.3 popped up a clearer error -- I got the wrong mojave
* Update mojave 10.14 -> 10.14.3 I think. Each of these updates involves hours of my laptop turning into a brick with a progress bar, *and* a non-zero chance of more serious bricolage
* And there was evening, and there was morning, the second day
* xcode 10.3 is too old to deploy to the test device I stole from my work friend's desk, which is on ios 13.1, so I installed xcode 11 to see if that would be better. 
* My disk filled up around here. I couldn't store more than one version of xcode, so every version switch is requiring a 5+ GB download. The hours do not pass quickly. Docker pruning prevents me from filling up completely, but I am not having a good time of this.
* Bad news -- xcode 11 is *too new* for this codebase. There's a cocoapod that isn't ABI compatible with swift 5.1 or something. (also cocoapods, wtf? why doesn't the ios buildsystem have a native package manager? Why is this stuff hosted on github? Ever heard of a CDN?).
* **Finally, success**: copying device support files from xcode 11, then installing xcode 10.3 again, then pasting the device support in.
* I still couldn't deploy to my device though, because the ios ecosystem makes it really hard to deploy software to a device without signing certs. Deploying unsigned code to your device is for pirates.
* Then some build tool called fastlane donked up my osx keychain somehow in a way that broke my work VPN -- this fixed itself on restart but jeez, why are these build tools *so clunky*

By comparison, you can download android studio from a website, it's less than 1GB, it updates itself to the SDK it needs, and doesn't require immersing your laptop in the bath of ritual cleansing in order to get running.

Whole-version upgrades like this are big, scary, bad for consumers and bad for developers. All else being equal, upgrades are risky and bad generally. They can be expensive. And apple is the only party benefiting doing them so often, because after enough of them apple gets to sell me a new laptop.

The most important users of a platform are developers; once they replatform, even if only in their hearts, it's only a matter of time before the users follow. This is one of the ways that apple beat windows in the corporate market -- developers switched to mac because it was closer to linux, and eventually the business side followed.

## Cadence, innovation & incentives

![emptying trash]({{ "/assets/xcode-trash.png" | absolute_url }})

The reason apple doesn't prioritize compatibility over upgrade cadence is that upgrade cadence is how they make their money. They've made it their business to determine exactly how much shit people will eat and to maintain their growth are willing to switch to a hose.

Those terrible '% updated after 6 months' graphs for non-google android systems are indeed terrible, because they mean security holes, but automatic updates are a two-edged sword -- they're half about security and half about [degrading your old phone](https://www.vox.com/2017/12/22/16807056/apple-slow-iphone-batteries), especially on ios. I really like the [your change is probably not for the better](https://gist.github.com/sleepyfox/a4d311ffcdc4fd908ec97d1c245e57dc) article by a frustrated product person.

Is low developer productivity strategic for apple? No, but it's a side effect of the anti-user tricks that *are* strategic: creating strong version gates, using software updates to make hardware work badly, and using frequent updates to force people to buy new hardware.

Apple's commitment to keeping their ecosystem under control & forcing people to buy new hardware every N years is the reason this tools ecosystem sucks such a smelly egg. If they lost control of the tools, it would be easier to keep apps up to date on multiple platforms and they would lose their ability to break compatibility with old OS versions and hardware. Apple wants backwards compatibility to be harder than it should be.

Also bear in mind that whatever consumer benefit is provided by new OS versions, it's *bundled*. Bundling is the reason every cable subscriber pays for ESPN even though thtey don't all want it. If the future of apple is the future of cable, that's bad news for apple. ESPN is going to die soon because they negotiated their content at peak cable, and won't be able to pay those prices through their long, slow decline. ESPN evolved to be the king lizard and can't exist in any world where it's not.

The same thing happened with unions in detroit. They didn't understand how times had changed and contributed to bankrupting the car companies. Bad union negotiations were only one of many things that killed detroit, *but* bad incentives for the most powerful player can block innovation.

In apple's case, they need to control everything about their tools because nobody else is aligned with them. Every action is potentially threatening to their hegemony. Many authoritarian systems have this problem -- it's why the soviet union's centrally planned economy failed.

Unaligned incentives + absolute power = you have to oppose all change, because any effective change will lead to a shakeup.

## Economically speaking, maintenance is agriculture

![xcode, developer tools, apple]({{ "/assets/xcode-stuck.png" | absolute_url }})

Software is a big part of the american economy. 'Every company is a software company now' isn't far from the truth. Which means, as the line count increases, *maintainability* matters more every day. As the software supply chain grows, and applications touch more & different vendor APIs to do their work, maintainability gets more complex.

My experience is probably not extreme. What else takes 2 days in apple's world that takes an hour on 3rd-party systems? What's the economic cost of 2 days of my salary x everyone in my industry? I think apple is taking a big shit on everyone.

Software maintenance is like agriculture. When there's no way to automate it, you can get a lot of people to do it and generate a small surplus that employs specialists who diversify your economy. Over time, it becomes automated, and most people move into value-added services.

Apple's crappy tools & bad incentives are making it really hard to automate maintenance. In 1919, if you couldn't automate agriculture, you couldn't have a modern economy. I think that's true in 2019 for the parts of software engineering that a computer can do by itself.

It's not like this stuff is hard. If it doesn't work it's because someone wants it to not work, to the detriment of the rest of us. If you believe my metaphor, apple thrives by making food more expensive. And when food is expensive, nothing else gets done.

## The year of the linux phone

![paused]({{ "/assets/xcode-paused.png" | absolute_url }})

... will not be 2019. Purism is [having trouble shipping](https://jaylittle.com/post/view/2019/10/the-sad-saga-of-purism-and-the-librem-5-part-1), and the open firmware values that drew early adopters to their product don't exist for a lot of the competition.

The developer experience for building ios is the worst I've experienced in years. I know UI is supposed to be worse than backend, but this is way worse. An open source ecosystem, by providing a menu of options rather than locking down the toolchain, will be better than my xcode experience before long.

The year of the linux phone isn't 2019, but it may be 2020. The moment someone launches open hardware and a non-bananas mobile OS, a series of dominoes will fall that leads to a lot of the profit going away for the mobile platforms, and most of that profit is apple's. The moment a linux handset starts to gain traction, I'm shorting apple.

Linux will welcome python, go, C. And it will be possible to develop compact codebases that deliver usable apps. You won't have 2k line XML files to get a build to work. You'll be able to create a working app in one line, and in one file.

Installable web pages will work properly because it will be easiest to support and it's the only way to seed the functionality of the device. Linux phone vendors won't have a vested interest in closing down their APIs, at least not at first.

It's in apple's DNA to suck at this, and they won't be able to catch up.

Consumers sense that they're being shat on and they'll want to switch as soon as the platform is ready -- which isn't yet, but it's soon.

## How could this be better

![installing components ...]({{ "/assets/xcode-components.png" | absolute_url }})

### Replace version numbers with a compatibility matrix
{:.no_toc}

Today, for the most part, unless you're building against a library and relying on a type system, it's hard to automatically say if two pieces of software can interact safely.

We use version numbers as a proxy for this; a developer designs their app to work with a library or platform version, and tests it thereof. But this is expensive and difficult, and easy to get wrong when something changes. It also discourages app developers from staying up to date with libraries and platforms.

Instead of targeting a version for compatibility, I should target the specific APIs my app consumes, and the side-effect semantics I want from those APIs. Then the library can publish a matrix or manifest and I can update to any version with a compatible manifest.

Even better, if I'm targeting a semantic that turns out not to be true, I can get automatically notified of this when the vendor corrects the manifest. For example, imagine some social sharing API that discovered a bug in their privacy implementation, so that the 'not publicly visible' semantic was wrong for some route. If I'm asserting that semantic, I can discover the problem in lint and get notified to upgrade.

### 3rd-party upgrades
{:.no_toc}

Upgrades are bad everywhere and allow these kinds of dark patterns, lack of accountability by vendors, lack of control by users, difficulty selecting feature vs security channels. People were very frustrated by [windows 10 forced upgrades](https://www.makeuseof.com/tag/block-aggressive-windows-10-upgrade-windows-7-8-1/).

For the typical consumer, upgrades are better than not having upgrades, because they can't manage their own security. For any player worth stealing information from, the story is more complicated. When the Department of Interior bought chinese drones, they considered [automatic updates to be a threat vector](https://abe-winter.github.io/dieselgate/2019/07/20/djigate.html).

I think there's room in the market for a 3rd-party update manager -- an industry-standard user interface that allows users to view and control what updates they get, and which can punish vendors who try to slip in new features or privacy threats on the security channel.

This doesn't just add value for consumers. Small shops that don't want to manage their own update infrastructure could use this; they currently get it from app stores, but app stores are tied to platforms are pose a competition risk.

The only players that are harmed by 3rd-party upgrades are platform vendors, and only because they're been using automatic updates as a stick to do things that got Bill Gates in trouble with the DOJ in the 90s.

{% include flatpixel.html tag="versioning" %}
