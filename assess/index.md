---
layout: main-page
title: A universal system of assessment
---

otlw-assess is a network based system of assessment. It forms a universal layer capable of assessing any quantifiable goal through _[schelling point](https://en.wikipedia.org/wiki/Focal_point_(game_theory)) assessment_, where multiple qualified assessors attempt to arrive at a result as close to each other as possible in order to be rewarded with tokens, which can then be used to initiate assessments of their own goals in turn.

The network is completely decentralized and robust, making as few assumptions as possible about assessors, assessments, or goals.

# Overview
The process works by randomly assembling a panel of users who have previously demonstrated achievement in the task at hand. These assessors, with no knowledge of each other, agree to provide an assessment based on information provided by the assesee. This assessment could range from proof that objects have been constructed to a demonstration of mathematical ability.

The inputs of all the assessors are given in the form of a signed numerical scores. We then cluster these scores based on their distance from one and other, accepting the largest cluster as the most accurate. In this way we can reward or punish assessors based on their distance in relation to that cluster. Assessors also get a higher reward if there are more individuals outside of the largest cluster, which means they can never guarantee their peers won't try and double cross them.  

# The Token

The reward in question here is a token that users can spend to initiate assessments. Tokens are generated through assessments and spent on creating assessments, forming a loop that ensures a constant supply of assessors and assessees within the system.

# Organizing and relating assessments

To know when to call assessors we need to have an understanding of the relationships between different assessments and skills.

An assessment belongs to a single "concept"; a smart contract with an arbitrary description which can have multiple other concepts as parents. A parent is any concept more general than the child, building up a **hierarchal ontology** organizing concepts. These concepts store a database of users who have earned them, and hence are qualified to assess. In this way we can move up a tree, pulling first assessors with the most relevant experience, and later those with a weaker relationships.

The concept abstraction is extremely versatile, as each has no defined purpose. A concept doesn't have to be a concept or a piece of knowledge, it can serve as a rule set or a modifier. Essentially any goal a user might have can be described through concept dependencies.

# Why this is necessary

The foundation of any educational institution is its assessment system. This defines what it values, promotes, and propagates. In turn an educational system forms the foundation of a society, defining what its citizens value, promote, and create. Our current dependence, then, on standardized assessments is disturbing yet necessary.

We need ways to measure an individual’s abilities and achievements. If one cannot prove they have learned they cannot operate on that learning with others and move forward. So students are forced to use the limited standardized assessments valued by society, assessments that encourage poor pedagogical practices and restriction of independent learning while putting incredible stress on teachers and institutions both in creation and maintenance of their integrity.  So while these test may currently be necessary it’s clear their continued use is unsustainable.

# Looking forward

We believe this system offers several fundamental advantages to these current systems of assessment. Most importantly it makes no assumptions. It functions to fulfill the needs of students, not to create a need to be filled. It encourages people to create and maintain their own standards, and discourages dependence on centralized bodies.

Above all we’re trying to a create a new universal culture and community of education. Anyone should have access to the means to prove their labor and achievements and interact globally.  

This is a live document and is a work in progress, so any suggestions or questions can be directed at **jared(at)otlw.co**
