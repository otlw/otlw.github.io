---
layout: page
title: A decentralized system of assessment
home: /assess
---
A decentralized assessment platform enables the assessment of items based on the consensus of qualified individuals. It is a way to prove things are valid using people who have been proven (by the system) to know what they’re talking about. Peers are motivated both to be assessed and to be assessors, and are incentivized to be as accurate as possible.

# Overview

We randomly assemble a panel of users who have previously demonstrated achievement in the task at hand. These assessors, with no knowledge of each other, agree to provide an assessment based on information provided by the assesee. This assessment could range from proof that objects have been constructed to a demonstration of mathematical ability.

The inputs of all the assessors are given in the form of a signed numerical scores. We then cluster these scores based on their distance from one and other, accepting the largest cluster as the most accurate. In this way we can reward or punish assessors based on their distance in relation to that cluster. Assessors also get a higher reward if there are more individuals outside of the largest cluster, which means they can never guarantee their peers won't try and double cross them.  

# The Token

The reward in question here is a token that users can spend to initiate assessments. At least initially, tokens will not be tradable which means the only method users have to earn them is assessing. Conversely in order to assess you must have records on the platform.

This forms loop that ensures a constant supply of assessors and assessees earning and spending tokens.

# Organizing and relating assessments

To know when to call assessors we need to have an understanding of the relationships between different assessments and skills. We do this via hierarchies.

An assessment belongs to a single "tag"; a smart contract with an arbitrary description which can have multiple other tags as parents. These tags store a database of users who have earned them, and hence are qualified to assess. In this way we can move up a tree, pulling first assessors with the most relevant experience.

The tag abstraction is extremely versatile, as each has no defined purpose. A tag doesn't have to be a concept or a piece of knowledge, it can serve as a rule set or a modifier. Essentially any goal a user might have can be described through tag dependencies.

# Why this is necessary

The foundation of any educational institution is its assessment system. This defines what it values, promotes, and propagates. In turn an educational system forms the foundation of a society, defining what its citizens value, promote, and create. Our current dependence, then, on standardized assessments is disturbing yet necessary.

We need ways to measure an individual’s abilities and achievements. If one cannot prove they have learned they cannot operate on that learning with others and move forward. So students are forced to use the limited standardized assessments valued by society, assessments that encourage poor pedagogical practices and restriction of independent learning while putting incredible stress on teachers and institutions both in creation and maintenance of their integrity.  So while these test may currently be necessary it’s clear their continued use is unsustainable.

# Looking forward

We believe this system offers several fundamental advantages to these current systems of assessment. Most importantly it makes no assumptions. It functions to fulfill the needs of students, not to create a need to be filled. It encourages people to create and maintain their own standards, and discourages dependence on centralized bodies.

Above all we’re trying to a create a new universal culture and community of education. Anyone should have access to the means to prove their labor and achievements and interact globally.  
