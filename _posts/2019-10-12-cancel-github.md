---
layout: post
title: Good luck backdooring encryption without banning github
description: And math I guess
author: Abe Winter
new: true
---

Bill Barr [wrote a letter last week](https://www.buzzfeednews.com/article/ryanmac/bill-barr-facebook-letter-halt-encryption) begging facebook not to install end-to-end encryption. The letter doesn't say the word backdoor but FB's response does.

If you want to backdoor encryption, here are all the other things you'll have to ban:

* Github, i.e. the right to publish source code without a government audit
* running arbitrary software on a device, i.e. running any computer without monitoring software
* steganography, i.e. any technology for hiding a message
* sending any non-backdoored encrypted message over a public network
* mesh, i.e. non-centralized public networks
* the [unlicensed radio band](https://www.wi-fi.org/discover-wi-fi/unlicensed-spectrum)

The things you have to ban are fundamental to a software-based economy, and fundamental to my concept of freedom in the 21st century. [Even China hasn't banned github yet](https://www.npr.org/2019/04/10/709490855/github-has-become-a-haven-for-chinas-censored-internet-users). Ultimately encryption is math. The security apparatus that you'd need to bring to bear to *ban math* is beyond belief.

My point isn't just that this is impossible. It's that granting any government the political capital to *try* this begins with a regulatory crackdown on communications software and hardware, and there's not a lot of daylight between software and speech.

It would also require a sustained legislative assault on the court system -- multiple rounds of laws getting defeated in the courts because they violate basic protections. Any politician who wants to do this is either legally stupid, technologically stupid, or some kind of bond villain.

I'm not the [first person to write about this](https://www.schneier.com/blog/archives/2015/07/the_risks_of_ma.html) and I won't be the last.

* toc
{:toc}

## The secret keys have to be *everywhere* for this to work

in order to backdoor, you have to distribute the law enforcement secret key to every switch & router in the land.

You *can't* just use a technology to prove that the packet is encrypted without actually encrypting it. Because what if your packet contents are in turn encrypted with another key? The network switch will have to decrypt the packet and check that the contents seem benign according to some lookup table.

People are saying 'we can keep the encryption keys safe in a lockbox' but if you're going to do packet inspection then every backbone switch will need its own lockbox.

## Assumptions about centralization that won't hold true

Leaning on facebook to install a backdoor is silly. FB is adding end-to-end encryption because they expect to hemorrhage users when other networks add it. Consumers have been trained to look for SSL on their bank, they'll ask for this too. And generally, relying on criminals to use a centralized service is stupid.

It's highly likely that we'll see hobbyist wifi chips, CPUs and cell phones in the very near future, especially as linux support for most hardware becomes progressively crappier. Will it be cutting edge? *It doesn't have to be*. Cell phones have been 'good enough' since the iphone came out. My ancient Nexus 5 still boots fine.

What's true for hardware will also be true for networks. First hobbyists and then an increasing mainstream population will use mesh networks, initially in places where cell phones don't work well and gradually for day-to-day stuff.

The current regulation regime for radio [equates enforcement with manufacturer licensing](https://softwarefreedom.org/resources/2007/fcc-sdr-whitepaper.html). That works for the status quo when relatively few companies make wifi chips. It won't work when high school kids are building chips in their basement that operate in the unlicensed band.

*Even if* encryption backdoors can be rolled out with current technology (a dubious claim), we'll need to gun down a generation of basement hobbyists to keep the stranglehold on future silicon and future networks.

## Bad crimes on the dark web

Tor is used as an example of a technology that doesn't have any applications other than bad crimes. But there are other ways to investigate these crimes than backdooring encryption. If a child goes missing it gets reported. Law enforcement has done a bunch of effective dark web stings.

On the drug front: we're talking about substances some countries have decriminalized in a desperate and reasonable attempt at harm reduction. So while you can make a legal argument against mailing people drugs it's hard to make an unambiguous moral one.

On child porn: the argument that encryption makes it safer to consume this, and therefore creates a market with financial incentives, is one I believe. But the cat is out of the bag. It's *not possible* to ban any software technology among criminals. I believe claims that criminals have organized encrypted communities to commit their crimes.

But organized crime isn't a new phenomenon. This has to be a job for old fashioned police work, because I suspect anyone willing to produce or consume illegal porno is also willing to download an illegal version of tor. 'Target offender organizations' is one of the legs of the [national child exploitation prevention strategy](https://www.justice.gov/psc/file/842411/download#page=90) (2016, p81). Cops have been doing this forever. They'll make it work.

## Every government effort of this kind in the past has failed

(In the US).

* Export restrictions on encryption [were rolled back in the 90s](https://en.wikipedia.org/wiki/Export_of_cryptography_from_the_United_States) because they were no longer enforceable. Can you imagine searching some tourist's alanis morisette jewel case for a windows 95 CD?
* The [clipper chip](https://en.wikipedia.org/wiki/Clipper_chip#Backlash) met with instant negative backlash from the 90s tech community and never was rolled out
* FCC sent [mixed signals on DD-WRT](https://arstechnica.com/information-technology/2015/09/fcc-accused-of-locking-down-wi-fi-routers-but-the-truth-is-a-bit-murkier/) and then backpedaled
* Apple banned [the police tracking app HKmap.live](https://thenextweb.com/security/2019/10/10/apple-bans-app-that-warns-hong-kong-citizens-about-police-activity-again/) in hong kong but [mesh networking is gangbusters](https://www.forbes.com/sites/johnkoetsier/2019/09/02/hong-kong-protestors-using-mesh-messaging-app-china-cant-block-usage-up-3685/) and every platform *but* apple can still install HKmap.live
* The [NSA bribed RSA](https://www.reuters.com/article/us-usa-security-rsa/exclusive-secret-contract-tied-nsa-and-security-industry-pioneer-idUSBRE9BJ1C220131220) to weaken their algo. This actually worked until snowden, but it wasn't a legislative effort. Does this kind of slimy stuff = 'safe' to you?
* Senior FBI people were ["definitely not happy"](https://www.techdirt.com/articles/20180327/15444939518/fbi-officials-were-angry-that-iphone-hack-blocked-them-getting-court-to-force-apple-to-break-encryption.shtml) that they cracked the san bernardino phone before they could establish some nasty case law in court
* The [DMCA case against deCSS](https://en.wikipedia.org/wiki/Universal_City_Studios,_Inc._v._Reimerdes) prevented the dvd encryption keys from being widely spread. They were briefly banned from wikipedia but are now [posted on the page about the controversy](https://en.wikipedia.org/wiki/09_F9_11_02_9D_74_E3_5B_D8_41_56_C5_63_56_88_C0). I think these suits were successful in that they prevented FOSS decryption tech from being distributed with commercial technology, but they didn't prevent the tech from being accessible to criminals & wikipedia users.

## Backdoors keep failing because they're counter to our values

Backdooring effectively means banning encryption.

The technological changes involved to really enforce 'you can only use ours' amounts to rebuilding the entire internet backbone to be able to decrypt all packets. *And furthermore* you'd have to ban alternative networks and custom chips.

That's the technology. On the legal side, there's no way to ban the use of encryption without unwinding every statute & case protecting individuals against state power. This isn't the same as DMCA takedowns, where someone wants their content down. You'd have to ban the building blocks.

I get that top cops want to keep my kids safe but so did the [comics code authority](https://en.wikipedia.org/wiki/Comics_Code_Authority) and the [PMRC](https://en.wikipedia.org/wiki/Parental_Advisory). If you haven't seen Dee Snider [dis Tipper Gore in congress](https://youtu.be/S0Vyr1TylTE?t=1062) you haven't lived. "Ms Gore was looking for sadomasochism and bondage and she found it."

[Frank Zappa's take on music ratings](https://youtu.be/hgAF8Vu8G0w?t=249) also fits. "The PMRC proposal is an ill-considered piece of nonsense which fails to deliver any real benefits to children, infringes the civil liberties of people who are not children, and promises to keep the courts busy for years."

{% include flatpixel.html tag="cancel-github" %}
