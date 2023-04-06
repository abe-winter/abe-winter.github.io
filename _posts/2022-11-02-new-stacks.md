---
layout: post
title: Trying new serverless tools
categories: stackshare
noindex: true
---

* toc
{:toc}

## Project / goals

I burned a weekend to try some hosting platforms. Learning goals:
- Try a non-Auth0 hosted auth provider
- Try cloudflare pages for a CMS-like app

The stack I ended up with: CF pages, react, supabase auth, CF functions, GCP functions for one python thing.

Total cost: $18 for a vendor which I ended up not using, $5 for cloudflare pages pro (to get rid of 50ms runtime limit so I could do external API calls from my functions -- tbh I could have hit my external API directly, or refactor to a queue, and save the $5). Also $10 for a domain I ended up not using. Supabase will cost me nothing up to 50k users.

## Pain points

### Auth pain

Investigated but didn't use:
- cloudflare zero trust: (their auth product) costs multiple dollars per user, prohibitive for b2c
- ory.sh: was weirdly slow (like 800ms to check my session). It seems to not support jwt, i.e. I presumably cannot extract a user ID from their cookies on the server side.
- looked at clerk.dev and supertokens. The supertokens splash page loads slowly, which was a turnoff, and there was no login link on their homepage, bad sign for a login provider. (Eventually found it behind the signup link).

I ended up with supabase, which isn't even an auth product primarily. I think this allows them to treat auth as an afterthought and give like 100x the value for the money. (I'm not paying for supabase -- I paid $18 for pro ory to see if it made it faster; it didn't). Supabase isn't perfect:
- at least 2 versions of their auth UI exist, both deprecated, and there are infinite versions of their docs out there, most stale. I ended up downgrading a library to get mutually compatible session + UI libraries
- the settings for redirect after email verification consumed like an hour, in part possibly because I rolled back one of their deps. Still not sure how I solved this

Despite the warts, I came away liking supabase and wanting to try its other features.

I used a random library with no tests to decode jwts in cloudflare workers. I feel bad about that but in general am happy with the result. I wish the supabase jwt could be verified with a public key so I don't have to ship my private key, which is *highly* sensitive bc it lets anyone masquerade as anyone. I think, per some github issue, that SB is working on asymmetric jwts.

### Non-auth pain

Cloudflare local tools were surprisingly good (I wasn't expecting them to exist at all), but not a smooth process. Most of the docs information is for workers, not functions; functions is still in beta, so this is fair.

Docs led me to a false start with miniflare when I needed wrangler. Why have 2 tools? Converge and deprecate. `wrangler.toml` seemingly isn't supported for what I'm doing. Docs were vague on where the /functions directory should go -- inside my pages folder, or in cwd? (in cwd apparently). CF dash doesn't seem to list the functions I've deployed. and I'm still not sure how to find the functions error log. Cloudflare workers support secrets (i.e. vars with extra encryption), but functions seem to not.

Lack of html templating in cloudflare workers was small but surprising. [Flareact exists](https://blog.cloudflare.com/rendering-react-on-the-edge-with-flareact-and-cloudflare-workers/), and CF / vercel both support some 'edge compute' feature, and [vue cares](https://jross.me/server-side-rendering-vue-cloudflare-workers/). But I was surprised some HTML templating approach wasn't built into pages / functions -- there are various optimizations you can do around caching + rendering once this exists in a standard way.

One component is in python because I needed a specific library. I think CF pages supports python, but via some kind of transpiler documented in what felt like an april fools blogpost. I used GCP cloud functions for this one piece.

## What I liked

The CF functions file-based approach to routing, which I think next.js does too. Below your functions/ dir, folders are treated as *paths*. So like `./functions/api/accts/[acct]/verify.js` on disk will show up at `/api/accts/ACCTID/verify` on my server. Not life-changing but fun, easy to understand, and forestalls a lot of 'where does this go' arguments.

Supabase generally. I love the idea of supabase and have been looking for an excuse to use it. Somehow the objectively bad onboarding experience left me even more excited.

I was worried about cloudflare KV because it's eventually consistent (i.e. writes won't always be readable right away). I'm still worried, but while playing with it I didn't run into any trouble. They have a 'durable' product that probably solves this.

CF wrangler for local testing. Docs could be better, but once I got it running, it did its thing. Works fine without a CF acct, and the only problem I ran into after deploying was missing variables (and I couldn't access error logs to be sure that was the problem). If you have 2 hours you should try wrangler locally with static html, functions and KV. It will open your mind to cms-like backend architectures.

Buildsystems: GCP functions and cloudflare both have non-docker approaches to build + deploy. I like docker better than what came before, but I'm increasingly unhappy with docker as an image format because it makes dependencies so hard.

If you use a dynamic language, libraries are just smallish files that take a ton of work to download and unpack. Docker is a technology for making you download ALL of them when you change ANY of them, which affects build times, storage costs, and transfer time. Docker is a technology for treating your OS, dependencies, and app as a single bundle.

I think docker could *easily* fix this by supporting unordered layers for deps, and by exposing some basic cache / workflow tools for package managers. Every time I have to run apt or pip in docker I die a little inside.

## Conclusions

Overall -- least painful first attempt at a serverless platform.

On AWS my first lambda experience involved booting a piece of hardware to tunnel to aurora serverless (already a bad sign), and then aurora serverless having slow starts so I had to keep *it* always-up, and then I tried doing something relational with dynamo and got the consistency wrong. On GAE, I had to keep my instance always-up because the image was huge and booted slow, then got billed for like 30x usage because every old version was still running in the background. (They rescinded the bill).

This time was not as bad; it didn't feel like I was fighting the system (perhaps because this time I wasn't trying to run a multi gigabyte docker image with django and numpy). There are many things these tools *don't* do well, but the hammer-nail zone for them is BIG.

Supabase as auth provider was clunky but ultimately great. I've always avoided firebase because it's obviously designed to farm me, but the value prop of firebase architecture is real. From SB, I got a cultural signal that they weren't building their system to nickel and dime me on things that should be open source.

The cloudflare local dev experience was unxpectedly good and worked unexpectedly well with my other tools.

I'm paying like $200 a month for a tiny kube cluster on google cloud (for other projects). I built on kube because it's at least theoretically cross-platform, i.e. I could switch clouds or self-host in an instant. But it's also beefy to run and makes everything hard. I build on SQL because it's nice when I need it, but most of the time it's overkill and I don't need it.

Kube is in theory an efficient way to self host OSS apps that weren't designed for serverless. But these apps are incredibly inefficient -- they're running slow on hardware that is small by cloud terms, but still modern silicon that works at the limits of energy and matter.

I don't work much with serverless but my sense is that storage options and runtimes are both not standardized.
If they converge, that would be an incredible boon for self-hosters, who run lots of services and don't load them heavily.

{% include flatpixel.html %}
