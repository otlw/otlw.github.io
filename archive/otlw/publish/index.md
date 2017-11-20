---
layout: main-page
title: A decentralized document management and micropayment framework
---

otlw-publish is a system of smart contract for managing documents and their sources. It also facilitates the distribution of micropayments through the networks of sources. This can be leveraged to represent any document relationship that has sources or dependencies, for example academic papers, or even blog posts and replies. It can be used for any form of media as it simple stores IPFS hashes.

# The Document contract

This is the only contract necessary for the network. It maintains the data related to a document, its sources, and the weight of those sources, which determines how much of a share they get of any payments sent. The really neat part is how you can create networks of these documents managed by central contracts that enforce certain principles on them to create distinct systems. For example...

# The forum contract

The forum contract creates and manages networks of document contracts to represent a forum, where people can make posts and replies. The catch is that to reply to post you have to pay a certain amount, essentially acknowledging the value of the original post. We can then use the number of replies to rank posts. You can also tag posts and manage them in that fashion. This simple ruleset leads to some pretty powerful behavior


# Possible applications

This document contract could be used to represent all sorts of relationships, from academic papers and their sources, to the contributors to a work of fiction, to the actors involved in a movie production. Its small and simple. It is limited in the sense that it can't limit data consumption or release things upon payments, but it can restrict rights to add and modify relationships.
