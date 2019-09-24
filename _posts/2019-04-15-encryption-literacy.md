---
layout: post
title: Encryption literacy is coming (I hope)
author: Abe Winter
description: It gets better
date: 2019-04-15
categories: scifi
noindex: true
---

I just listened to a [Jim Comey interview](https://www.lawfareblog.com/lawfare-podcast-bonus-edition-james-comey-verify-2019) where he talks about how platforms are going to cooperate with government to execute warrants and it serves the needs of society to follow the middle way here. Do it for the children. (I'm not being snide, I'm summarizing the argument he made).

Counterpoint: now that people know about github, you can't place limits on individuals' use of encryption without shredding freedom of speech. You have to reclassify math as a weapon = you have to wield the 2nd amendment to erode the 4th by defanging the 1st.

Remember when people were printing the DVD Jon DeCSS algo on t-shirts?

We're going to get to a point soon (ish) where people manage their own private keys. Good crypto hygiene will be a basic life skill like charging your phone or brushing your teeth.

And a cryptography-literate population will look at state backdoors and limited key lengths the same way we look at cigarettes and twinkies -- moderately dangerous to the user and anyone in their vicinity.

1. toc
{:toc}

## Where are we now

People and companies are using password managers, but they're often remotely managed (1password, lastpass, managed MFA). I guess they do security audits after a breach the same as ashley madison, but you really have no idea what they're doing with your stuff.

It's probably better than using the same password everywhere, but still not great.

Our recovery pathways (email and SMS) are exploitable and/or out of our control.

If you administer your own fido or yubikey, you may not be doing the other stuff you should (server-side HSM, physical security). I don't know anybody who self-hosts backups in a safe way, and I wouldn't want to manage an important private key without good backups.

It hasn't been that long since linkedin did poor man's oauth to scrape your contacts by prompting for your actual email password. Facebook was caught doing this this year.

Lots of programs prompt for a root password on install. I don't know anyone who runs software in a VM unless their job is analyzing naughty executables.

## Where might we be in 5 years

Imagine a world where 30% of consumers are capable and comfortable managing a strong private key with **no password recovery**. We'll own specialized hardware that stores physically secure backups.

This group will have zero tolerance for companies who aren't as educated and serious about security. We won't use public records data as passwords (SSNs, birthday, first pet's blood type).

We won't buy anything that has default credentials.

In 2019 we live in a password-locked world. A PKI world will be fundamentally different:

* PKI is peer to peer -- instead of a security models where sites verify me but I have to trust the weakest CA on the list, I can verify the counterparty in every transaction. My interaction with my bank will b e safer -- so will my email from grandma.
* Snooping is over. Consumers get zero benefit from having someone read their emails. Gmail autorespond is a hot carl and it always will be. (Think forward to the day they put ads over your signature). Consumers tolerate this now but nobody will actively CC gmail in a PKI world.
* Consumers used to PKI will view centralized systems as fundamentally insecure and counter to security best practices

More connected doesn't have to mean more centralized. It has so far but that can change.

## It gets better

Will we get shiv'd in the alleyways for our yubikeys? Yes probably. In most other ways, a world with crypto-literate consumers will be better.

The snowden stuff and the revolving door at the trump white house notwithstanding, the third biggest political story of the decade is IMO cambridge analytica. Experts have known about this risk for a decade but the CA scandal kicked consumers awake.

The fourth should be a cyber breach -- pick any.

If you lived in a non-russian eastern european country, you'd be in a tizzy about cyber risk. I'm talking about nation states shutting off each other's utilities (not that russia & ukraine aren't shutting off power and water conventionally as well). Forty years ago this would be tanks rolling in, now it's silent & deadly and if you respond with conventional arms you're overreacting.

For anyone to be secure everyone has to be secure. Security is a weakest link problem.

If you're already crypto-literate, the world has felt surreal for a while, in the way that politically aware liberals have felt since 2016 ('how could anybody want to live like this'). Websites and electronics feel as safe as a carbon monoxide baby blanket but nobody cares.

Don't burn out -- consumers will start to care. People have to get that this is a public safety issue.

{% include flatpixel.html tag="encryption-literacy" %}
