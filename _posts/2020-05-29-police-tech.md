---
layout: post
title: Tech / future police
description: "There are four of us, we're one team"
categories: dont panic
author: Abrrrham Winter
new: true
---

Not in any way inspired by anything happening in the news this week, I gathered up my notes about how technology will change policing.
By 'policing' I mean specifically regulation of behavior in public spaces.

This is pure sci-fi thought experiment, I don't work in this area or study it, but in my opinion as a technologist all of these things are technically feasible and the base technologies are COTS in non-police applications today.

Zoom way way out and the impact of technology on anything is to:

* Make new things possible
* Make existing things cheaper

'Lowering the cost of policing' is not necessarily increasing fairness which means it will go wrong before it goes right. New tech has been better at increasing capabilities than improving governance.

* toc
{:toc}

## Robocop(s)

Delivery rovers, quadrupeds roaming hospitals, quadcopters delivering medical supplies, volvo SUVs with LIDAR towers -- these are all real now somewhere.
5 years ago they weren't.

None of these robots are *armed* today.
Police robots may not be armed either, especially not at first.
I can imagine 'patrol rovers' wandering around to render aid in various ways --
helping someone carry their groceries across the street, stand by and record if someone is in a fight or getting mugged.

Over time these bots may gain legal arrest powers even if they're not armed;
they can stop you and demand you wait for a human, and they can chase, or sensor networks can track you if you flee.
Over time, on the branch of history that we seem to be on, they may acquire nonlethal weapons or more.

I can imagine also a 'personal robocop' for civilians --
a taser or small armed drone you have on your person that needs to be remotely unlocked by a human 911 operator.
Automating the unlock decision is an interesting area as well.
Dangerous if unfair, but with the potential to create a database of 'use of force events' that leads to better transparency and norms.

Having people carry around locked weapons is better, I guess, than having people carry around weapons that *aren't* locked.
But it's not that simple --
it creates arms races between attackers and defenders, it creates opportunities for malware to unlock or trigger 'personal guard bots',
or fool them into attacking the wrong targets.
It means more total weapons.

'Personal robocop' works for actual police too; one human patroller with robot backup.
They can be specialized robots like K-9 (for finding drugs / explosives / people), or just extra muscle (for helping carry stuff as well as for violence).
General Dynamics wanted the big dog robot to do this for military, acting as a 'mule' to carry stuff over rough terrain, but it ran off a lawnmower engine which was too loud.

I'll bet good money on a legislative debate over 'remote arrest powers' in the next 5 years.
We've already had something similar in the SCOTUS case on GPS trackers --
the court ruled trackers make it too easy to track people, and violate your 4th amendment rights in a way that being covertly followed by a cop wouldn't.

## Panic buttons and norm wizards

Tech lowers costs.
It won't just lower the cost of policing.
It will lower the cost to defend against policing.

Criminals and non-criminals have different reasons to want this but both probably will want it and will have the same broad needs:
protection from surveillance and enforcement of norms.
The two groups will have different adoption curves though.

Enforcement of norms: my most common interaction with police is the TSA.
For a while every time I flew I got searched, and so I read up on the law here and tried to develop a patter to control the situation.
I wasn't successful.

Conversations I've had:

* 'Can I record this search / if you turn that on we'll arrest you for eavesdropping'. (This was in an airport in Illinois with zillions of cameras, no expectation of privacy by anyone, and it was an interaction that I was a party to).
* 'Am I under arrest or am I free to go / if you don't submit to a search we'll arrest you / arrest me for what / tresspassing' (this went on for an hour, I missed my cousin's wedding)
* 'Why are you calling the bomb squad / you tested positive for accelerant / is there any other explanation / you could have been on a freshly fertilized lawn'. (In this one I was instructed to submit to a 'private room crotch rub')

Also one time I got a ticket for switching cars on a (stopped) subway. The conversation then was 'show us your ID / am I under arrest / we'll arrest you if you don't show us ID'.

My point isn't that these conversations are against the rules.
I don't know the rules, some of what the cops said is potentially wrong, and these interactions are happening hundreds of times a day with no record.
I've always wanted an audio-recording panic button so these conversations would be on the record.
Even better would be cheap, live advice, or some sort of 'choose your own adventure' script.

The script would act as a 'norm wizard', guiding me through the situation, letting me know when I was in uncharted territory, and telling me when my counterparty breaks a norm.
I'm saying 'norm' not 'rule' because these norms don't have to come from the government -- whatever private party created the wizard would have tremendous influence.
Police haven't been willing to publish sane scripts for these situations; whoever does so will have a lot of power to shape the boundaries.

If you're an agency that employs law enforcement officers and someone asks 'are there limits to your authority' and you say 'not really', you're creating a 'norm vacuum'.
I think that private groups like the ACLU can disrupt this agency self-assigned absolute power by filling the norm vacuum with tools like panic buttons and arrest scripts.

## Camouflage

Surveillance is cheap and getting cheaper --
we have more cameras and better software for classifying what they see.
[Mr Ao got tagged by face software at a Jacky Cheung concert](https://www.bbc.com/news/world-asia-china-43751276).
Gait gives you away too.

In the US, there are specific situations where it's illegal to avoid surveillance:
tampering with an ankle bracelet,
tampering with lavatory smoke detectors,
highway radar jammers in some states (and even detectors).

These are technologies designed specifically for detecting crime, and so we make it a crime to mess with them.
But 'crime detection' will get a lot more general purpose, and so will mass location tracking.

At least today, [adversarial fashion](https://boingboing.net/2019/08/10/chaffing-the-alprs.html) *isn't* banned.
(Though I can imagine catch-all 'don't mess with the police' laws like obstruction of justice being used to harrass someone wearing one of these).

When will it be illegal to project a false scene into a street camera?
Under what circumstances will it be permitted to seriously impair a camera or device in states with a right to privacy?
Will we ban [wearable microphone jammers](https://techxplore.com/news/2020-02-team-jammer-bracelet-outsmarts-microphones.html)?
What about tech that doesn't hide your presence but masks your activity (adversarially invisible skateboards in a no-skate area, for example).

All the tricks of prey species for evading predators (for example, outline disruption in the [glass frog](https://youtu.be/U7zARByAu1c?t=73)) will be on the table for pedestrians when visual detection is used against us.
Like a lot of the novel ills of this century, camouflage vs surveillance is a form of information warfare.
I think making the city street a conflict zone will have a wide impact; it won't just affect the technology we carry, it will bend back the curve of urbanization.
Density will become less safe.

## Automated bureaucratic decisionmaking

Here are two wildly different takes on fairness when computers make administrative decisions.

First, the [COMPAS recidivism core analyzed by propublica](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing).
COMPAS is a software tool that spits out a risk score that a given person will commit another crime.
I think these numbers are used to advise sentencing.
Propublica borrowed the risk scores from arrestees near Fort Lauderdale and discovered that it mispredicted black arrestees 2x more than whites.

Second, from this week, research saying [black people are more open to automated bureaucratic decisionmaking](https://academic.oup.com/jpart/advance-article-abstract/doi/10.1093/jopart/muaa019/5848482).
(I think the actual claim is that 'relative to polled police, polled blacks place relatively more trust in the machine vs human decisions when they find out that the agency making the decision employs few blacks'. That's a mouthful).

It seems like these two points contradict each other but they don't:
(1) machines can be biased, (2) machines can be a solution to human bias, or at least a leveller.

Algorithmic fairness isn't a solved problem;
I think it's only been in the public eye for 5 years (though wikipedia has some [examples from the 70s and 80s](https://en.wikipedia.org/wiki/Algorithmic_fairness#History)).
I don't know any good 20th century scifi about racist computers -- this is an area that hasn't been explored as thoroughly as gender and cyberspace.
It caught us flatfooted.

The trends to watch here are probably
(1) improving access to justice by using technology to increase the speed of bureaucracy,
(2) improving access to justice by simplifying filing, and
(3) making sure the *quality* of automatic justice is non-zero.
The third one is hard.

## Observing and controlling sentiment

Not sure whether this fits my 'regulation of behavior in public spaces' definition but online is kind of public, and speech is kind of behavior, so I'm going for it.

China is way ahead of the game in regulating online speech, so much so that they can exercise some subtlety:
a 2013 paper says that they're [fine with criticism, as long as it doesn't 'spur social mobilization'](https://gking.harvard.edu/files/gking/files/censored.pdf).
(A lot has changed since then though; Winnie the Poo wasn't on anyone's radar and the [Grass Mud Horse](https://en.wikipedia.org/wiki/Grass_Mud_Horse) was still young).

China does this mostly with human labor I think;
they have a corps of party members who get paid half a yuan to post pro-gov stuff online, and so are called the '50 cent party' or 'wumao dang'.
For at least a while, [you couldn't say wumao on youtube](https://techcrunch.com/2020/05/26/youtube-china-comments-wumao-dang/), and nobody understands why.

Sentiment analysis at scale isn't what I would call effective, as online speech is terse and full of slang, but [brands still pay for it apparently](https://www.brandwatch.com/).
Sentiment surveillance is IMO a form of 'future crime', i.e. predictive policing, i.e. some combination of racist and random.

Sentiment isn't only something to measure.
Facebook has run experiments in [mood manipulation](https://www.theatlantic.com/technology/archive/2014/06/everything-we-know-about-facebooks-secret-mood-manipulation-experiment/373648/).
My guess is this isn't very effective on most people and amounts to harrassment, but nothing has every stopped governments from harrassing groups at scale.

The ability to target and influence groups is what cambridge analytica was accused of in 2016.
I read somewhere that facebook stopped fighting Alastair Mactaggart's CCPA campaign because the cambridge analytica was too much bad press for them.

As these capabilities emerge from scifi to reality, I wonder how ordinary people will defend themselves against manipulation.
One answer is that we'll purchase 3rd-party services that explain what content is being personalized for us and to whose benefit.
This probably isn't possible for individuals (we're busy enough), but a political group might do it -- 'we vote as a block, let's compare our personalization to a neutral and see what the system wants of us'.

Facebook apparently hates this kind of defensive counter-surveillance because they [blocked some tools in 2018](https://www.propublica.org/article/facebook-blocks-ad-transparency-tools).
Propublica / quartz are [back in this game now](https://projects.propublica.org/facebook-ads/), though.

Another defense against manipualation is to never log into anything and don't trust anything that makes you log in.
(And find ways to resist identification of incognito sessions).
I feel strongly about not consuming while logged in; even when I paid for the NY Times I still read it in an incognito browser.

## Active hostile architecture

[Hostile architecture](https://www.atlasobscura.com/articles/anti-pigeon-spikes-hostile-architecture) is a real world thing that means 'pigeon spikes for people'.

I think of these as non-punishment ways to deter behavior.
They're passive now
(benches you can't sleep on, spikes, [paint that 'pees back'](https://www.theguardian.com/world/2015/nov/27/walls-that-pee-back-people-urinate-in-public)),
but technology that can detect undesirable behaviors could change that.

Any form of 'I see you' acts as a deterrent, so something as simple as a pop-out camera or lights changing to red could do the trick here.

Noise is another area:
better noise cancellation technology would certainly change my NY subway experience.
I read somewhere that playing back loud speech or music at a delay is uncomfortable for the speaker / ruins the music.

Interesting recent law here is SCOTUS rejecting cert for an [8th amendment ruling making it hard to criminalize homelessness](https://www.latimes.com/politics/story/2019-12-16/supreme-court-lets-stand-ruling-that-protects-homeless-who-sleep-on-sidewalk).
A lot of hostile architecture is in this ballpark, addressing 'doing indoor behaviors outside' (like sleeping and peeing).
I'm not sure what current rights framework would apply to 'selectively hostile' public spaces that targeted nuisance behaviors rather than survival.

## Going dark

AG Bill Barr is continuing his 'going dark' fight against encrypted communication.
(I ran a consumer survey on this -- more people understand encryption than I expected, more care about it, and I think it's bipartisan).

A retired philly cop was [released after 4 years on jail](https://arstechnica.com/tech-policy/2020/02/man-who-refused-to-decrypt-hard-drives-is-free-after-four-years-in-jail/) for refusing to decrypt a hard drive full of child porn that he'd shown to an undercover fed.

A related area to communication privacy is digital payments.
India ['demonetized' large bills in 2016](https://timesofindia.indiatimes.com/city/jaipur/Roll-back-demonetization-it-has-caused-riot-like-situation/articleshow/55445150.cms), I think to erode criminal wealth and help with tax enforcement.
China is building their social credit system on top of alipay, alibaba's digital payments infrastructure, which has penetrated widely in a short time.

Backdoored, non-warrant-proof encryption is a police technology that requires serious legal legwork to deploy, but would also make it hard for a criminal to move around or eat in a society where most financial and communication interactions are electronic.

Semi-related to encryption is cryptographic signing:

I heard an interview with Rachel Botsman, I think a journalist who writes about trust, where she claimed that the existence of deepfakes threatens the validity of every piece of evidence in criminal law.

Proving the chain of evidence will in theory be a job for technology, but I'm not sure how you do this in practice;
encrypted communication requires that you trust the party who holds the private key.
If that party is the prosecutor in a criminal trial, they could just as easily sign a fake image.

## Future of legitimacy

It's easy to focus on 'how do you enforce' and ignore the 'should we enforce'.
I think IP law made this transition between napster and youtube -- I think that 5 years earlier, viacom could have buried youtube in equitable damages.
That's an example of an area of law that relaxed because the internet reduced the cost of distribution;
if youtube had been burning CDs and mailing them to people, it would have been an easy case.

Cheaper policing is an inverse problem: it gives us the option to write shiny *new* laws because our enforcement technology is cheaper and more capable.
It also presents the challenge of how to police evasion of surveillance.

If policing is so prevalent and so overreaching that people start to hate and resent it
(and for a lot of people we're there today),
the fact that we *can* enforce rules using technology doesn't mean that we should, or that the rules are good.

I don't have an answer for how to prevent this, but we need a legal framework for dealing with laws that do more harm than good.

{% include flatpixel.html tag="police-tech" %}
