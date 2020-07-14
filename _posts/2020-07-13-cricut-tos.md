---
layout: post
title: Cricut TOS readthrough
categories: tos
new: true
---

This is part of a
[series]({% post_url 2020-07-14-alltos %})
where I read terms of service and vent.
As always, I'm not a lawyer and you owe me one hundred dollars if you make it to the bottom.
(Trust me, I'll know).

* toc
{:toc}

## Terms of use

[Terms of use](https://cricut.com/en_us/legal#terms-of-use)

> Although we may attempt to notify you when major changes are made to these Terms of Use, you should periodically review the most current version at http://www.cricut.com/legal#terms-of-use. Cricut may, in its sole discretion, modify or revise these Terms of Use and policies at any time

I think this makes it not a contract.
We're getting off to a strong start.

> You acknowledge that in establishing your Account you have provided us with certain personal information about you. While we normally keep this information confidential, you agree that it may be necessary, from time to time, to disclose certain personal information to third parties and **you consent to all such disclosures.**

Emphasis mine.

> You have verified and determined that your use of the Site does not violate any law or regulation in any jurisdiction that applies to you. It is your sole responsibility to ensure that this is the case.

This is like a greatest hits of bad e-commerce boilerplate

> You fully understand the methods, rules and procedures of the Site

God I hope there's a reverse engineering ban somewhere downstream of here

> You will not engage in any conduct that injures or may injure the business, reputation or goodwill of Cricut.

Vague

> should you learn that any user is using the Site or any Sponsored Activity for fraudulent or otherwise illegal, infringing, or disallowed purposes, you will immediately notify us.

Cuttlefish and asparagus

> You will not mask your identify in any way, including without limitation, IP masking by accessing the Site or any Sponsored Activity over any type of proxy server, through IP masking software or the like.

1. what about NAT, is that 'the like'?
1. 'mask your identify'. If it's too long to proofread it's too long for a consumer to fairly understand.

> Not to engage in the sale of advertising, sponsorships, or promotions on any page of an ad-enabled blog or website containing Content delivered via our Site

Let's recap -- Cricut is selling a *printer*. I would think anything I printed on it would be fair game?

> Not to use or launch any automated system, including without limitation, "robots," "spiders," or "offline readers," that accesses our Site in a manner that sends more request messages to the Cricut servers in a given period of time than a human can reasonably produce in the same period by using a conventional on-line web browser;

A 'conventional online web browser' has a REPL

> you will be exposed to Content from a variety of sources

you better believe it

> You agree that Cricut is not liable for any loss caused by any unauthorized use of your Pay-Pal Account, your credit card or any other method of payment by a third party in connection with our Site

Unlikely

> Pricing Errors. Please note that even though our Site is composed with care, it is possible that the pricing information on our Site contains errors. Cricut is not bound by our offer and we reserve the right to cancel your purchase in the event of such error.

I wonder about this.
Guessing there's case law on this sort of 'bad print' situation that I'm not familiar with,
but 'not bound by our offer' is dangerous language to have in a contract and should, in a sane world, invalidate the whole thing.
In general, zooming out, if Cricut isn't bound I'm not bound either.

You might get away with this in a business deal where one party is taking risk to manufacture a product and needs to be compensated for the risk whether or not they deliver,
but I couldn't see this getting enforced in a contract of adhesion.

> Risk of Loss. All items purchased from Cricut are made pursuant to a shipment contract. This means that the risk of loss and title for such items pass to you upon our delivery to the carrier.

Once again, probably not.
The shipper is Cricut's vendor.
This would be like saying 'someone else manufactures our crap, they might send you box of dogshit, ah well.

> The use or distribution of tools designed for compromising security (e.g., password guessing programs, cracking tools or network probing tools) is strictly prohibited

There it is.
I wouldn't put this line in the same document as the 'methods, rules and procedures' line above.

> You affirm that you are either more than eighteen (18) years of age, or an emancipated minor, or possess legal parental or guardian consent, and are fully able and competent to enter into the terms, conditions, obligations, affirmations, representations, and warranties set forth in these Terms of Use, and to abide by and comply with these Terms of Use. In any case, you affirm that you are over the age of thirteen (13), as our Site and the Sponsored Activities are not intended for children under thirteen (13). If you are under thirteen (13) years of age, then please do not use our Site or engage in any Sponsored Activity. There are many other great websites for you.

This paragraph goes through 4 of the 5 stages of grief.
Pick an age.
Guessing this is a COPPA compliance thing?
Maybe there's case law here?

I'm no lawyer but I know a thing or two about math, and 18 > 13 in most parts of the universe.
Also if someone isn't competent to enter a contract, they're not competent to enter in this clause.
This one is over my head.

## Angel policy

[Angel policy](https://cricut.com/en_us/legal#angel-policy)

This part is a first for me.
My *guess* is that they're trying to describe the use of a bundle of content that they've sublicensed from Disney etc, which is fine, but this is *so badly written*.

> Cricut, Inc. (“Cricut”) is pleased that individuals wish to create and sell personal craftwork items incorporating our products, designs and images. This Angel Policy provides limited permission for certain sales of such craftwork items, but not others. Please read this entire Angel Policy carefully to see how it applies to You and Your proposed sale of craftwork items.

You're selling a printer, pal. If you sell me a printer and then sue me for printing something on it, nobody will ever buy another printer from you.

> “You may not copy, reproduce or in any other manner duplicate the Cartridge or Content, except as authorized in this Agreement or in the Angel Policy.”

I don't know what the 'Cartridge' is but I'm assuming this is at least wrong in right to repair states.

> “You should read the entire Angel Policy carefully from time to time to see how it applies to You and Your proposed sale of any craftwork items. In the event of a conflict between the provisions of this Agreement and the Angel Policy, the terms and conditions of the Angel Policy shall govern.”

WRONG. No court will enforce a 'from time to time' contract that can be unilaterally updated as applying to a printer that I paid for. You're no John Deere tractor.

> Cricut will change this Angel Policy from time to time and post the most recent version on this website.

La la la

> Copyright Materials means products, designs and images that are subject to protection as works of authorship under U.S. or international copyright laws

It absolutely does not. Do you mean 'copyright*ed* materials'? 'Copyright materials' sounds like it means materials pertaining to the enforcement of a copyright. Redefining a term of art like this is bonkers.

> Cricut will change this Angel Policy from time to time and post the most recent version on this website.

La la la

> Copyright Materials means products, designs and images that are subject to protection as works of authorship under U.S. or international copyright laws

It absolutely does not. Do you mean 'copyright*ed* materials'? 'Copyright materials' sounds like it means materials pertaining to the enforcement of a copyright. Redefining a term of art like this is bonkers.

> Notwithstanding the foregoing, Walt Disney Company (Disney Consumer Products, Inc.), Sesame Workshop, Hello Kitty (Sanrio, Inc.), Warner Bros. (DC Comics, c/o Warner Bros. Consumer Products, Inc.), Martha Stewart, Kirstie Allsopp (BBC Worldwide Limited), Entertainment One UK Limited, Nickelodeon (Viacom International, Inc.), and Boys Scouts of America characters and images MAY NOT be reproduced and sold

'Boys Scouts of America' characters

> Copyright Material may not be altered in any manner, including without limitation, copyright notices, or the like. Any such alteration will be considered an infringement of copyright

starts with F ends with 'air use'

> Any modification or termination posted on this website shall be deemed effective and binding upon all parties five (5) business days after posting

Doubt it

> We believe the Angel Policy is the most generous policy in our industry

I suspect this is binding

> The Angel Policy authorizes you to sell up to 10,000 completed projects annually (i.e., cards, scrapbook pages, finished cakes), using cuts made with Cricut products. It does not, however, authorize you to produce and sell individual, unassembled cuts using Cricut products (i.e., mass producing individually-cut letters or shapes to re-sell)

Zero chance this is enforceable. Say it with me -- you're selling, not leasing, a printer. I could use this product to do appendectomies and Cricut wouldn't have a cause of action.

> Any project with a user uploaded image is by default saved as private and no one else has access to it. We do not sort through user projects looking for images that we can add to our image library to sell/give to others.

I didn't ask but now I'm wondering. Also 'sort through'? Also 'no one else has access to it' is certainly wrong.

> Can I report potential copyright violators? Yes. We appreciate our consumer’s assistance in helping us to protect the intellectual property rights and livelihood of the artists whose work we license

Again with this

## Privacy policy

https://cricut.com/en_us/legal#privacy-policy

> Keep in mind, we do not sell, rent, or otherwise disclose your personal information to third parties for their marketing purposes without your consent

Scroll back up to 'consent to all such disclosures'

> PLEASE READ THIS PRIVACY POLICY CAREFULLY BEFORE USING OUR SITE

> By using our Site or participating in a Sponsored Activity, you acknowledge that you have read this Privacy Policy, and agree to be bound by it.

Nope, wrong

> to the extent you voluntarily provide your Personal Information to us, we collect such information

> At times, Cricut may make certain Personal Information available to strategic partners that work with Cricut to provide products and services, or that help Cricut market to members.

No kidding

> Unfortunately, however, no data transmission over the Internet and no data storage can be 100% secure

Classic 'unfortunately however' construction

> You have a right to know if your Personal Information was stolen due to a breach. We will notify you no later than 72 hours after we become aware of the breach. We note that an inability to determine whether a breach has occurred which is caused by a failure in our internal systems and policies does not excuse a delay in reporting.

WTF?!?!?!?!?! What does this mean? How can they notify me if they're not sure a breach has occurred? Is this required by statute? This is unconscionable *on their side*.

Who writes this garbage.

> We may send cookies

Strength to your arm

## What happened instead

2+ week shipping = too little too late. Bought from amazon instead.

Worth it for the entertaining read though.

{% include flatpixel.html %}
