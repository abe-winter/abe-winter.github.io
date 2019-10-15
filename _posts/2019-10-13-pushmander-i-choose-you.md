---
layout: post
title: Stop gerrymandering my push settings
description: Respect my authoritah -- or at least my configs
author: Abe Winter
noindex: true
---

Tinder added a live entertainment product. Which is fine but they also sent me a push notification about it. 

I've left several categories of transactional messages enabled, but **disabled** marketing messages (see screenshots below). I'm guessing they're considering their live show to be a new category. At the moment I can't disable it at all. I'm guessing they'll add a toggle eventually.

I **hate** it when apps ignore my preferences by bucketing new kinds of spam into a new category. This is the push marketing equivalent of waving your hands in front of someone's face and saying 'not touching not touching'. If I'm paying for the ad-free product, this may even be legally risky for the company.

![tinder marketing & transactional notification settings]({{ "/assets/tinder-notifications.png" | absolute_url }})

## If you're going to spam me don't flub the launch

Crossing the transactional / marketing divide is a big no-no in the world of email marketing and should be bad here too, except that we don't have spam filters for pushes. Which is fine because I have the option to uninstall the app, but it's annoying, and leads to bad norms in this space.

The click-through for the push was buggy (on droid, of course) and not only didn't open the new content, but broke page-switching on the app until I backgrounded and reopened. And it seems like tinder has now decorated my public profile with new garbage which I'm supposed to be able to turn off but can't (on droid, of course).

!["Your critical choices will display inside profile. Manage these preferences in profile settings"]({{ "/assets/tinder-critical-choices.jpg" | absolute_url }})

This isn't an unusual story. My guess is most product people at app companies have shipped something half-baked in their day. Heck, Boeing shipped a buggy *airplane*, probably to make a delivery date, and those things are really dangerous.

I'm not just calling out tinder. Every app is doing this. My android device, many years old now, randomly turned on news notifications a few weeks ago and I had to learn how to turn them off. Maybe give me a setting for 'new settings default to off'.

I liked this ["Your change probably isn't for the better"](https://gist.github.com/sleepyfox/a4d311ffcdc4fd908ec97d1c245e57dc) article that I read a while ago. Specifically for push, if I've ever visited your settings page and disabled anything, I probably don't want to be interrupted by your new thing.

## Settings are a great way respect user choice

Product managers are incentivized to provide defaults that benefit the company rather than the user. There are a lot of good reasons to have 'annoying defaults' in your app:

* new users benefit from the extra chattiness as a form of onboarding
* the defaults increase engagement with the app (though potentially at the cost of burnout, which is harder to attribute)
* your app is freemium and the less annoying version costs extra

However there's a difference between 'default' and 'mandatory'. Unless there's a powerful business reason and you've done user research, you should allow users to turn things off.

At minimum, it's a good way to learn about what your users hate. Absent configs, they'll send you this signal by leaving. Only the crazies will bother to write in before they bail.

{% include flatpixel.html tag="pushmander" %}
