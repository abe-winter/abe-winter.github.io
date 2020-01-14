---
layout: post
title: The future of product is fraud
description: "Preventing it, I mean"
noindex: true
author: Abe Winter
---

Teams come away from launches with 'ugh items' to avoid next time -- things that went wrong on release, weren't foreseen during design & development, and should be added to a checklist for next time. This launch -> design feedback process is one of the ways orgs get better at what they do.

Tech shops typically list scalability, debuggability, maintainability. An item that I haven't seen on these lists until recently is **fraud**. It's especially relevant for free / social products. What went wrong that we could have planned for? Fraud is often the ticket.

I don't just mean expecting fraud and beefing up your support team. I mean designing your product so it's less vulnerable to fraud, so the cost of enduring / repairing / investigating fraud is less, so fraudsters are less able to hide.

1. toc
{:toc}

## Reviews & endorsements

Amazon reviews are in theory a useful way to punish bad products and reward good ones. In practice they're highly spammable and often crazier than the people who dial in to call-in shows.

The arms race for fake reviews is so advanced now that spammy sellers have weaponized them, buying obvious fake reviews for their competitors and then turning them in.

Reviews aren't amzn's only fraud problem -- the sportswear company [Nike left amazon](https://www.bloomberg.com/news/articles/2019-11-13/nike-will-end-its-pilot-project-selling-products-on-amazon-site) this year because amazon couldn't or wouldn't stop sellers of fakes, and likely also for other reasons like data sharing and controlling their own distribution.

Search spam is not that different from review spam -- especially in the bad old days when G rankings were mostly dependent on the link graph of the web. Remember when about.com and other content farms were the top of every search? G treated this as an existential threat and solved it, but spammability was a fraud hole in the original product design for search and is still a constant war.

## Gaslighting and incentives

The incentives and market dynamics here are tricky because fraud is a quality issue that gaslights its victims. For an individual victim of fraud, it's hard to distinguish between epidemic platform fraud, a single bad actor, or just one bad transaction. If a fraudster is doing a good job of spamming their rating / reputation score, you might think this is a one-time problem and the bad actor is in fact mostly good.

Because fraudsters are pretty good at covering their tracks, platform operators have the option to play along. Platforms are incentivized to downplay complaint volume. This lets managers ignore the fraud problem on their platform and work on 'higher value feature work'. Quality, profitability, growth -- pick one and run with it.

If users aren't being directly and frequently harmed, products can survive a while with relatively high rates of fraud.

Over time, this opens the floor for competitors. Consumer startups often try to prioritize growth over product quality, suppressing arguments like 'this feature would make me use this' over 'this lets us grow'. You can forget 'good' for a while if you're an org with a tolerance for 'bad', but it comes back to bite you when someone else gets into the market.

## Paying users and paid vendors have aligned incentives

Free / growth-subsidized / ad-supported products are uniquely able to ship bad stuff because they don't have direct 'win-win' arguments in their product designs. Everything is 'how do we get the user to' rather than 'they're paying for X, give it to them and make it good'.

For paid products, quality = profitability = growth. That's the solution to the 'pick one' dynamic for growth-driven free or subsidized products.

If twitter were a paid product, botnets wouldn't be easy to build. Not only would they be more expensive to operate at 10 or 50 cents per tweet, but [KYC](https://en.wikipedia.org/wiki/Know_your_customer) becomes the credit card's problem. There are other downsides to making twitter less anonymous, but the ship has already sailed for facebook -- their real name policy has been in effect forever now.

## Reputation markets

Instagram & youtube were probably the first large influencer platforms, i.e. the first social networks to have major markets for product placement. As such they've gone through phases of reputation spam. I think the progression is something like:

1. Toy platform only interesting to cool creators
1. A first wave of consumers who trust the content arrive, and creators who were early adopters have a follower advantage that persists
1. For a while there's a real market for quality as the platform starts monetizing
1. The death throes -- people are using botnets or other paid promotion to build up brands but most of the success is grandfathered

Only phase 3 has a level playing field. And I'm not saying that platforms should be fair, but I think many users believe that they're consuming 'real' content; there's product value in giving them that, and risk if they find out that's not how it works.

School in the US has, in my opinion, has gone through the same steps -- it's very expensive and for the most part doesn't pay off its debt.

These platforms are land grabs with phases of decay. I think github has stayed relevant for longer, possibly because of [personal value precedes network value](http://bokardo.com/archives/the-delicious-lesson/). Maybe there's a corollary that networks that are tools first and networks second are more sustainable? Or maybe GH by its nature has higher % of experts in the voters who star things. *Or* maybe javascript and go have achieved dominance entirely through reputation spam and we're living in a simulation.

## User-generated content

The lego MMO was delayed or derailed or something because [the moderation costs of detecting penis sculptures was too damn high](https://twitter.com/glassbottommeg/status/604407061380640768). (Which is technically not fraudulent but presented a similar behavior policing problem).

Elsagate, which I gather is a youtube genre of beloved cartoon characters dissecting each other, is a bad actor problem that's created demand for a dedicated 'youtube kids' product and numerous clones.

To me this is the same problem as the mortgage debt bubble -- when an institution (whether youtube's recommendation algo or FNMA) creates infinite demand for a product, and they run out of high quality items, they'll start shipping low quality items.

The recirc bar on these sites is *never empty*. You do the math.

## Short of punishing bad actors, at least reveal them

Right now reputation is one-way. That means there's no penalty to liking a lot of stuff, or a lot of bad stuff, or one bad thing all together. As a person who avoids social media like the plague but gets sent links, I'm interested in knowing more about the like count -- who's liking these posts? What else do they like? Are they acting in correlated bundles? Have they liked things that I, or someone I follow, has marked as spam?

Platforms are using stats like this internally to identify 'coordinated inauthentic content' but my point is that these scores aren't exposed to ordinary users. I suspect that this is partly because FB / TWTR don't want to look like troll farms, and partly because the scoring still only half-baked -- it's a dance between machines and human moderators using editorial discretion to decide who to ban.

I worked on a (tiny, defunct) product called [trustgator](https://github.com/abe-winter/trustgator) that used trust graphs to contextualize comments on a reddit-like interface. This isn't the only one of these or the best, but I hope a major platform adopts something like this so that users can get more information about who they're listening to.

## It's up to consumers & designers

Fake news and fake nikes have this in common: they're happening on a platform that benefits from fraud, but isn't doing the deed themselves.

I watched Gaslight, the 50s movie that named the trope. She stayed crazy until she got external validation that she was being deceived and controlled.

Consumers, I think, feel pretty gaslit about various digital products. Is facebook listening to our conversations? It's really hard to prove what's going on, even to ourselves, so we rewrite our memories and go on with our lives.

I pay for everything I possibly can because when I pay for something it creates a paper trail and clear promise to deliver. I avoid free products like the plague. I hope more people take this route.

Until consumers get with the program, product managers & designers of free or social products, it's up to you: you're going to have a fraud problem after you launch, so plan for it and design the mitigations now. Hard-to-spam, hard-to-game products are the future.

{% include flatpixel.html tag="prod-fraud" %}
