---
layout: post-no-feature
title: Lightpaper
description: A decentralized system of assessment.
---
The foundation of any educational institution is its assessment system. This defines what it values, promotes, and propagates. In turn an educational system forms the foundation of a society, defining what its citizens value, promote, and create. Our current dependence, then, on standardized assessments is quite disturbing.

We need ways to measure an individual's abilities and achievements. If one cannot prove they have learned they cannot operate on that learning with others and move forward. So students are forced to use the limited standardized assessments valued by society, the same assessments that encourage poor learning practices and restriction of independent learning. At the same time, these test put incredible stresses on teachers and institutions both in their creation and the maintenance of their integrity. This system is costly and ineffective, and in its broad operation limits development. 


Overview
---------------------
As an alternative we propose an abstracted system of assessment based on randomized peer consensus and built on [Ethereum](https://ethereum.org/). Instead of focusing on single hard-to-make easy-to-break assessments we leverage multiple smaller, peer created, microassessments of user defined tasks.

To counteract the quality difference in a peer-assessment versus a professional assessment we randomly assemble a panel of users who have previously demonstrated achievement in the task at hand. These assessors, with no knowledge of each other, must design and administer their own microassessment to gain an understanding of the assessee’s ability. This could range from proof that objects have been constructed to a demonstration of mathematical ability. Based on this microassessment they then decide whether the user passess, and if so assigns them a numerical score.

The decisions of all the assessors is collated into one final score. Based on statistical analysis we can determine which assessments contributed most heavily to the variation, or noise, in the score, and by this measure, determine their accuracy. In this way we can reward assessors based on their accuracy in relation to each other. Importantly, because they cannot communicate, they must attempt to be as accurate as possible in order to match their peers and get the biggest reward.

That reward is tokens, tokens that can be used to initiate assessments. This means that anyone who wants to participate in the system cannot play only one role, in order to prove their own knowledge, they must help prove others. And conversely in order to assess, you must have already have records in the system. This creates a loop by which the whole system grows in power and ability.

Technical Structure
-------------------
To fully utilize this growth the system needs to be structured relationally. We do this through a system of hierarchies. An assessment belongs to a single "tag", which is just a smart contract with an arbitrary description, which can have multiple other tags as its parents. These tags store a database of users who have earned them, and hence are qualified to assess. In this way we can move up a tree when calling assessors, pulling first the ones with most relevant experience.

The tag abstraction is extremely versatile, as they have no defined purpose. A tag doesn't have to be a concept or a piece of knowledge, it can serve as a rule set, or a modifier. Essentially any goal a user might have can be described as through tag dependencies.

Why this works
-----------------
This system functions because we can depend on people to be self-centered. Everything costs tokens, from starting assessments as mentioned before, to creating new tags,which are earned through actual labor. This discourages system abuse, for every action can only occur with your own work.

We also tie our payout system to consensus. So you don't get "paid" if you're right, you get "paid" if you're the same. So you are under a strong economic incentive to do the thing everyone would do. And so if a culture of doing the right thing is incentivized initially, doing the **right** thing will become doing the **common** thing.
