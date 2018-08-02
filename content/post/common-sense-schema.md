+++
title = "The Elusiveness of a Schema for Common Sense"
date = 2018-07-07T19:24:31-04:00
draft = true
summary = "Graphs, logics, vectors, frames, tables... the inadequacy of these and a zoo of other schemas in representing common sense. And an application to role-playing games."
# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = []
categories = []

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
# Use `caption` to display an image caption.
#   Markdown linking is allowed, e.g. `caption = "[Image credit](http://example.org)"`.
# Set `preview` to `false` to disable the thumbnail in listings.
[header]
image = ""
caption = ""
preview = true

+++

The Elder Scrolls V: Skyrim is my favorite role-playing video game. It was a fantastic, immersive experience except for one sore point: the non-player characters (NPCs). The designers created a graphically beautiful and lore-rich world, inhabited by finite state machines.

> The designers created a graphically beautiful and lore-rich world, inhabited by finite state machines.
---

If you're role playing as a manic Nord who kills every villager in sight, the state machine design is fine. But as soon as you try to talk to an NPC the immersion falls apart (you select dialog lines from a pre-defined list at each turn).

I developed an idea that sits in my journal under "NPC manifesto" from 2014. The first part is using speech recognition and text-to-speech instead of multiple choice. But that creates a problem: how do NPCs respond to arbitrary text? This is the crux of the idea.

I wanted to represent each NPC as a set of several things: (1) a personality vector (think word2vec), (2) a vernacular embedding, and (3) a subscription to various databases. The databases would chiefly be semantic nets (e.g. 3-tuples of entity-relation-entity), with some things stored in a relational database (e.g. date of birth). Neo4j, OrientDB, or other graph databases that allow you to mix properties and relations would be a good fit for this. The game would have several KBs. There'd be a interpersonal relation KB, a temporally-coded KB of events (e.g. a lore), and specialty knowledge (e.g. crafting materials). As an aside: perhaps a temporal graph database could simplify this structure. I thought I'd cracked NPCs - or at least had the right design such that a team of writers, engineers, and artists could make believable characters under the framework. I considered building it as a middleware and marketing it as a "personality engine" for games ([related paper](https://www.researchgate.net/publication/262150526_GAMYGDALA_An_emotion_engine_for_games)).

What if the player asks an NPC, "Why can Dragons fly"? The system queries the knowledge graph and retrieves the tuple <dragons, can fly because they have, wings>. Then the NLG systems realizes this into a coherent sentence and delivers it to the player.

Now the player asks, "But what is it about wings that allow an entity to fly". Maybe, as virtual assistants do, the system grabs a span from Wikipedia on how wings work. It then uses the vernacular vector to "translate" the span and have the NPC speak it.

But what if the player asks, "Shall I attempt to slay the dragon with my dagger"? This requires an understanding, among many other things, that (1) a dagger is a melee weapon, (2) the dragon can fly, which entails (3) a melee weapon is not an appropriate choice because the dragon can just fly away. In other words, this requires an understanding of intuitive physics.

How do we represent intuitive physics?
