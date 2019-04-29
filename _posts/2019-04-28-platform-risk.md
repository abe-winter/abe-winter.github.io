---
layout: post
title: Lulu's Christmas present & platform risk
author: Abe Winter
description: Alle Menschen werden Brüder wo dein sanfter Flügel weilt
date: 2019-04-28
---

1. toc
{:toc}

## Lulu's Christmas present

Remember Lulu, the 'sleek platform to slander men'[^forbes-slander]? I always thought they closed shop because they were a ticking legal time bomb. But recently I saw an interview with the founder[^chong-interview] where she blamed their failure on their sleazy vendor:

[^forbes-slander]: [Why We Should All Be Scared of Lulu App](https://www.forbes.com/sites/kellyclay/2013/11/24/why-we-should-all-be-scared-of-lulu-app/) Kelly Clay in Forbes

[^chong-interview]: [Alexandra Chong On Lulu's Growth and Scaling Challenges](https://techcrunch.com/video/alexandra-chong-on-lulus-growth-and-scaling-challenges/) Techcrunch

<style>
blockquote {font-style: normal; letter-spacing: normal;}
</style>

> We built on top of Facebook as an MVP, it was a way on which on our users could authenticate. ... Then something happened – a realization that we had real platform dependence with our partners and the dependence was something we could not control.

As Lulu gained popularity, men wanted in:

> What men were doing, they would go onto Facebook, and they would change their gender identity to get onto Lulu.

> On Christmas Eve of 2013 I got a phone call, and it was a request to remove ourselves from the store in Brazil. And we did.

Facebook saw Lulu as incentive for college-age men to create fake accounts, and they pulled the plug. In retrospect this makes total sense. Lulu wasn't paying FB to be an identity vendor. FB lets you have Facebook logins to your site **in trade for** hosting a pixel so FB can track its users across the web.

From FB Connect's terms[^fb-terms]:

> We may enforce against your app or website if we conclude you ... are negatively impacting the Platform, and we may suspend your app or website, with our without advance notice

[^fb-terms]: [Facebook Platform Policy](https://developers.facebook.com/policy) section 7.17 under 'Things you should know'. The whole document is worth a read. Some zingers in there like 'don't surprise anyone', 'don't require people to log in to access 3rd party apps', 'don't proxy passwords', 'we may share your contact info'.

Yeah there's a typo in it. Ignore it and remember this instead: never trade with someone bigger than you. Also remember this, again from the terms:

> We can create apps or products that offer features and services similar to your app.

## All places shall be hell that are not heaven

> He serves me, but still serves me in confusion; <br>
> I will soon lead him into clarity. <br>
> -- Mephistopheles (per Goethe)

Platforms are great because they're a giant pool of consumers that you can use to grow your business by word of mouth.

What Lulu learned is that platforms attract partners with a faustian bargain. You offer something that makes their platform a little better, and in exchange you get access to their pool of consumers (but on the platform's terms). At the point where you have any ad revenue of your own they'll treat you as foreign tissue and launch an inflammatory response.

This is especially dangerous for a parallel social network like Lulu because they can compete directly with the platform. But it's also true for news and games on FB, video and music content on Youtube / Spotify, apps on the mobile app stores[^play-fair] [^addiction-crackdown], and third-party sellers on Amazon[^amzn-3p] [^amzn-eu].

[^amzn-3p]: [Merchants Say Amazon Is Copying Their Products](http://fortune.com/2016/04/20/amazon-copies-merchants/) Michal Addady in Fortune

[^amzn-eu]: [Is Amazon Unfairly Copying Products? EU Quizzes Merchants](https://www.bloomberg.com/news/articles/2018-09-27/amazon-s-copy-cat-products-targeted-as-eu-quizzes-smaller-rivals) Drozdiak et al in Bloomberg, with shoutout to Margrethe Vestager.

[^play-fair]: [Time To Play Fair](https://www.timetoplayfair.com/timeline/), a sexy infographic in which spotify claims apple is ripping them off. Apple responded: [Addressing Spotify's claims](https://www.apple.com/newsroom/2019/03/addressing-spotifys-claims/).

[^addiction-crackdown]: [Apple Cracks Down on Apps That Fight iPhone Addiction](https://www.nytimes.com/2019/04/27/technology/apple-screen-time-trackers.html) (clever play on words there). Jack Nicas in NYT. Anecdotally, I have friends who've worked at app companies around the time AAPL 'launched the feature in house' or acquired a competitor. The approval process gets a lot harder.

And it's fine -- companies are supposed to look out for their own pocket. If platforms exist by offering their partners a deal with the devil, then by inference competent platforms will **become** the devil in order to sustain their business. That's okay, but everyone that does business with / on them seems to get burned.

I like the Tim Cook 'if you're not the product you're the customer' line. For platform integrators I absolutely believe it. Facebook Connect integrators aren't paying for the privilege. FB likes having their shitty PHP on more sites and oauth logins incentivize that, but if it were strategic to charge money for this they would have done so by now. Having a fiduciary obligation to anyone would pollute FB's DNA.

## Uber discovers there's always a bigger fish

I love Uber because of how quickly they turned on everybody. Consumer privacy stuff with God Mode, employee welfare with the Susan Fowler stuff[^susanjfowler] (it started on her first day). And the drivers, of course.

[^susanjfowler]: [Reflecting on one very, very strange year at Uber](https://www.susanjfowler.com/blog/2017/2/19/reflecting-on-one-very-strange-year-at-uber) Susan Fowler

For a brief moment when Uber was new they had the best consumers in the taxi businesses and were able to offer real income to gig workers. The drivers didn't realize that Uber is a platform and as soon as it had all the drivers it wanted, would start treating them badly. They're not partnering with Uber -- they're the product Uber sells.

This manifested as steady price pressure. It's difficult to get accurate information on hourly rates[^mit-study], but: Uber's take on UberX rides went up, from 15 to 20%[^from-15-to-20] and then to 25 in some cities[^from-20-to-25]. They pulled some kind of accounting snafu which improperly calculated commissions and may have illegally charged some payroll-esque taxes to drivers[^tax-scam].

[^mit-study]: [Uber, Lyft Drivers Earning A Median Profit of $3.37 Per Hour](https://www.npr.org/sections/thetwo-way/2018/03/02/590168381/uber-lyft-drivers-earning-a-median-profit-of-3-37-per-hour-study-says) James Doubek in NPR. I'm not citing this for the hourly wage stimate but for the link to Uber's challenge of the methodology. Let me say that it's **totally bananas** for an economist who works at Uber to challenge the methods rather than just revealing the answer from the data in his possession. I don't know anything about the professional ethics of economists but this seems fishy.

[^from-15-to-20]: [UberX drivers protest commission increase](https://www.sfchronicle.com/business/article/UberX-drivers-protest-commission-increase-5464114.php) Thomas Lee in SF Chronicle

[^from-20-to-25]: [Uber Raises UberX Commission To 25 Percent In Five More Markets](https://www.forbes.com/sites/ellenhuet/2015/09/11/uber-raises-uberx-commission-to-25-percent-in-five-more-markets/) Ellen Huet in Forbes

[^tax-scam]: [Uber to Repay Millions to Drivers, Who Could Be Owed Far More](https://www.nytimes.com/2017/05/23/business/economy/uber-drivers-tax.html) Noam Scheiber in NYT

A shakier source claims that 'upfront pricing' rides pay drivers less than half of sticker of some rides[^upfront] and that Uber is raising their take on the per-mile rate in some cities[^mile-take]. A historical rate tool shows per-mile rates decreasing in NYC[^historical-rates], which drivers probably see as them loaning Uber money to fund its war with Lyft. (Doubly frustrating because they all drive for both platforms).

[^upfront]: [The Case Against Upfront Pricing](https://therideshareguy.com/the-case-against-upfront-pricing/) The Rideshare Guy (not sure this is a legit source but the chief economist of uber cites them [here](https://medium.com/uber-under-the-hood/an-analysis-of-ceeprs-paper-on-the-economics-of-ride-hailing-1c8bfbf1081d) to it might be)
[^mile-take]: [Uber Raising Rates For Riders But Not Drivers](https://therideshareguy.com/uber-raising-rates-for-riders-but-not-drivers/) The Rideshare Guy
[^historical-rates]: [New York City Uber Prices & Historical Rates](http://uberestimate.com/prices/New-York-City/all/) uberestimate.com

But oh karma is a bitch. It's 2019 and every government in the world (local or otherwise) has it in for Uber. They were either out-competed, out-walleted or plain forced out of Russia and China (I've heard all three versions; people say Didi made more sense to Chinese users).

They nearly got indicted for obstruction of justice from using their Ripley tool during a tax raid in Canada[^ripley] ('nuke the entire site from orbit'). And 'greyballing' city employees in California probably played a role in the state making their drivers into employees, which hurts margins. Other states copied them. Italy kicked them out entirely[^italy].

[^ripley]: [Uber developed secret system to lock down staff computers in a police raid](https://www.theguardian.com/technology/2018/jan/11/uber-developed-secret-system-to-lock-down-staff-computers-in-a-police-raid) Olivia Solon in The Guardian. They never faced the obstruction charge and complied layer with a more specific warrant. [Uber’s Secret Tool for Keeping the Cops in the Dark](https://www.bloomberg.com/news/articles/2018-01-11/uber-s-secret-tool-for-keeping-the-cops-in-the-dark) Zaleski et al in Bloomberg.
[^italy]: [Uber: Which countries have banned the controversial taxi app](https://www.independent.co.uk/travel/news-and-advice/uber-ban-countries-where-world-taxi-app-europe-taxi-us-states-china-asia-legal-a7707436.html) Anna Rhodes in The Independent

It's not all bad. They're allowed back in Austin[^austin] and London[^london], the latter having declared them 'fit and proper' to operate a car service. My point is that government is basically a platform from Uber's perspective, able to act to protect its 'users' but also to protect infant industries or to avenge a grudge. And every interaction with a government leaves Uber worse for wear.

[^austin]: [Texas legislature overrules Austin, allows Uber and Lyft to return](https://www.engadget.com/2017/05/25/texas-legislature-overrules-austin-allows-uber-and-lyft-to-retu/) David Lumb in Engadget
[^london]: [Uber survives legal challenge brought by London cabbies](https://www.theguardian.com/technology/2019/feb/26/uber-survives-legal-challenge-london-black-cab-drivers) Gwyn Topham in The Guardian

## "ceise and desist or whatever thefuck that is"

It's not just taxi drivers and sleek slander startups who are exposed to platform risk. Singer-songwriters and movie studios are in the same boat because they're not in control of their distribution anymore -- they rely on streaming platforms to get seen.

Three takes on streaming and music:

* Streaming ended music piracy
* Streaming sites *are* pirates who are using legal pressure to rip off artists
* They embarrass Taylor Swift superfans[^superfan] (only one person is saying this).

[^superfan]:
	Hey, celebrities are platforms too -- an agglomeration of consumers deployed for business purposes. [Taylor Swift Pulled Music From Spotify for ‘Superfan Who Wants to Invest,’ Says Rep](https://www.rollingstone.com/music/music-news/taylor-swift-pulled-music-from-spotify-for-superfan-who-wants-to-invest-says-rep-164557/) Steve Knopper in Rolling Stone.
	> “We never wanted to embarrass a fan,” says Scott Borchetta, president of Big Machine Label Group, in a radio interview with Motley Crue’s Nikki Sixx, of all people. “If this fan went and purchased the record, CD, iTunes, wherever, and then their friends go, ‘why did you pay for it? It’s free on Spotify,’ we’re being completely disrespectful to that superfan.”

	Craaaazy. She smacked AAPL pretty hard too.

The 'spotify ended music piracy' argument is an interesting one with two sides. Polling in England suggests piracy is down[^yougov-piracy] (or at least fewer people are admitting it). An IFPI report says it's still high[^ifpi-report]. People using ad-blockers on Spotify are arguably using the platform for piracy[^premium-piracy].

[^yougov-piracy]: [Music piracy fallen dramatically over last five years thanks to streaming services such as Spotify and Tidal, survey reveals](https://www.independent.co.uk/arts-entertainment/music/news/music-piracy-uk-spotify-tidal-streaming-services-yougov-survey-a8474436.html) Jack Shepherd in The Independent
[^ifpi-report]: [One-Third of the World Is Still Pirating Music](https://www.rollingstone.com/music/music-news/streaming-music-piracy-copyright-stealing-734293) Amy X. Wang in Rolling Stone
[^premium-piracy]: [Spotify, the ‘Solution to Music Piracy,’ Is Getting Pirated by 2 Million People](https://www.digitalmusicnews.com/2018/03/26/spotify-piracy-hacked/) Marsha Silve in Digital Music News

I think the piracy argument doesn't matter because rights-holders are getting paid so little by the platform[^revenue-neutral]. I'd rather get robbed by pirates than by Spotify -- pirates are cooler ('can vampires be pirates' my nephew asked me once) and also you can take legal action against them. 'Let us give it away or else people will steal it' is kind of a 'let them eat cake' argument. It misses the point.

[^revenue-neutral]: [Spotify really does reduce music piracy, but at a cost](https://www.engadget.com/2015/10/28/spotify-piracy-study/) Jon Fingas in Engadget

Also I firmly believe that streaming platforms drove down the price of all media by giving it away and then hiding behind intellectual property safe harbor provisions. There's not much difference to content owners between Napster/Kazaa at $0 and Youtube/Spotify at pennies on the dollar. Especially for indie studios who blame Youtube for 'cutting out Merlin' (their collective bargaining platform)[^merlin].

[^merlin]: [YouTube accused of trying to strong-arm indie labels into poor deals](https://www.theguardian.com/technology/2014/jun/04/youtube-independent-record-label-deals) Mark Sweney in The Guardian

I'm not saying the platforms are stealing content now (I'm not saying they're not; I don't know). But they certainly took advantage of the era of peak piracy to acquire a stable of primo content in the 2000s at a fraction of its market value under 1990s assumptions.

Viacom sued Youtube back when the world was young and argued they were wilfully blind to copyrighted material on their platform, and came up with some zany internal emails to support it:

>  they knew the site was "out of control with copyrighted material" -- including videos taken from Viacom programs they identified by name -- but they decided not to block even "the obviously copyright infringing stuff," because if they did "site traffic [would] drop to maybe 20% of what it is."[^plaintiffs-memorandum]

[^plaintiffs-memorandum]: [PLAINTIFFS’ MEMORANDUM OF LAW IN OPPOSITION TO DEFENDANTS' RENEWED MOTION FOR SUMMARY JUDGMENT](https://www.docketalarm.com/cases/New_York_Southern_District_Court/1--07-cv-02103/Viacom_International_Inc._et_al_v._Youtube_Inc._et_al/446/) Smith et al for Viacom et al in Viacom v Youtube

> one co-founder stating to the others in response to a cease and desist letter: "haha, awesome!!! a sign of our continuing success.. we're getting [sic] ceise and desist or whatever [sic] thefuck that is emails now."

(The non-quoted parts are written by plaintiff's counsel so huuuge grain of salt obviously).

And Youtube somehow got a judge to argue their case for them:

> The judge rejected what he called Viacom’s "ingenious" yet "extravagant" argument that YouTube should monitor the content of videos being uploaded at a rate of more than 24 hours of viewing time per minute.[^ingenious-yet-extravagant]

[^ingenious-yet-extravagant]: [Google, Viacom settle landmark YouTube lawsuit](https://www.reuters.com/article/us-google-viacom-lawsuit/google-viacom-settle-landmark-youtube-lawsuit-idUSBREA2H11220140318) Jonathan Stempel for Reuters. 'Terms were not disclosed. No money changed hands, a person close to the matter said.'

I.e. 'we’re much too big to regulate and our margins are too low to behave responsibly’. I.e. 'let them eat cake'.

<!-- paid content can't compete w/ free but also the free streamers didn't ask permission. They stole. Courts know what to do with napster / kazaa but they don't know what to do with a big legit company doing this brazenly in the sunshine. -->

Newspapers deal with the same problem. A guy from Vice thinks platform risk is the live-or-die problem in his industry:

> You’re giving another company your manifest destiny. Unless you are on those platforms, you’re dead, but if you are on those platforms then you’re not making money, so therein lies the rub and that’s going to be biggest challenge in media going forward.[^manifest-destiny]

[^manifest-destiny]:
	[Vice’s Shane Smith: ‘Expect a bloodbath’ in media within the next year](https://digiday.com/media/shane-smith-vice-media-interview) Jordan Valinsky in Digiday. This is from 2016 -- not sure if the bloodbath happened or not.

	He also says the most honest thing I've ever heard anyone say about Brooklyn:

	> We were a sweatshop for trustafarians, so there was a time when to live in Williamsburg or New York and to work at Vice, there’s no money in it

## Empecemos lento, después salvaje

Margrethe Vestager was just a mild-mannered Danish cabinet secretary until she was bitten by a radioactive spider and became EU commissioner for competition. From the outside, it looks like she's made it her job to punish the American platforms for anticompetitive behavior (and sometimes just for existing). The EU fined Google 2.4 billion euro in 2017[^fine-2017] and 4+ billion euro the year after[^fine-2018]. Yes, with a B.

[^fine-2017]: [Google Fined Record $2.7 Billion in E.U. Antitrust Ruling](https://www.nytimes.com/2017/06/27/technology/eu-google-fine.html) Mark Scott in NYT
[^fine-2018]: [E.U. Fines Google $5.1 Billion in Android Antitrust Case](https://www.nytimes.com/2018/07/18/technology/google-eu-android-fine.html) Satariano & Nicas in NYT

But that's not the whole story: The EU's lawsuit is based on petitions from friends of the little people like review website Yelp, java patent troll[^java-troll] Oracle, and victim of unfair and incompetent phone hacking accusations[^unfair-phone] News Corp.

[^java-troll]: [Oracle America, Inc. v. Google, Inc.](https://en.wikipedia.org/wiki/Oracle_America,_Inc._v._Google,_Inc.) Wikipedia
[^unfair-phone]: [News International phone hacking scandal](https://en.wikipedia.org/wiki/News_International_phone_hacking_scandal) Wikipedia

This is funny to me because Yelp is also a platform. They charge for access to their eyeballs in the form of paid placement, but they also allegedly charge for not setting fire to your restaurant, i.e. not surfacing bad reviews[^pretty-nice-place-you-got-there]. Anecdotally, I've spoken to friends in the restaurant business who believe this accusation.

[^pretty-nice-place-you-got-there]:
	[Yelp's servings could use a dash of candor](https://www.latimes.com/archives/la-xpm-2009-feb-11-fi-lazarus11-story.html) David Lazarus in The LA Times
	> But is Yelp also a shakedown racket for merchants? Some restaurant owners say the San Francisco company is unusually aggressive in trying to get businesses to pay hundreds of dollars in monthly "sponsorship" fees to improve their ranking in search results and to move their most positive review to the top of the page

So will Europe defend us small folk against the evil platforms? The suits so far have been against G for anticompetitive behavior i.e. for hurting other businesses. On the content side, the EU is developing something called Article 13 (published as Article 17 I think).

The head of Youtube warned humanity just how dangerous this law might be in her blog last year:

> Take the global music hit “Despacito”. ... some of the rights holders remain unknown. That uncertainty means we might have to block videos like this to avoid liability under article 13. Multiply that risk with the scale of YouTube, where more than 400 hours of video are uploaded every minute, and the potential liabilities could be so large that no company could take on such a financial risk.[^empecemos-lente-despues-salvaje]

[^empecemos-lente-despues-salvaje]: [The Potential Unintended Consequences of Article 13](https://youtube-creators.googleblog.com/2018/11/i-support-goals-of-article-13-i-also.html) Susan Wojcicki for the YouTube Creator Blog

Sound familiar? It should. They got that judge to say it in 2010.

She claims Content ID is the best you can do on this kind of platform and I agree, but that means we need to reexamine as a society what copyright means. If you can sell ads against something without being responsible for piracy, you're basically empowered to rob a bank.

My prediction is that copyright law will weaken in careful and deliberate ways. That outcome isn't great for YT -- more realistic laws will make it easier for small players to launch similar products. Their best bet is likely to remain in a legal gray area for as long as possible, but Europe is making that pret-ty expensive.

But my main point: it's a scary time to try to monetize content unless you own the distribution. That's probably the reason Amazon and Netflix are producing content at the rate they are -- as prominent distribution platforms with captive eyeballs, they're equipped to see their content priced fairly in the marketplace.

## Investment advice & assignment of blame

Who's to blame?

Consumers, of course, who have never looked a gift horse in the mouth, are pretty content to receive stolen goods, and don't care who makes their shoes as long as they're cheap. We're still not sure we're upset by what FB is doing to us. We certainly appreciate our cheap cabs and free videos.

I think regulators are so far behind the curve on this. There's the Lina Khan article from forever ago which says Amazon is a new breed of monopoly[^new-breed]. Antitrust law, already defanged, has no idea what to do about it.

[^new-breed]:
	[Amazon's Antitrust Paradox](https://www.yalelawjournal.org/note/amazons-antitrust-paradox) Lina Khan at Yale
	> the current framework in antitrust—specifically its pegging competition to “consumer welfare,” defined as short-term price effects—is unequipped to capture the architecture of market power in the modern economy

I think the only way out of the hole we're in is for a new breed of companies to refuse to touch the platform ecosystem at all and to offer consumers a more expensive but ethical or healthy product -- what granola was in the 80s.

My main point is this: you're never going to get big building on top of someone else's platform. Nobody does. They're going to pull the rug out from under you. Don't invest in companies with platform risk, don't work at them if you can avoid it, and stop starting them.

## Sources
{:.no_toc}
