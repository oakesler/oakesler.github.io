---
layout: post
title:      "WokeApp from Start to Finish"
date:       2019-12-04 14:52:53 -0500
permalink:  wokeapp_from_start_to_finish
---


**Embark**
WokeApp was conceived as a means to access social justice and humanitarian news items.  It takes four sources - The American Civil Liberties Union (ACLU), Amnesty International, Human Rights Watch, and The Southern Poverty Law Center - and returns a headlining story from each.  Users can view the array of headlines, reveal a specific abstract, and continue to the actual website. 

I designed WokeApp as an answer to my own need for a specific type of news.  While tools exist (Google News) to help with story/source filtration, accessing saved searches requires known devices/login credentials. Furthermore, search engine results tend to be overly textual and visually overstimulating. Interested people like me - with very little time - could benefit from WokeApp. But what about people unlike me? Wouldn’t it be ideal if the program could cater to them?  Could WokeApp be a quick, painless access point for the completely, even passionately uninterested?

**Elevation**
As WokeApp progressed, I realized its utility might extend beyond mimicking a Google search.  We consume news faster and in greater quantities than ever before; the reader of 2020 has an increasingly selective appetite for his or her specific taste in current events. The standard news app in Apple iOS learns what the user reads and doesn’t read--and when the algorithm fails, you can manually approve and reject news pieces.  Upside: people are more informed than ever.  Downside: the scope of what media reaches a reader is increasingly streamlined.

Humanitarian/human rights news has a tendency towards marginalization.  Perhaps some find it to be less important than political or financial news, or the stories/graphics are too overwhelming.  Others may not feel familiar with the subject matter.  However this lack of conscientiousness starts, it *is* ignorance; consequently, there is an objective need: getting more people aware of social justice news.  

**Expectation**
Thus, WokeApp’s approach begins at the intersection of everyday utility and basic advertising.  By offering simple, comparative, digest-in-a-glance information, a (closed) window of interest and curiosity opens.  The program’s focal point is really it’s simplest: the instant display of four issues from four top social justice groups.  Users aren’t overwhelmed with multiple windows, graphics, or lengthy text.  Less is more.

Even the user disengaging immediately post-headline has become aware of four different aspects of current human rights--without even reading the articles.  The utility of this minimal awareness - at work, school, in daily conversation - may lead to another WokeApp visit.  Before you know it, he or she is reading a piece’s abstract--after all, it’s super brief and one command away.  And if the paragraph piques his/her interest...the URL is right there below its last sentence.  That same, initially uninterested reader is now exploring ACLU.org.

**Engineering**
Devising the architecture of WokeApp's CLI started exactly how Avi Flombaum advises; writing down a (literal) logical flow of the program and using it as "scaffolding" for the actual code.  I knew I wanted my program to open to an zen, uncluttered menu.  The first option would return four headlines.  I didn't want the headline spread to automatically generate--when users have the opportunity to make a choice and stimulate a reaction based off that choice, they are less likely to feel overwhelmed by what is automatically popping up in front of them.  Ideally, users of this app are genuinely curious to begin with— if they are not, perhaps making selections to view unseen material will stoke that interest.  

I knew each headline should hold deeper layers--in WokeApp's case, an article abstract and URL.  In lieu of a text-and-hyperlink assault, users remain in control of how far they explore.

WokeApp's coded architecture is similarly based off this notion of simplicity.  The program is centered on four "story" objects.  Each object is populated with the data from twelve precise scrapes.  The bin file performs the scrapes upon initialization.  The program then commences by greeting the user with an interface offering the options of a) an array of headlines or b) generation of a random story.  Since the scrapes have already been performed, displaying the scraped data became a matter of responding to user input and encapsulating that code as efficiently as possible.  

**Encumbrances**
Not surprisingly, the most challenging aspect of creating WokeApp was scraping four quasi-disparate websites. More than one site used advanced JavaScript pagination techniques (an example is the cool, element-specific movements some websites employ as you scroll through a page.)  Furthermore, scraping from four distinct sites also entails messier code.  For instance, ideally one method would satisfy generating a url for all objects.  With this program, however, each "story" object required separate 3-5 line methods to generate a headline, abstract, and URL.  For such a simple program, I ended up with a relatively large amount of code.  

The silver lining was evaluating - and reevaluating - WokeApp's organization very mindfully, which was an excellent learning exercise.  Due to the fragile nature of scraping, I am able to “repair” a broken scrape quite easily--the method that gathers that data would be called “[source]_url_scraper” in my file, thus isolating the pertinent code is as simple as finding that method.  As an actual working program, each scrape would need to be checked at least once a day before users were depending on the app (these websites typically change every 1-3 days.)  

I also chose to place the code for creating story objects in a separate file--this made it easy to isolate changes or vulnerabilities in how the “stories” were being constructed.  For instance, in the future, if including page views became a crucial piece of information I wanted to offer users, it would be easy to add a “page_views” property to each story object.  

**Elegance**
Another benefit to this exercise was familiarizing myself with the character/spacing usage that lends itself to graceful - and gracious - presentation.  In completing the final rounds of WokeApp’s testing, I noticed how my use of asterisks to separate consecutive lines made the interface look cluttered and overwhelming.  Replacing most of these sequences with blank space streamlined the presented material.  Even accounting for blank space between user input and the consequent text increased interface readability.
Coding an app with lots of scraping drew my attention to the execution times of different processes.  Bottom line: scraping can be slow.  My program improved dramatically when I changed the bin file to execute the scrapes upon initialization (instead of segmentally as requested by the user.)  Directing attention towards time efficiency (an important part of the “Algorithms” module in the Computer Science component of this course!) had the additional benefit of, simply put, caring about the user’s experience!  I made sure to program a recursive method that receives unrecognized input and provides (polite!) redirection to a menu of options.  I also made sure to encourage feedback as the user exits WokeApp by listing an email address.

**End**
Completing my scraper portfolio project was educational in so many ways. I heightened my impressions of efficient coding, elegant interfacing, and engineering cleanly *around* an actual need (rather than a desired need.)  I hope you enjoy using WokeApp as much as I did making it.


