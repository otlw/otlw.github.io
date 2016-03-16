---
layout: post-no-feature
title: Lightpaper
description: A decentralized system of assessment.
---
The foundation of any educational institution is its assessment system. This defines what it values, promotes, and propagates. In turn an educational system forms the foundation of a society, defining what its citizens value, promote, and create. Our current dependence, then, on standardized assessments is disturbing yet necessary.

We need ways to measure an individual’s abilities and achievements. If one cannot prove they have learned they cannot operate on that learning with others and move forward. So students are forced to use the limited standardized assessments valued by society, assessments that encourage poor pedagogical practices and restriction of independent learning while putting incredible stress on teachers and institutions both in creation and maintenance of their integrity.  So while these test may currently be necessary it’s clear their continued use is unsustainable.


Overview
---------------------
As an alternative we propose an abstracted system of assessment based on randomized peer consensus and built on [Ethereum](https://ethereum.org/). Instead of focusing on single hard-to-make easy-to-break assessments we leverage multiple, smaller, peer created microassessments of user defined tasks.

To counteract the quality difference in a peer-assessment versus a professional assessment we randomly assemble a panel of users who have previously demonstrated achievement in the task at hand. These assessors, with no knowledge of each other, must design and administer their own microassessment to gain an understanding of the assessee’s ability. This could range from proof that objects have been constructed to a demonstration of mathematical ability. Based on this microassessment they then decide whether the user passess, and if so assigns them a numerical score.

The decisions of all the assessors is collated into one final score. Based on statistical analysis we can determine which assessments contributed most heavily to the variation, or noise, in the score, and by this measure, determine their accuracy. In this way we can reward assessors based on their accuracy in relation to each other. Importantly, because they cannot communicate, they must attempt to be as accurate as possible in order to match their peers and get the biggest reward.

The reward in question is a currency (“tokens”) that users pay to initiate assessments. The only method users have to gain these tokens is this accurate assessment so in order to participate as students, users must also participate as good assessors. And conversely in order to assess you must have records in this system. By this incentive the system forms a loop that ensures a constant supply of assessors for students wanting to categorize their skills.

Technical Structure
-------------------
To fully utilize this growth the system needs to be structured relationally. We do this via hierarchies. An assessment belongs to a single "tag"; a smart contract with an arbitrary description which can have multiple other tags as parents. These tags store a database of users who have earned them, and hence are qualified to assess. In this way we can move up a tree, pulling first assessors with the most relevant experience.

The tag abstraction is extremely versatile, as each has no defined purpose. A tag doesn't have to be a concept or a piece of knowledge, it can serve as a rule set or a modifier. Essentially any goal a user might have can be described through tag dependencies.

Why this works
-----------------
This system functions because we can depend on people to be self-centered. Everything costs tokens, from starting assessments as mentioned before, to creating new tags, which are earned through actual labor. This discourages system abuse because every action can only occur through your own work.

We also tie our payout system to consensus. So you don't get "paid" if you're right, you get "paid" if you're the same. So you are under a strong economic incentive to do the thing everyone would do. And so if a culture of doing the right thing is incentivized initially, doing the **right** thing will become doing the **common** thing.

Each assessor must also agree to assess when requested. This means assessors unsure of their own ability in a specific area will decline those assessments, as they would stand to be punished for inaccuracy

Future
-----------------
We believe this system offers several fundamental advantages to our current systems of assessment. Most importantly it makes no assumptions. It functions to fulfill the needs of students, not create a need to be filled. It encourages people to create and maintain their own standards, and discourages dependence on centralized bodies.

Above all we’re trying to a create a new universal culture and community of education. Anyone should have access to the means to prove their labor and achievements and interact globally.  
