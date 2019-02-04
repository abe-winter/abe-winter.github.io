---
layout: post
title: Platforms, identity, and the future of due process
description: The whole proceeding bears upon its face the most diabolical jesuitism that has ever cursed the world
author: Abe Winter
date: 2019-02-04
---

<style>
blockquote {
  font-style: normal;
  letter-spacing: normal;
}
</style>

I got kicked off of facebook and I don't know why.

We have the concept of due process from the 1354 restatement of the Magna Carta. It's interesting that it only appeared in the restatement -- their rights were useless without structures for exercising them.

Due process is the secret ingredient for fair systems. Without it, nobody should submit themselves to institutional power. *But* internet platforms that began as toys have lately insinuated themselves into different daily transactions, like purchases, communication and travel. Transactions made through platforms generally afford one or both parties fewer due process rights than they'd get in a traditional market.

Why is due process relevant to the web? When I lost FB, I lost access to services that only accept facebook logins. And it's not clear who's accountable -- I can't pay FB to reopen the account, I can't compel them to give me an explanation, and it's unclear if the external services are responsible for ensuring that I can log in to them.

Platforms, in order to remain sticky and survive, have to be essential, which means incorporating all our daily transactions into themselves. Having a FB account may become a requirement for banking, getting on a plane, crossing borders -- you get the picture.

This is scary because there's no Magna Carta for platforms.

1. toc
{:toc}

## Micro- and meta-transactions

In theory platforms are an economic good because they reduce transaction costs. I buy more on amazon because of 1-click, I take more lyfts because it's hard to hail a cab, people tweet because it gets the word out.

(By 'platform' I'm including big social platforms like FB / twitter and market providers like uber / seamless).

Platforms reduce transaction costs in several ways:

1. 👍 Automating communication (uber & seamless both know where to find you, FB sends your photos to your friends)
1. 👍 Providing proof of identity & kicking bad actors = trust
1. 👍 Standardizing the agreement & terms (you don't have to create a new account a read a bunch of terms every time you place an order)

But these are two-edged swords:

1. ❌ Automatic communication means you have limited approval or control of data sharing
1. ❌ Kicking bad actors means the platform gets to define 'bad', and enforcement is often a blunt instrument. Requiring identity means no anonymity.
1. ❌ Standardized micro-transactions means they're all governed by one meta-transaction, the clickwrap from your signup. I suspect this concentrates negotiating power in the platform provider over the user. Furthermore, as more consumer contracts waive class action and mandate arbitration, more transactions will be happening that can't get to the legal system.

Convenience has come at the cost of negotiating power and fair arbitration. If [market networks are what's next](https://www.nfx.com/post/10-years-about-market-networks), arbitration is the missing piece that can interrupt this trend. Technology has driven down the margins on executing cookie-cutter transactions but not on negotiating their details or arbitrating bad outcomes.

## Identity is the linchpin of platforms

I have a Ukrainian friend who is from the Donbass and when the Russians invaded, all their institutional stuff was in limbo. Immigration paperwork, banking, housing -- there are a zillion institutional interactions that require proof of identity and when your birth certificate is under a pile of rubble, that gets pretty tense.

There's a reason people [pay up for a second passport](https://www.businessinsider.com/countries-where-you-can-buy-citizenship-residency-or-passport-2018-9).

I got hit on the head by a surfboard and couldn't remember my laptop password for a few hours and even that was scary. For web companies, password reset is a major security question and one reason to prefer oauth logins.

For platforms, identity is a primary function that they need to be good at. It enables them to provide trust to their market participants. For platforms that don't operate markets, identity lets them subsidize services by selling your clickstream. This is why facebook is so serious about their real name policy. It's probably the reason google+ outed trans people.

The UN considers national identity a human right. I wouldn't go that far because birth certificate = biometric database and nobody wants that jazz, but this is an important issue.

OAuth (login with FB / google) is convenient, reduces the effort of creating an account, and reduces the cost of running an app because you get high confidence that your users are real people. It also means that losing your facebook account, an event with no process guarantees, can terminate your access to a bunch of third parties who have no clear obligation to restore access. This should terrify you.

## Reputation & repudiation

The obvious application of identity for online marketplaces is for reputation -- summarizing a user's transaction history (what's your uber rating?), and kicking users who don't meet the bar. Regulating markets lets strangers trust each other.

The Fair Credit Reporting Act was passed in the 1970 at the dawn of computerized tracking of individual transactions, and basically encodes the immediate concerns one should have about automatic reputation systems:

* Data vendors are liable for inaccuracy and need to have a dispute process
* Consumers are entitled to know when & how their data is used against them
* Some controls & transparency around who can use the data and how; prior permission in some cases

These legal obligations don't exist for facebook (they sort of do in Europe under the GDPR). Most web platforms aren't subject to FCRA. Some platforms provide some of these protections but inconsistently and without 3rd party review.

Imagine if personalization vendors were required to show you the provenance of every ad view, all the different companies through which the information changed hands. I think even the jaded web user of 2019 would yack.

I read the Atlantic article about [credit reporting in the 19th century](https://www.theatlantic.com/technology/archive/2016/04/mass-surveillance-was-invented-by-credit-bureaus/479226/). Aside from the computers, this isn't a new problem. It quotes an 1851 source on contemporary credit bureaus:

> were it put in practice by any other than the selfish and insolent class who in reality govern and rule this age ... it would bring disgrace and incurable odium upon those who indulged in it. But now it is only regarded as evidence of the shrewdness and thoroughness of the commercial community, and no possible means of escaping it exist.

## Lulu's christmas present

Remember Lulu, the app that let women rate men? They got shut down, not for being a 'platform for slander' (says forbes) but for screwing with FB's data mill.

I watched [an interview with Alexandra Chong](https://www.youtube.com/watch?v=iuOurxcPUpM), the founder. Juicy excerpts:

> We launched the product, we built on top of facebook as an MVP, it was a way on which on our users could authenticate **but it was the only way**

> Then something happened -- a realization that we had real **platform dependence** with our partners and the dependence was something we could not control

> You can abide by all the **policies and rules** that platforms give you to build on with them, there are some things that can change, and lulu had that realization at the end of 2013

Lulu got into an arms race. Men were creating 100s of thousands of sophisticated fake accounts to see their ratings, and Lulu mined friend-network connections like what cambridge analytica captured:

> One part of the problem -- when guys couldn't get in by changing their genders -- because we became really smart. A girl would join, we'd take all her male friends, we'd tag them as male.

> We were getting smarter and smarter. ... we didn't know it would eventually hurt us. It hurt us because it hurt our partner. facebook relies on these authentic profiles for its relationships with advertisers & for platform developers, to have this completely obscure happening at scale, it became a problem.

> On christmas eve of 2013 I got a phone call, and it was a request to remove ourselves from the store in Brazil. and we did.

Lulu was a ticking legal time bomb and needed to die, but slander claims didn't kill it. The proximate cause of death was relying on FB for identity verification. Lulu was the perfect customer to one of the core things FB claims to provide -- verified identities. And somehow it didn't work.

Was there a contract between lulu & facebook? My guess is it was a standard API integrator contract. As far as I know, FB doesn't have business accounts -- businesses are backed by personal accounts. I doubt Lulu was paying facebook. Absent consideration, it's really unclear whether there was an enforceable contract here.

Platforms != vendors. Ecosystems != contracts.

## Erosion & leakage

Ever read the terms of service when you create an account? I read all of them. They're horrible. Expect to waive every right a contract of adhesion is allowed to waive.

The news isn't all bad. A [2012 case on zappo's terms of service](https://en.wikipedia.org/wiki/In_re_Zappos.com,_Inc.,_Customer_Data_Security_Breach_Litigation) ruled that the arbitration clause of the contract was void because:
* The contract was 'browsewrap', not 'clickwrap'
* The statute & case law around arbitration require a determination that the parties formed a contract, preventing zappo's from dismissing the case
* The terms granted zappo's the right to change them 'at any time'. The court ruled that meant zappo's wasn't giving any consideration, rendering the contract 'illusory' (good word)
* The link to the terms was on the 3rd or 4th page of the homepage when printed out (who's living in a paperless society? not the judiciary)

But that's zappo's which is, yes, a website but basically just a shoe store. When you send them money they have to send you shoes. The law is so focused on protecting market participants that a contract can't easily change that.

Traditional protections don't apply as well with platforms. For market platforms like uber, uber *is the market* -- they're not a market participant. The model for regulating it is going to look less like the Uniform Code of Commerce and more like FINRA. (Though uber is in a world of legal hurt for reasons unrelated to platforms and due process).

For social platforms like FB, it's not clear what voiding the terms would do for consumers; the only thing FB has of mine is my data and the law doesn't know how to value that. And while the contract remains in force, it's completely vague about the platform's sharing features and what happens if they're misrepresented.

Features affect the user's rights much more than contracts, and the features aren't written down anywhere.

facebook has their foot in the door -- they have your data and they're gradually normalizing leaking it. I was shocked when people started doing google searches from logged in google accounts. I was shocked when google auto-signed-in gmail to chrome browsers. Platforms with an identity component have to continually erode your privacy in order to survive as online ad margins go down.

Has an individual's click history and social graph ever been the consideration in a contract? Maybe when [AT&T was discounting broadband if you allowed deep packet inspection](https://arstechnica.com/information-technology/2016/09/att-to-end-targeted-ads-program-give-all-users-lowest-available-price/) (the [TOS on archive.org](https://web.archive.org/web/20160826101843/http://www.att.com/legal/terms.internetAttTermsOfService.html) forwards to an [empty KB article](https://web.archive.org/web/20160826101843/http://www.att.com/InternetPreferences)). The case law isn't here yet. Until it is, a lot of traditional consumer protections are unclear for social platforms.

FB/google's model flips consumer protection on its head by appearing to give away the product. It's similar with amazon and antitrust. From the [Lina Khan law review article](https://www.yalelawjournal.org/note/amazons-antitrust-paradox):

> the current framework in antitrust -- specifically its pegging competition to "consumer welfare," defined as short-term price effects -- is unequipped to capture the architecture of market power in the modern economy

## Social credit vs incarceration

I'm interested in the forward march of social credit in china because (1) it's moving so fast, (2) the winners get enhanced access to institutions, which is an interesting economics experiment and (3) it's solving real problems (china went from using a lot of cash to omnipresent phone payments in like 4 years). That said, it's bad and terrifying. The go-to horror story is how a court revoked a lawyer's right to travel because [his apology, dated April 1, was 'insincere'](https://www.hrw.org/news/2017/12/12/chinas-chilling-social-credit-blacklist).

Reduced access to services is I guess a positive alternative to being put in jail. *But* the due process bar is way lower for this stuff. Given a choice between greater fairness and less severity I might choose fairness (depending, always, on the details).

It's not like the west doesn't have the same kind of thing. You can't drive anonymously on public roads, and in the US drivers [waive their fourth and possibly fifth](https://en.wikipedia.org/wiki/Implied_consent#Driving_while_intoxicated) amendment rights.

When you squint it's getting harder to distinguish the behavior of free governments and non-free ones. The chinese have ['several hundred thousand'](https://www.bbc.co.uk/news/resources/idt-sh/China_hidden_camps) muslims in jail in Xinjiang, but if the US no longer leads china in purchasing power parity or math scores, guess where [we beat them hands down](http://www.prisonstudies.org/highest-to-lowest/prison-population-total?field_region_taxonomy_tid=All) in both absolute numbers and per-capita?

Does the west gain anything by executing on our values rather than just paying lip service to them? If we're going to impose trade barriers, should we do it for human rights goals instead of military and economic ones? I really don't know.

## Takeaways for the web ecosystem

Everyone knows this but I'll say it again -- platform risk is the habanero flavor of vendor risk. Don't trust them too far or you'll get slimed.

Watch for the unbundling of identity from platforms and for higher-priced, secure, verified 'identity as a service'. It will suck in its own way just as bad as facebook but hey, at least it won't *be* facebook.

Look out for arbitration as a service -- third parties who are accountable to both sides of a transaction and who create some kind of anonymized public record of disputes. The courts are too slow and expensive to keep up with facebook or uber. Arbitration is equally slow, opaque and probably favors the repeat customer. Cheap, fair and effective arbitration is a key ingredient for the next chapter of electronic consumer markets.

I have my fingers crossed for the decline of purely free products. Free and freemium = really unclear contractual rights. I think consumers are getting sick of the abuse, and voting with their wallets is the only way to end it.

{% include flatpixel.html tag="due-process" %}
