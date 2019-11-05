---
layout: post
title: Firebase app distribution teaches people to get phished
description: More domains is not always better
keywords: phans
author: Abe Winter
new: true
---

I spent like 30 minutes today today figuring out whether a 'firebase app distribution' email that I got was real.

The email was from a https://appdistribution.firebase.dev domain, came from a crashlytics.com email, and required me to auth with google oauth to turn it on. Just confirming that an oauth link is on google.com (vs googIe.com or any other weird combination) is hard on a mobile device. And these links are long and you have to scroll horizontally in the smaller-than-the-diameter-of-my-index-finger address bar.

Firebase spiced up the batch by putting the link on firebase.dev, a domain that [according to whois.com](https://www.whois.com/whois/firebase.dev) is owned by:

```
Registry Registrant ID: REDACTED FOR PRIVACY
Registrant Name: REDACTED FOR PRIVACY
Registrant Organization: Charleston Road Registry, Inc.
Registrant Street: REDACTED FOR PRIVACY
Registrant Street:
Registrant City: REDACTED FOR PRIVACY
Registrant State/Province: CA
Registrant Postal Code: REDACTED FOR PRIVACY
Registrant Country: US
Registrant Phone: REDACTED FOR PRIVACY
Registrant Fax: REDACTED FOR PRIVACY
Registrant Email: Please query the WHOIS server of the owning registrar identified in this output for information on how to contact the Registrant, Admin, or Tech contact of the queried domain name. 
```

Wonderful. Not that that would be a positive confirmation if it weren't shady, but it's shady! Charleston road registry [is indeed connected somehow to google](https://www.registry.google/faqs/#!/) but it's hard to know what that means.

No sweat -- maybe firebase.dev is mentioned anywhere on the google docs for firebase. That would be reasonable, right? TLDR [it isn't on this page](https://firebase.google.com/docs/app-distribution) nor does it seem to be anywhere else.

No problem. I logged in to my company's firebase account and tried to find a way to send myself a link -- removing and re-adding myself didn't do it. The firebase console *also* doesn't have any mention of firebase.dev that I found.

I tried going through the flow on my laptop where I could at least verify that the URLs were the characters I thought, and ended up having chrome ask me to switch to safari (?!?!?!) which was (1) insane and (2) probably a dead end. I tried on my mobile device and got into a place where the 'multiple downloads' right on mobile chrome was blocked and there was no 'site settings' entry to fix it. Am I just unlucky in love?

I never got it to work, but the fact that it didn't work is less concerning than the phish-like initial email.

One positive note -- I learned that if you reload the password page on google oauth, the terms & services prompt disappears. I'm now TOS-free and living it up! Woo.

I suppose the TLS on the email verifies that this is from a real crashlytics.com address? In practice I don't know what that means: I don't understand email certs as well as I understand web certs, maybe the crashlytics domain was lost in their acquisition, and nothing else in the email says 'crashlytics'.

FWIW firebase.net was for sale for $3800 when I checked this afternoon. If you sent me this email from that domain it would look slightly *more* legit.

## Setups like this contribute to fraud

Domains are linked to certs. This stuff matters. When a company has multiple domains in play in a conversion flow, I'm going to get cranky and write a blogpost. A less technical person will either ignore it or assume this is normal, but we can't tell people to check the links they click and then have big 5 web companies unload a stream of garbage like this.

## Why are platforms so grabby about their distribution?

Developer ergonomics matters. The ability to deploy to your team without making them jump through hoops saves time and money.

Google is apparently not great with these tools and apple is actively hostile. At least they [bought testflight](https://www.macworld.com/article/2875441/apple-will-shut-down-original-testflight-beta-testing-platform-in-february.html). Remember when [they revoked facebook's private cert](https://arstechnica.com/gadgets/2019/01/facebook-and-google-offered-gift-cards-for-root-level-access-to-ios-users-data/)? Yes, short term this a way to maintain control of your platform, but 

As a progammer who seldom touches mobile, I feel slimed every time I do. The tools are **so bad** and the only explanations I can think of are incompetence, malice or a powerful 'not invented here' culture.

Come on google -- it's one thing to change your charter so you can be evil but it's another to totally suck. Get it together.

{% include flatpixel.html tag="firephish" %}
