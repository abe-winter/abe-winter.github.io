---
layout: post
title: Stripe formed an LLC faster than my bank could execute a wire transfer
description: Big banks lack the DNA to build self-serve
author: Abe Winter
new: true
---

> Catastrophe is always just around the corner[^complex]

[^complex]: [How Complex Systems Fail](https://web.mit.edu/2.75/resources/random/How%20Complex%20Systems%20Fail.pdf)

I made two major financial moves in the last 4 weeks:

**Move 1**: I formed an LLC using Stripe's automation. Excluding waiting for the EIN, the process took two or three days. There were a few recoverable bugs and zero large surprises. I talked to zero people on the phone. There's a pleasing flowchart that tracks your progress.

**Move 2**: Naively trying to fund a new brokerage account from my checking account. This triggered a chain reaction of fraud alerts and errors that spread like a tropical fever from my checking account to my credit card to various things attached to said card, including stuff I need for my business.

If Stripe's values are self-serve, transparency, and good docs, the banks' values are a syrupy blend of opaque rules, utter deafness to my time value, and hold music.

After days, I finally reached an agent who decided that this was an outgoing transfer rather than incoming, so there was no reason for my account to be locked. And so they unlocked my account.

Easy, right?

Interacting with stripe and the old banks simultaneously made the difference here really evident. I think the root cultural cause is an aversion to self-serve flows. Legacy financial institutions are built on call centers and branches, two things consumers have *always hated*, and can't quit them.

* toc
{:toc}

## Legacy finance has no self-serve DNA

> Human operators have dual roles, as producers & as defenders against failure[^complex]

I had a lot of time to stew while I was listening to fuzzy hold music. (Why is the audio quality so bad! At one point citi conferenced me through their system to an operator for my brokerage, and the third party was clearer than the citi agent! Ugh).

One of my on-hold activities was to read about citi's executive leadership team. There's nothing resembling the CTO or head of product at a real tech company. Their CEO for global consumer banking came up through commercial banking. The one tech person is described as a 'head of enterprise infrastructure', doesn't have a C title, and came out of their institutional clients group.

This is a room full of people who are used to selling products that are too big to fail i.e. can afford to mostly suck. Every interaction I had with citi this weekend sucked, and I suspect this is true for every person or business unfortunate enough to do business with them.

This wide gap between stripe-quality customer service and the war crime version practiced by citi would, in any industry other than healthcare or banking, cause citi to rapidly get left in the dust.

There must be many others like me. If you sum up the hours of wasted life, inept banks are committing mass murder. Better self-serve really matters. I'll be undwinding this crisis for weeks.

## Transparency and exceptional status

Both citi and chase dropped the ball on communication once shit + fan began to intersect.

Citi's website claimed that the initial bad transfer had succeeded (note: it hadn't). The web view of the account didn't show any errors or warnings.

My chase credit card was slightly weirder, with two attempted bill pay transactions showing as completed, and my balance under my limit, but available credit varying between 0 and $150 as I checked back.

Neither account signaled any kind of error status. Think about this. Something is wrong and not only can they not tell me what without hours of phone time, they can't even tell me *that there's a problem*.

In the system that the call center agents had access to, something was wrong but nobody knew quite what. The chase operators told me a few times that 'something is weird about these payments' but they couldn't tell me what. WTF.

'Banking isn't exactly real-time', explained a chase agent this evening. She said it to justify why in order to pay my card now I have to go to a chase branch, hand someone a physical check, wait for the charge to land in my checking account, then call chase, who will then call citi, likely while I hold the line with bated breath.

## Phone trees & password roullette

In part because I deeply despise my cell phone and therefore SMS 2FA, the yubikey is the possession that gives me the most delight. I savor the click when I plug it in. I take it out and look at it sometimes, tipping the gold USB contacts towards the light, muttering about how it was a birthday present. One day someone will win it from me in a riddle contest.

Neither of the banks I've been dealing with support FIDO / U2F. Not that it would matter because to get anything done, you have to call them.

The pieces of information that you have to give to identify yourself vary from call to call and they're all 'username / password' things -- like a credit card number or CVC is something that you give to strangers but somehow is also considered to be a password. One time they asked me to 'confirm my phone number for verification purposes'. WTF! A phone number isn't a password. An SSN isn't a password, especially not the last 4 digits which are used by *every company* to identify me.

Also the clearest google result for the random texas number they called from is [this tweet](https://twitter.com/jstackhouse/status/652132359286882305):

![tweet about phish-like citi source #](/assets/citi-fraud-tweet.png)

My real point is that better self-serve flows allow a lot of this to go away.

Also citi sent me an unencrypted email. WTF.

## Y kant citi hire

> Change introduces new forms of failure.[^complex]

It's 2020 now. The new millennium has come of age. The talent for doing usable web 2.0 isn't cheap but it's affordable. But they don't want to work at a bank. I worked at a bank in 2012. I quit after 2 weeks when I discovered how much it sucked. They were so dysfunctional they threatened to sue to keep me (wtf). Months later, Sandy closed our office and the team kind of dissolved.

If citi had access to 40 devs and 10 senior PMs from stripe, could they be better? If they bought stripe, could they be better? I doubt it. I think citi has a combination of legitimate legacy processes, people who are incentivized to lie about legacy processes to maintain their political power, and stale rules that nobody remembers the reason for. This combo is toxic to real producers.

I've met star managers who can toe the risk / reward line of refactoring legacy stuff. I've never technically been inside citi, but I got a pretty good map of their bowels from being shat on. I've deduced via colonoscopy that the leadership at citi would mob that star and drive them to failure. Their political survival depends on it.

Their survival as a company, however, may depend on allowing such a person to succeed. It will be interesting to see how dinosaur organizational cultures like citi evolve as actual tech cos begin to steal their lunch money.

Visa the credit card company apparently bought banking oauth provider Plaid while I was writing this. Blockbuster had a chance to buy netflix when it was just a DVD mailer, but BB never would have let it become the mass producer of shitty marvel spinoffs. Somebody this will reverse -- fintechs will buy legacy banks for pennies on the dollar. In a few years, a bank will basically be a taxi medallion -- a bundle of dissatisfied customers on their way out + the valuable regulatory right to operate as a bank.

Want to buy a medallion?

## Footnotes
{:.no_toc}

{% include flatpixel.html tag="self-serve" %}
