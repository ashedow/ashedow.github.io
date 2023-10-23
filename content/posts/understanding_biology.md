---
title: "Understanding biology"
date: 2023-06-23
edited: 2023-07-08
description: ''
featured_image: ""
tags: ["#bio", "#paper", "#link"]
draft: false
---

Understanding biology. Parallels between Biology and other sciences

> [Will we ever understand biology like we currently understand physics*? My take is no (and it seems clear) but curious to hear other takes!](https://twitter.com/ArtirKel/status/1458188399328694274)
{{< tweet user="ArtirKel" id="1458188399328694274" >}}

The study of organisms looks no less complex than the study of distant space systems.

And while the study of a collection of organ systems looks like a rather pessimistic undertaking, the study of a single system looks somewhat more rosy.
At least the paper [Could a Neuroscientist Understand a Microprocessor?](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005268) seems more optimistic than the paper [Can a biologist fix a radio?—Or, what I learned while studying apoptosis](https://www.cell.com/cancer-cell/pdf/S1535-6108(02)00133-2.pdf)

On the other hand, watching the AI in Drug Discovery but not being involved in the industry I cannot be super optimistic in this direction.
We have many tools and experiments, research, papers, pre-prints ... but databases are not open

> I just like this lecture about stats https://youtu.be/hVimVzgtD6w?t=921. trash in-trash out. "we cannot give the data free to the students, free to the entrepreneurs of the world". 
{{< youtube hVimVzgtD6w >}}

It's hard to start to analyse it.
At most what is available is rare data from platforms like Kaggle, [open reaction database](https://docs.open-reaction-database.org/en/latest/), sometimes some other open data like [enamine](https://enamine.net/compound-collections/real-compounds/real-database), [chemify](https://www.chemify.io/) or a piece of data from services like drugbank.

`But even this might not be [enough to allow AI tools to reach their full potential](https://jgreener64.github.io/posts/science_the_hard_way/#fnref:blog). The best possible training sets would also include data on negative outcomes, such as reaction conditions that don’t produce desired substances. And data need to be recorded in agreed and consistent formats, which they are not at present.`

It is true that this is understandable for security reasons. 
But I would like to see something similar to "Could a Neuroscientist Understand a Microprocessor" but on drug design or gerontology. 

So, the main limitations, from my point of view, are:
* [Data](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7382642/). Data availability and quality (Will synetic data be a solution? [one](https://arxiv.org/abs/1906.05221), [two](https://arxiv.org/abs/2004.14308)); little data on structures, tissues, targets, etc.
* Cultural and ethical limitations

`“No one ever realized it until now, but here’s a strong contender for the root cause of Disease X”. And that could lead to predictions like “So that means that inhibiting this particular kinase that no one has cared about until now should be a drug for the disease”, or (more likely) "If you can find some way to interfere with this pathway over here, that would attack Disease X at a key point". That would be a very nice thing for software to tell us`

and

`So at the moment, if you took any of the AI-generated molecules from these projects and showed them to an experienced medicinal chemist, the response would be "Well, yeah, sure", and probably also "You'd better check to make sure those are actually patentable". `

`Did this computational approach speed things up, though? Wills' blog post mentions the number of compounds that the company says were actually synthesized in each of these three cases (350, 163, and 500, respectively). These are not at all out of line with what you would expect from doing a traditional fast-follower effort off of known chemical matter. It would be interesting to know if these were all synthesized from a first run of recommendations of the AI software, or if assay results were fed back in as the compounds appeared and were tested, but either way that seems to be a reasonable amount of SAR, given the fact that you're starting in well-studied chemical space. The time savings would come, though, if the software was able to direct synthesis in a way that you were sure that whatever you went to the trouble of making would also be in those areas of legally clear space.`

`So as far as I can tell, that's where we are now. But again, credit where it's due: these are early days, and it's going to be the easier problems that yield first. Right now, the AI stuff is working at the level of "Hey, here's a whole bunch of people working on Target X for Disease Y - is there any room for me in there?". That of course doesn't get at the reasons why we still have nearly a 90% failure rate overall in the clinic in this business, which are that it turns generally out that Target X really isn't that useful against Disease Y, or that our compounds directed towards it do other things that we didn't expect. Those are the harder problems
`

UPD:

[Where is generative design in drug discovery today](https://medium.com/@leowossnig/where-is-generative-design-in-drug-discovery-today-7234945177cf) article said that `Molecules that are generated today can satisfy relevant ranges for physicochemical properties like molecular weight, logP, or logD, and pass through MedChem and PAINS filters. They are selective (where needed), and progressively more examples also include experimental validation.`.

Automatic chemical design level 1 refers to a degree of ideation automation in chemical design where the machine generates ideas for molecular structures, while the chemist still provides varying amounts of guidance and retains the responsibility of final selection and assessment of the synthesisability of the molecules.

[Exploiting sand was a mistake or Physics as Information Processing ~ Chris Fields ~ 2023 QIP course](https://www.youtube.com/playlist?list=PLNm0u2n1Iwdq0UnnnnkUr446lUz00x6E7) [link](https://www.activeinference.org/education/Physics-Fields-2023)

[continually updated list of awesome-molecular-generation on GitHub](https://github.com/amorehead/awesome-molecular-generation)

[Notes on end-to-end biology](https://nintil.com/biology-llms)