---
layout: post
title: The coming IP war over facts derived from books
description: Facts are friends not food
author: Abe Winter
new: true
---

* toc
{:toc}

## Monetization of ML is N years away

We like to say that big tech has become expert at monetizing private behavioral data but I don't think that's true.

I was looking for a statement my brain remembers from google's Eric Schmidt about 'everything we do now is ML' but google search is a goldfish now and I only got recent stuff. Interestingly, it surfaced these two Schmidt statements:

* [5 years before AI is more than an advisory tool](https://xconomy.com/boston/2018/11/08/google-eric-schmidt-artificial-intelligence-machine-learning/) from 2018
* [ML will be the basis of every huge IPO in five years](https://www.techworld.com/data/eric-schmidt-machine-learning-will-be-basis-of-every-huge-ipo-in-five-years-3637206/) from 2016

He's consistent. That 5 year number isn't budging.

Are the biggest big tech companies monetizing their big datasets? I think the answer in 2020 is 'sort of', and doesn't involve particularly advanced statistics.

At amazon, even really good product recommendations aren't (I suspect) driving sales growth more than fast shipping.

For FB & G, my ML questions are:

1. Does ML improve the quality of their core offering (search for G, feed for FB)
1. Does it improve the performance of ads? (for any stakeholder)
1. Does it enable development of new things that diversify their product offering

For me, the answers are no, maybe, and no. G search has gotten worse as they've focused on recency in the index, gotten more tolerant of synonyms, and gotten less strict about quoted phrases. And no, they haven't diversified -- their core revenue stream is still ads and in G's case that income may be drying up.

The maybe is 'does ML improve ads'. There's some statistical work that goes into deciding what to show to who. The platforms use the word 'optimization' in their config dashboards. Having bought ads, but never worked on these systems internally, I suspect they're just sorting by click rate per ad per keyword.

I could believe there's some fancy clustering happening here, but I don't see AI-level stats used for categorization in a way that moves the revenue needle. Maybe I'm wrong.

I don't think this is a controversial claim; the big 5 tech companies aren't AI companies. Their continuing user traffic would be monetizable with early 00s yahoo technology -- distributed systems yes, but no advanced statistics necessary.

My point -- they're monetizing their traffic but not their data.

## Google has only one valuable proprietary dataset

Well two if you count email. I'd pay $1000 to read someone's gmail, but I don't see that happening until they're really strapped for cash.

But there's another dataset that google has proprietary access to, has been [sued for collecting](https://en.wikipedia.org/wiki/Google_books#Legal_issues), but still has running in the basement:

Google books, their scanning project which gave them access to OCR'd full text of tens of millions of books under copyight.

Books are the information that's worth money.

My mental hierarchy of information value is:

1. Actual secrets: passwords, real-time locations of things, kompromat
1. In-house operational data used to run companies or governments, including payment streams of what people are buying
1. Up-to-date expert research like janes.com or whitepapers. CRS, which is mostly open now on fas.org, is in this category. Science papers, which are still relatively closed, are here too.
1. Books
1. Wikipedia
1. Paywalled news (WSJ)
1. Non-paywalled news (huffpo)
1. Hokey free content like this blog
1. Gibberish farms like wikihow and about.com

Google today is like a library that only has the bottom three categories. Not just that, but it creates optimization loops that bid for trash like wikihow that's clearly not written by an expert. A search engine used by serious people would remove this junk from their index.

Google has access to wikipedia I guess, but wikipedia also has its own search engine.

Also, you know what wikipedia is mostly based on? Books.

If you look at the trend of NLP research and question-answering systems, it's reasonable for G to release a system that can answer questions based on information in books. At first it will let you query a specific set of books. Later it will merge facts and claims across them.

Hella useful if you're writing an essay and just need some quotes. It will be for school-age essay-writing what the calculator was for math -- a game-changer that questions our cultural expectations around this 'educational' activity.

Eventually useful for anyone who uses knowledge in any way.

Here's the problem:

## They'll claim to own the derived product

Because facts are facts, after all. A question-answering bot is a transformative work. G will claim to claim to own the expert system generated from the book, and offer zero money to the copyright owners.

This will do to non-fiction books what youtube did to music: drive down the price in ways that makes distribution only economical for low-margin platforms. It could give G a monopoly on the market and create a disincentive for production of new knowledge.

If I'd published a non-fiction book in the last 100 years I'd put $10 right now into a class action to prevent this product from hitting the market.

Google will force us to create a new format for information by removing the profitability from the existing one.

It's not like they didn't tell us they were doing this. Their mission statement was to 'free the world's information'. Small wonder they don't understand privacy. In this case we're talking about information that's protected by IP rights. When you free something that belongs to someone it's called stealing.

Stealing is evil, of course, and [evil has only been on the menu since 2018](https://gizmodo.com/google-removes-nearly-all-mentions-of-dont-be-evil-from-1826153393). So no surprise on the slow start.

## Appendix

There's a [thread about this](https://news.ycombinator.com/item?id=22301512) on HN. Arguments I liked in there:

**Publishing a summary doesn't violate copyright**.
Probably right, but publishing *every* possible summary of a book doesn't have case law and is much more like a substituitable good.
And releasing an expert system based on a book is more like 'every summary' than a single summary.

In my opinion this is like G's problem with yelp / genius infoboxes -- scraping an entire site and deterring you from clicking through.
I'm not a lawyer or an expert on IP law, so I don't know if there's case law for yelp v google on US soil.
Also [Genius watermarked their lyrics so the apostrophes read out 'red handed' in morse code](https://www.wired.com/story/what-the-google-genius-copyright-dispute-is-really-about/).

**Airbnb uses ML successfully to rank search results**. From [this comment](https://news.ycombinator.com/item?id=22304652). I think the person was trying to say that FB & G are using ML effectively, but they just posted this paper on [ML-based ranking at airbnb](https://arxiv.org/abs/1810.09591). Re-sharing here because I liked the paper, draw your own conclusions about the rest.

**Maps and street view are a valuable proprietary dataset**. (from the same comment as the airbnb paper). Yeah, maybe. I think about this a lot because maps is a product that I hate but kind of must use. I think street view is silly; a digital database of storefronts would be useful, a shitty 2.5d VR game is not useful. Is G maps better than DBs published by the government? Maybe. For streets, probably. For finding retail businesses, not sure -- if there were a city-published DB of businesses by category I'd give that a shot. I've tried to use the open street map version of G maps and never got it to work.

{% include flatpixel.html tag="books-facts-ip" %}
