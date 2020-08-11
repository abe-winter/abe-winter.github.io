---
layout: post
title: Mesh twitter for election week
description: Yes this means you, yes this means now
author: Abe Winter
categories: yes-now
new: true
---

1. toc
{:toc}

## Yes this means you, yes this means now

The institutions that regulate elections in the US are ancient and under attack from all sides.
This includes everything from districting to polling places to the post office.
I think we should build a decentralized, Twitter-like platform to make election experts 'uncancelable' in case of a dispute in the US elections this fall.
The rest of this article is about how,
but this intro section is about why.

First, I saw historian Timothy Snyder's [lecture about how free societies become un-free](https://www.c-span.org/video/?424912-2/timothy-snyder-discusses-on-tyranny).
He has a book about this and it's short, probably shorter than the talk.
Snyder says, again and again throughout, sometimes out loud, sometimes to himself as a reminder, "Yes this means you. Yes this means now."

The line stuck with me.

Second, I titled this 'election week' rather than 'election night' because I finally read the [Transition Integrity Project report](https://www.bostonglobe.com/2020/08/03/nation/transition-integrity-projects-full-report/).
The paper is about a tabletop simulation they ran with a group of experts to game out the season of misinformation that we'll be in in November.
One of the conclusions is that because of a larger-than-normal amount of mail-in voting, the vote may not be decided in one night.
There may be a lot of uncertainty.

And third, Belarus used police violence against protestors and opposition candidates after a disputed election this week.
The weird thing about it for me is I'm not thinking 'this wouldn't happen in America', but rather 'this looks a lot like Portland'.

FWIW, here's what our state dept [wrote about Belarus](https://www.state.gov/presidential-elections-in-belarus/):

> detentions of peaceful protesters and journalists marred the process

Yup.

In Belarus, the protesters are using out-of-band or mesh networking apps to stay in touch as the state blocks access to social media ([source tweet](https://twitter.com/franakviacorka/status/1292840766369390595)).

![tweet about mesh services used by belarusian protesters]({{ "/assets/belarus-mesh.png" | absolute_url }})

This article is about whether and how to build similar networks here.
In the case of a disputed election, we may need them -- not even to organize protests, but for finding a palatable collective truth.

## Which mesh

I don't have the technical depth to answer this, but can at least raise some broad questions.

**Does it need to survive an internet outage?**
It seems like in Belarus this week, the outages have been site-specific rather than the internet going down entirely.
If we expect decentralized social apps to continue working, mesh networking may be overkill.
Example: BitTorrent runs over the internet but uses ad-hoc discovery and network toplogy.

**Should it run on nonstandard hardware?**
This is a major tradeoff.
As I understand the space, the mesh network tools with longer range use the wifi chip rather than bluetooth.
But also, they don't run on stock iPhones or Android devices.
Asking people to flash their phones is impossible for Apple hardware, and probably a non-standard for Android users.

There are hardware options like GoTenna and random single-board computers with big antennas,
but is there enough of a stock of these?
And I think some of them only have proprietary messaging protocols, they can't run arbitrary traffic.

Another option is to collect all of people's old linksys routers and flash those;
it's a reasonable guess that some % of households has one or more spare wifi boxes.
I suspect wifi routers are the most commonly available flashable wifi hardware.

## Sneakernet and neighbors

My friends just moved to the suburbs and, as young parents on a block of young parents, the community formation is almost automatic.
They have a shared chat thread for everyone on the block and organize things like over-the-fence meetups and social distance porch drinks.
My point here is that community formation leads to norm formation, and if any kind of shit goes down, the people on this block will be listening to each other for information and interpretation.

One of the 'things to do' in the Tim Snyder talk was to shake hands and make eye contact.
It's scary that one of these things is discouraged or unsafe now,
and the other is hard to do with only half your face visible.

I suspect the IRL isolation caused by lockdown has degraded neighbor-nets in some places,
and the lockdown-driven migration probably hasn't helped.
(Though my newly-suburban friends migrated post-covid, so I may be wrong here).

Neighbor nets are especially important for an election-week mesh because:

- Mesh networks rely on geography, so you need to have your neighbors on board 
- In the case of jamming or other interference, sneakernet can replace a clogged digital network
- Digital information is in some ways less trustworthy than face to face discussion; if the digital information starts to seem weird, people can get together and talk
- In a 'take to the streets' outcome, having geographical concentrations of people who are aligned on the facts and on electoral values can suppress violence

As this sort of network booted up, I imagine early adopters or node operators organizing sidewalk meet-and-greets to get a sense of each other.

## Topologies of trust

In a provocatively titled [Twitter George Soros and Porn](https://themargins.substack.com/p/twitter-george-soros-and-porn) newsletter from this week, this author's well-read but very offline friends turned to Twitter for covid news because traditional media wasn't 'fast' enough.

> he didn't feel like he was getting reliable information from traditional media and had downloaded Twitter to try to find better information 🤯🤢. COVID is the most fast-moving, earth-shattering, difficult-to-comprehend thing imaginable and he logged onto Twitter for the first time in his life to find information about it.

> It was frustrating when he sent me the first Alex Berenson tweet. ... Contact tracing is pointless, Sweden is doing it right ...

> He downloaded an app and assumed it worked as advertised. As Twitter proclaims on their landing page, they would help you “See what’s happening in the world right now”. ... he shaped his idea of reality ... with no real background on the underlying dynamics and mechanics of the app.

Confession time:
I joined twitter this March to get faster information about covid.
And now, 5 months later, I 1000% agree with this newsletter -- it takes a while to understand how to read an account or community.

And also that Twitter isn't vetted.
Nobody claims that it is, but we all have experiences where we realize exactly what that means.
I exited a futures position in March based on a tweet from a Politico journalist that was negative for stocks,
and the author followed up 5 minutes later with something like typo, sorry, left out the 'not'.

'Election-week mesh twitter' won't be immune to these problems.
But it has some advantages.
As a 'single-issue' social network, we can reimagine the blue checkmark and the approach to fact-checking.

Most of the users of this network won't be publishing.
The ones who are will be carefully selected experts who will declare their area of expertise up-front.
That means, at minimum, there's reputation risk for a cyber-security expert who is wrong in a big way.

It also means that there may be only 10 cyber-security experts on the thing, and they'll all be weighing in on the same question.
Readers can build their personal conclusions based on the spread.
Also, they can check each other if they publish information before all the facts are available.

The goal of trust in general is more rapid consensus, at the cost of not being able to verify every claim or interpretation yourself.
Putting together groups of experts can give you a middle ground where you pick from a menu of expert opinions.

## Truth-finding vs organizing for action

Why orient this towards finding a consistent view of the truth rather than enabling action in case of an unfair election?

Two reasons:

First, you can't, or at least shouldn't, make the decision to protest unless you have the truth.
A fair election that achieves an undesired outcome is the best we can ask for, and the best we can demand.

Second, truth is, or at least should be, something that all sides want in an American election dispute.
Building a resilient, high-tech, grass-roots national institution that achieves this should be a common goal.
If it isn't, we might as well start the civil war today.

## Legal protections for mesh networks

The TIP paper points out that whoever is currently behind the desk can use the apparatus of power to warp the election outcome.
Here are some ways that could happen and some other ways to protect against this kind of interference.

If the network runs over normal internet, ISPs can be compelled to block it, or to shut down entirely.
Power companies can be compelled to shut down power, although I think that would backfire because it would send people onto the street and force them to build local coalitions.

If the network runs on software that's in the app store, it can be taken out of the app store by exerting pressure on Apple and Google.
If it's sideloaded on Android devices, vendors can be pressured to release updates that block it, although I suspect this is harder to do;
it takes between 6 months and never to plumb security updates through the diverse Android ecosystem.

If local wifi or bluetooth is the transport, these things can be jammed, but if it's done by police or with regulated equipment, this too can be challenged in court.

There needs to be a legal armor for resilient networks to be truly resilient.
I would start with commitments of support from infrastructure companies (ISPs and OS vendors),
and then have a consortium of them seek a declaratory judgement.

A declaratory judgement is a declaration by the courts that is 'preventative' in that it allows a court to affirm the rights of the litigant.
I'm not a lawyer and my sense is that standing in declaratory judgement suits is not simple,
but no harm in trying.

## What will this take

* A network of experts and 'election first responders' who can provide a feed of factual observations and expert interpretations of what's happening
* Technology experts to select the software and hardware to run the mesh
* Legal experts to defend the network from executive action
* Grassroots organization to install and test the network in advance of November

If you're interested and qualified to do any of these things, DM me on Twitter ([@abewinter2](https://twitter.com/abewinter2)) or email me awinter.public at gmail.com, and I'll put you in touch with the others.

## Appendix: alternatives

The [National Popular Vote Interstate Compact](https://en.wikipedia.org/wiki/National_Popular_Vote_Interstate_Compact) is a group of states who have agreed to use all their electors to follow the outcome of the popular vote.
The agreement doesn't take effect until the compact includes states with a sum of 270 electoral votes, and it's not clear that it's legal.
But if you include states with pending legislation, we're basically one medium state from passing this thing.
My suspicion is that with this change in effect, the election wouldn't be close enough to be contested.

But it also means a big shift in political power to cities;
if the goal is to defuse the new American tribalism, this doesn't get us there.
It just shifts power to a different tribe.

Another option is to develop external sources of truth for the vote, like some kind of mass digital polling --
not 'how will you vote' but 'how did you vote'.
It's bad that we need this but frankly it's bad that we don't already have it.
Reliable systems have backups.

Another option is to get independent observers.
They can be UN, or just retired officials with mixed party alignment.
You'd want them in the Post Office if there are lots of mail-in ballots, in polling places.
If we have a last-minute pandemic or security lockdown, they would assess whether it's necessary.

{% include flatpixel.html %}
