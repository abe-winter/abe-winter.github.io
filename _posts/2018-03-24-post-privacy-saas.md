---
layout: post
title: Blueprint for post-post-privacy saas
description: What I want from my hosts
author: Abe Winter
date: 2018-03-24
noindex: true
---

<u>Post-privacy</u> saas is what we have now. SaaS and cloud companies in 2018 disclose so much user data to third parties.

They give away the data not because they're evil, but because:
1. it lets them improve their products (which customers seem to want), and
1. customers *don't* seem to want privacy.

<u>Post-post-privacy</u> is the era I hope we're entering, a utopian time when legislative overreach and commercial data sharing are so egregious that every company will start to care about cybersecurity and even grandma and grandpa are dumping FB.

If I were a company shopping for cloud services in the current climate, here's what I'd want from my vendor:

1. toc
{:toc}

# Do business customers even need more security

[Wikipedia's list of data breaches](https://en.wikipedia.org/wiki/List_of_data_breaches) is likely not comprehensive, but the bulk of these are sleazy consumer dinosaurs like [ashley madison](https://en.wikipedia.org/wiki/Ashley_Madison_data_breach) and [equifax](https://en.wikipedia.org/wiki/Equifax).

My uninformed guess is that because some portion of SaaS customers force a security checklist on the vendor, SaaS providers are generally more secure than consumer companies.

Despite the lack of high-profile breaches, here are reasons SaaS customers will get more hawkish about security anyway:

* More aggressive nation-state adversaries (both espionage and police / legislative)
* A breach is already a big reputational hit. After the last few years, customers (both consumers & business) are going make a habit of dropping their vendors after a breach, no questions asked
* Legislators and executive seeking to punish privacy breaches (in Europe, for example). And the law, as it should, is starting to punish companies that get leak customer data (for example [Equifax small claims](https://blog.legalist.com/i-won-8-000-from-equifax-in-small-claims-court-heres-how-you-can-too-f0ce6925c079))

# BYOB (box)

Cloud has always had a convenience vs security tradeoff, but here's a compromise:

- SaaS should support third party hardware so the customers with the most aggressive requirements can drive the state of the art
- Cheap multitenancy can be the default but shouldn't be the only option

The unit of BYO might be cloud rather than box (see gitlab links below).

Unbundling of hosting from software may be a good thing for customers AND for small SaaS startups. It lets the SaaS vendor focus on software rather than ops, and it lets the customer throw as much hardware as they need at the software to get good performance.

# External KMS and RBAC

I'm in a minority here but it's *insane* to call it encryption at rest if the cloud host controls the keys.

There's a guy in philadelphia [stuck in solitary because he has an encrypted porno collection](https://arstechnica.com/tech-policy/2017/03/man-jailed-indefinitely-for-refusing-to-decrypt-hard-drives-loses-appeal/) that he showed to the feds and now won't decrypt. Not condoning his hobbies, but whatever government body is leading the charge here can't decrypt the drive. Compare this vs the new iphone which you can [crack in 30 seconds](https://blog.malwarebytes.com/security-world/2018/03/graykey-iphone-unlocker-poses-serious-security-concerns/). Having control over your keys is a huge advantage.

On the RBAC side, it's about integration sanity. OAuth is a questionable choice for consumers because it can lead to accidental grants by the user. For companies that can control the grant with a central policy, it's a no brainer. Charging extra for SAML or what have you is a completely sane way to monetize your freemium service.

# Backups

Backups must be external. It's insane that we don't have a standard third-party backup protocol for cloud.

Externally hosted backups benefit SaaS buyers worried about data lock-in. They also give some protection against malware by allowing the customer to tweak backup SLAs.

# Monitoring vs logging

We shouldn't ask SaaS operators to make do without monitoring except for SaaS clients that have the highest security needs.

*Logging* is privacy invasive and should stay in the customer's hands. Monitoring, on the other hand, is inherently aggregated and probably safe (with some oversight) to share.

Tracebacks (a la sentry / rollbar) fall somewhere in between and are probably okay as long as they don't ship local variables.

# Release notes / OSS

Automatic updates are a two-edged sword. They can fix bugs and introduce them. They can add features and subtract / mutate them. You're definitely insecure without them.

When the FBI was trying to crack the San Bernardino iphone people talked a lot about secure enclave. But as long as aapl can push updates at will, it's not a secure device.

Here's a compromise: let's have OSS services AND provide strong contractual protections around the release notes to reduce the cost of auditing updates.

Release notes should be required to disclose:

1. any major features and changes in the update (yes that's vague and will need to be interpreted by the courts)
1. changes in what data leaves the system, phone home features, and stats reporting
1. changes in the roles, access and permission features

Documentation must disclose data shipping & remote access, and provide penalties if the vendor misrepresents.

The goal here is to:

* make it hard to install a pen register or backdoor without the client's knowledge
* make it cheap / easy to audit changes

The public sector and big corporations are already getting access to source code when they buy. They're using the code to protect themselves as well as to mine for zero days. We aren't many high-profile breaches away from the day when small companies ask for source.

# Who's doing this now?

[Gitlab's cloud-native plan](https://docs.gitlab.com/ee/install/kubernetes/#cloud-native-gitlab-chart) is the best idea I've seen for installing complex server software on customer-managed hardware. Github has a self-host option but it gives me 'if you have to ask you can't afford it' vibes.

In the consumer space, [sandstorm](https://sandstorm.io/) and [remotestorage](remotestorage.io) are early players but not sure if either went anywhere.

The real point is that most SaaS providers are willing to provide non-multitenant hosting OR host on your hardware if you pay them enough. We should come up with some common asks so that this is the common case and available to smaller customers.

{% include flatpixel.html tag="post-privacy-saas" %}
