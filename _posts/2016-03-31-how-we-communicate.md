---
layout: post-no-feature
title: "How We're Handling Communication"
category: articles
tags: [ethereum, social, dapps, IPFS, communication, development]
---
This'll be a pretty short one. Any communication is going to be an absolute nightmare to make. Even integrating an existing platform with our application would bring on a huge new set of problems, and would probably not even fit our use case perfectly.

But communication is an integral part of our assessment process. The assessed must be able to clearly put forward their goals, and provide evidence to their assessors. Likewise the assessors must clearly be able to communicate their expectations and tasks. We can’t make any assumptions about the kind of medium necessary, nor the parameters of the conversation, like the number or people, or response speed, or anything really.

So basically, we’re just not going to deal with that at the start.


Instead
------------------------
We’re going to pass [IPFS](https://ipfs.io/) hashes back and forth. If you don’t yet know IPFS, it's essentially a decentralized datastore accessed through file hashes and so provides us a reliable way to pass arbitrary data back and forth. And because it is immutable, and we’ll be storing this all publicly, it provides a good concrete way to have a long term testament to which communications occurred.

So assessors and the assessed could conceivably pass back and forth any kind of data, text documents, videos, audio, or even instructions to use some other medium, such as contact details, or links to a chatroom, anything really. It could be from a  text document with instructions, to several links, to specific standard documents with an explanatory video.

Isn’t that dangerous?
------------------------------
Well yes, if they can communicate arbitrarily there’s no reason to stop bribes, threats, or all sorts of other shady behaviors going down. But we will still have a public record of this. So what will emerge is a public standard for what constitutes an appropriate interaction.

These kind of supporting media and tools already exist and we hope to encourage their integration and development. For example something like the existing [Open Badges](http://openbadges.org/) community is a perfect spring board for standards.

There could even be a Tag that constitutes this standard. Or even multiple tags for multiple standards. And because all the data is in the public eye, auditing becomes significantly easier. This ties back to my other post, [Building for Social](http://otlw.co/articles/building-for-social), in that we want to see, and will help, the community develop new meanings for tags, and for the interactions that are going to occur.
