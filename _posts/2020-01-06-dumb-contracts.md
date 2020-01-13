---
layout: post
title: The internet runs on (dumb) contracts
description: Consumer docusign could be huge
noindex: true
---

Think of all the random crap you sign that's life-or-death important for the company to have on file, and to be an enforceable contract: privacy disclosures or arbitration agreements, the former gaining steam as CCPA joins its european cousin. Or life-or-death for you: health insurance, for example.

I'm starting a business and I've signed up for like 4 things a week for the last month, and they all have a zillion contracts.

Here are some common pain points:

* No receipt: there's rarely a paper trail to let me know what I've agreed to
* Readability: would be nice to separate arbitration boilerplate from deal terms specific to this company

There's non-zero risk on both sides to these things, too little case law to call them ironclad, and no real way as a consumer to understand your obligations without massive input of work. I may be in a small minority of people who read these, but *everyone* hates them. I think this is an overlooked area of legal tech where innovation can serve both parties to the contract.

1. toc
{:toc}

## Are these valid contracts?

The bigger question is are these even contracts? In the US there are conditions that must be met for a contract to be enforceable in court. Some of these conditions have weird interpretation online: consideration, intent to contract, meeting of the minds.

'Consideration' means are both parties getting something. I'm not sure what this means for free products online, but beyond free products, a lot of terms of service don't clearly name what either party is getting. They have a bunch of lines releasing the vendor from obligation but there's no tit for tat.

This weasely behavior is great for companies -- not promising to do anything probably discourages legal challenges. But the flip side is that it could invalidate these contracts.

The lack of a neutral 3rd party that's acting as notary affects meeting of the minds. Because I'm a terrible person and a generally disgruntled consumer, I'll often edit the HTML of TOS to remove terms that I think are unconscionable or non-reciprocal. I screenshot them. Are these vendors keeping a record of the contract that I signed or the one they sent me? If the latter, we may not have the same picture of the agreement. I suspect there's no relevant case law here in the digital space, but there's at least one international case where a write-in change was honored.

Institutions are very entitled about 'the document we sent you is the only document', but my read is that courts find this digusting. I certainly do.

For consumer products, there's a legal phrase 'contract of adhesion' that means a huge boilerplate contract written by one party. Legislators and courts have both been variably leery about enforcing these in the past. If you read these, some of them have language like 'this document has been drafted equally by both parties' to try and get around this. Yuck.

## Case law & zappos

I'm not a lawyer so you should stop reading here, but my broad understanding of the legal theory is that there's a clear distinction between 'clickwrap' and 'browsewrap'. Clickwrap has generally survived legal challenge, with I think some trickiness about the ability to return the product for a full refund if you've paid for something before you had a chance to review the contract.

Browsewrap has not been so lucky. The main case here is a class action against zappo's, the online shoe warehouse also known for holacracy and its generous return policy. The part of the case I understand best is that the plaintiffs challenged the arbitration clause in the contract, i.e. they wanted to sue in a real court even though the TOS said they waived that right.

The plaintiffs won, and the winning argument was basically:

* The FAA ([the *real* FAA](https://en.wikipedia.org/wiki/Federal_Arbitration_Act), not [the failed regulator of drones](https://www.lawfareblog.com/dc-circuit-shoots-down-drone-regulations-taylor-v-huerta)) sets a higher bar than mere intent to contract, and:
* There was no evidence that the consumers in the class had even been shown the terms, much less agreed to them, because:
* In a paper printout of the homepage, the link to the terms appeared at the bottom of page three

And you thought you lived in a paperless society.

My point is that it's not clear when these contracts are valid, there's relatively little case law here, and UX probably will matter a lot of more of these come to light.

## The future of e-sign is negotiable terms

A bunch of writers on tech talked about consumer privacy tools being a growth area in 2020. Other than ad blockers I'm not sure what this means, but tools for transparency and fairness in contracts wouldbe a step forward for me.

A third-party platform for TOS / privacy policies could be a win-win:

* It's cheaper and safer for companies -- the agreement platform can do their research once and insure you against terms-related GDPR risk
* It's more readable for consumers because it can bundle familiar terms that they've seen before and highlight just the changes

Most interestingly, it can let consumers say no to things they don't like. If a PM is getting a stream of even 10 people a month saying 'I'd use this product if you removed this term', that's enough for them to listen. Consumer feedback is practically a form of civic engagement in the institutional web, and small cos get few enough of these letters to listen when there's a trend.

TOS are gibberish but they're gibberish shaped like the company's feature set. Adding a feedback mechanism at the buying stage gives consumers a form of market power over how their products work that doesn't exist today.

{% include flatpixel.html tag="dumb-contracts" %}
