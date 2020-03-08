---
layout: post
title: Stripe can make automatic LLCs but a wire transfer from citi nearly ended me
description: Big banks lack the DNA to build self-serve
author: Abe Winter
top: true
---

I made two major financial moves in the last 4 weeks:

**Move 1**: I formed an LLC using stripe's automation. Excluding waiting for the EIN, the process took two or three days. There were a few recoverable bugs and zero large surprises. I talked to zero people on the phone. There's a pleasing flowchart that tracks your progress.

![atlas application flowchart]({{ "/assets/atlas-application.png" | absolute_url }})

**Move 2**: Naively trying to fund a new brokerage account from my checking account. This triggered a chain reaction of fraud alerts and errors that spread like a tropical fever from my checking account to my credit card to various things attached to said card, including stuff I need for my business.

If stripe's values are self-serve, transparency, and good docs, the banks' values are a syrupy blend of opaque rules, utter deafness to my time value, and hold music.

After days, I finally reached an agent who decided that this was an outgoing transfer rather than incoming, so there was no reason for my account to be locked. And so they unlocked my account.

Easy, right?

Interacting with stripe and the old banks simultaneously made the difference here really evident. I think the root cultural cause is an aversion to self-serve flows. Legacy financial institutions are built on call centers and branches, two things consumers have *always hated*, and can't quit them.

* toc
{:toc}

## Legacy finance has no self-serve DNA

I had a lot of time to stew while I was listening to fuzzy hold music. (Why is the audio quality so bad! At one point citi conferenced me through their system to an operator for my brokerage, and the third party was clearer than the citi agent! Ugh).

One of my on-hold activities was to read about citi's executive leadership team. There's nothing resembling the CTO or head of product at a real tech company. Their CEO for global consumer banking came up through commercial banking. The one tech person is described as a 'head of enterprise infrastructure', doesn't have a C title, and came out of their institutional clients group.

This is a room full of people who are used to selling products that are too big to fail i.e. can afford to mostly suck. Every interaction I had with citi this weekend sucked, and I suspect this is true for every person or business unfortunate enough to do business with them.

This wide gap between stripe-quality customer service and the war crime version practiced by citi would, in any industry other than healthcare or banking, cause citi to rapidly get left in the dust.

There must be many others like me. If you sum up the hours of wasted life, inept banks are committing mass murder. Better self-serve really matters. I'll be undwinding this crisis for weeks.

## Built for branches

One of the things I had to do to repair my situation was walk into a chase branch with a check from citi and hand deliver it. On my way over, I noticed that there were a cluster of banks at the corner: TD, citi, chase, and like one or two others, all within a one block radius in a relatively high-rent district.

I always underestimate work, but it seems to me that the annual cost of just the branches on this corner could be used to build usable self-serve flows for let's say 80% of cases where people go into a branch. I've never understood how branches can be profitable. My theory after this week is that some unknown force is sabotaging successful self-serve systems. And maybe regulatory forces prevent incumbents from succeeding (although I'll certainly be switching banks ASAP).

I worked at a place that sabotaged self-serve. The technology pieces were mostly in place but powerful leaders in the sales and integrations team were incentivized to keep things as they were. The argument was always 'of course we want it, but it won't work so it stays at the bottom of the priority list. And we won't tell any clients about it, wink.'

I suspect the branch / call center culture at banks hides a hundred dark corners where someone is essentially being paid to resist modernization. Some of these corners may even be integration points, so that startup banks won't be able to do business in the industry and will quietly fail. This is a conspiracy theory, not an observation, but it's something I believe more today than 7 days ago.

In the economic research around automation replacing labor, 'why didn't ATMs reduce the number of bank branches' is an important question. After this week, my answer to the question is that banks are determined to suck and use their market momentum to get away with it.

## Transparency is a huge hole

It wasn't just that they couldn't tell me what was wrong online. The call center agents had varying levels of visibility and understanding of the problem as well. Nobody was able to tell me in a nutshell what was happening or why.

Both citi and chase dropped the ball on communication once shit + fan began to intersect. I'm honestly on the fence between incompetence / malice / 'hard problem' to explain why they're bad at this. In theory it's easy to tell someone not even *why* their account is locked but *that* their account is locked. In theory it's easy to make balance + available credit = limit. But there are certainly a lot of integration partners and exceptional cases here.

Citi's website claimed that the initial bad transfer had succeeded (note: it hadn't). The web view of the account didn't show any errors or warnings. My chase credit card was slightly weirder, with two attempted bill pay transactions showing as completed, and my balance way under my limit, but available credit at 0.

Neither account signaled any kind of error status. Think about this. Something is wrong and not only can they not tell me what without hours of phone time, they can't even tell me *that there's a problem*.

In the call center agents' system ('give me a moment while I pull up your account details'), something was wrong but nobody knew quite what. The chase operators told me a few times that 'something is weird about these payments' but couldn't be more specific. WTF.

'Banking isn't exactly real-time', explained a chase agent last night. She said it to justify why in order to pay my card now I have to go to a chase branch, hand someone a physical check, wait for the charge to land in my checking account, then call chase, who will then call citi, likely while I hold the line with bated breath.

Today, depositing my physical check at a physical branch, I asked how long it would take to appear in my account. 'Right away,' they said, 'because I put in your credit card number myself.' I have no idea who's right.

To gaslight me, chase has started backdating cancelation notices for the initial payments. This payment wasn't marked returned until a week after the date in the screenshot. Feast your eyes:

![backdated returned payment]({{ "/assets/backdated-payment.png" | absolute_url }})

Maybe this is chase's attempt to build a [bitemporal database](https://en.wikipedia.org/wiki/Bitemporal_database#Bitemporal_Modelling) but more likely this is them covering their butt at my expense so they can change history if I dispute anything.

Compare this experience to the stripe flowchart at the top of this article. Stripe doesn't want me to have to call in to do business with them. And so I haven't.

Here's the truly insane part -- during the N days that I couldn't use my bank account and citi was poisoning my credit card, an ACH transfer to the same brokerage account succeeded! (Note: ACH != wire transfer, apparently). Whatever fraud alert triggered a code blue here (1) wasn't triggered by a larger transfer via a different channel and (2) the lockdown didn't prevent said transfer.

## Replacing robots with people

I have unusually bad luck with institutional interactions, but if you've paid for anything in the last 50 years, you probably share my experience of transitioning from happy path (navigating automatic or reliable systems) to sad path (navigating institutional rules, at the mercy of a human agent).

I won't pretend the sad path is easy to fix -- after all, something has already gone wrong when you're calling in. But banking is sad path by design.

I suspect there's a strategic instinct here that banks can make their processes more flexible by having lots of people. But most of them aren't able to help for most problems. This isn't a dis, it's just saying that the training overhead of keeping everyone up-to-date on a complex system is too high.

I'm not proposing replacing people with robots -- I'm proposing taking a system where call center agents are basically an intermediary between their software and me, and letting me have access to the system directly. The banks have replaced robots with humans. That's not a business strategy that makes sense when 99% of your customers have a smartphone.

I think that the health insurance industry benefits from opaque information and rules, and is able to reject and delay payments by having complex reimbursement standards that they can interpret at will. I'm not sure what the banks get from behaving this way.

## Phone trees & password roulette

In part because I deeply despise my cell phone and therefore SMS 2FA, the yubikey is the possession that gives me the most delight. I savor the click when I plug it in. I take it out and look at it sometimes, tipping the gold USB contacts towards the light, muttering about how it was a birthday present. One day someone will win it from me in a riddle contest.

Neither of the banks I've been dealing with support FIDO / U2F. Not that it would matter because to get anything done, you have to call them.

The pieces of information that you have to give to identify yourself vary from call to call and they're all 'username / password' things -- like a credit card number or CVC is something that you give to strangers but somehow is also considered to be a password. One time they asked me to 'confirm my phone number for verification purposes'. WTF! A phone number isn't a password. An SSN isn't a password, especially not the last 4 digits which are used by *every company* to identify me.

Also the clearest google result for the random texas number they called from is [this tweet](https://twitter.com/jstackhouse/status/652132359286882305):

![tweet about phish-like citi source #]({{ "/assets/citi-fraud-tweet.png" | absolute_url }})

My real point is that better self-serve flows allow a lot of this to go away.

Also citi sent me an unencrypted email. WTF.

## Citi won't be able to hire

It's 2020 now. The new millennium has come of age. The talent for doing usable web 2.0 isn't cheap but it's affordable. But they don't want to work at a bank. I worked at a bank in 2012 and quit after 2 weeks when I discovered how much it sucked. They were so dysfunctional they threatened to sue to keep me (wtf). Months later, Sandy closed our office and the team dissolved.

If citi had access to 40 devs and 10 senior PMs from stripe, could they be better? If they bought stripe, could they be better? I doubt it. I think citi's problem is legitimate legacy processes, plus people who are incentivized to exaggerate the baggage of legacy processes to maintain their political power, plus stale rules that nobody remembers the reason for. This combo is toxic to real producers.

I've met star managers who can toe the risk / reward line of refactoring legacy stuff. I've never technically been inside citi, but I got a pretty good map of their bowels from being shat on. Extrapolating from politicized workplaces in my past, I suspect the leadership at citi would mob that star and drive them to failure. Their political survival depends on it.

Their survival as a company, however, may depend on allowing such a person to succeed. It will be interesting to see how dinosaur organizational cultures like citi evolve as actual tech cos begin to steal their lunch money.

## Banks and taxi medallions

Visa the credit card company apparently bought banking oauth provider Plaid while I was writing this. Blockbuster had a chance to buy netflix when it was just a DVD mailer, but BB never would have let it become the mass producer of marvel spinoffs.

Eventually this will reverse -- fintechs will buy legacy banks for pennies on the dollar. In a few years, a bank will basically be a taxi medallion: a bundle of dissatisfied customers on their way out + the valuable regulatory right to operate as a bank.

Want to buy a medallion?

{% include flatpixel.html tag="self-serve" %}
