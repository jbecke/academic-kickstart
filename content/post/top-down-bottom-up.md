+++
title = "Top Down or Bottom Up: Two Paradigms for Artificial General Intelligence"
date = 2018-07-26T21:07:34-04:00
draft = false
summary = "Will human-level AI emerge from a mega-neural network, a yottaFLOP, and a whole yotta data? Or will she be a pipeline system of engineered components? I think many researchers implicitly have an opinion."


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


Artificial General Intelligence (AGI, AKA strong AI, human-level AI) refers an AI that can solve any task a human can. I'm most interested in a conversational AI that is indistinguishable from a human [(Turing, 1950)](https://www.independent.co.uk/life-style/gadgets-and-tech/news/facebook-artificial-intelligence-ai-chatbot-new-language-research-openai-google-a7869706.html). Whatever you call it, there is a dichotomy in building AGI: **use one giant neural network, or use more than one.** It sounds like an implementation-specific decision, but your opinion will inform your research discipline of choice (assuming you want to build AGI).

I go back and forth on the topic and this post serves as a record of internal debate.


## An argument for bottom-up

The simplest option is a mega-neural network trained via Reinforcement Learning or Evolutionary Strategies. You'd give it a body, an environment, and let it run around and learn. With the excitement around Atari [(Minh et al., 2013)](https://arxiv.org/abs/1312.5602), Dota 2 [(OpenAI, various)](https://blog.openai.com/openai-five/), and other games, this idea seems most popular with the press [(The Independent, 2015)](https://www.independent.co.uk/life-style/gadgets-and-tech/news/facebook-artificial-intelligence-ai-chatbot-new-language-research-openai-google-a7869706.html). (A bottom-up system that suddenly becomes sentient is much more interesting than Apple over-engineering Siri for 50 years until it becomes similarly smart).

The problem is RL and ES require a metric to define success, e.g. the reward function. What should be the reward function? A naive approach would be to give it rewards for being human-like, e.g. points for using words, proper grammar, being useful, being nice, etc. This will never work because the reward function would be incredibly sparse relative to the desired actions. There are other interesting ideas like general formulas for emotions [(Moerland et al., 2018)](https://arxiv.org/abs/1705.05172), maximal compression of an adaptive compressor [(Schmidhuber, various)](http://people.idsia.ch/~juergen/creativity.html), or empowerment [(Mohamed et al., 2015)](https://arxiv.org/abs/1509.08731), and other information-theoretic ideas in "intrinsically-motivated" reinforcement learning.


## Counter points to bottom-up

The problem is bottom-up requires massive computing power. The current research task is getting a simulated agent to walk. This takes days on many computers [(Conti et al., 2017)](http://eng.uber.com/wp-content/uploads/2017/12/improving-es-arxiv.pdf). While steady improvements are being made, it's hard to see that this will lead anywhere in terms of AGI. Even if research gives an order of magnitude improvement in all metrics, where does that get the field? Maybe then the agents can walk forever, jump, ice skate, snowboard, but they'll still be as dumb as their objective function. I think we'd need a $10^3$ to $10^6$ improvement in GPU performance for this to be remotely feasible.

Perhaps the RL formalism is wrong. Perhaps there is no objective function that can create AGI.

## An argument for top-down

A top-down system uses many components which may be ML-based or symbolic. Knowledge is stored in a symbolic database, an NN, or both at different points in the system.

Modern virtual assistants like Siri use a pipeline (a specific type of top-down system):

1.  Speech-recognition to turn voice to text
2.  Intent recognition to understand what type of request you made (e.g. play music)
3.  Information extraction to determine the request specifics (e.g. you asked for Fly Me To The Moon by Frank Sinatra)
4.  Information retrieval (e.g. get latest weather, e.g. find Fly Me To The Moon in Apple Music)
5.  Natural language generation (e.g. "Now playing Fly Me To The Moon")

This allows engineers to make neural networks for the specific task. This is good because NNs are typically bad at doing multiple tasks or tasks that are not well-defined. It would be too hard to train a system to do all the tasks at once. This would require huge amounts of data and processing. A mega-NN also doesn't allow you to upgrade subcomponents (e.g. a better speech-recognition system).

Note that it is not necessary for the system to be a "pipeline", it could be a cycle, a waterfall, or whatever paradigm the project-manager wants to call it. The central idea is that there are many interacting subcomponents; it is an engineered system probably developed by a large team with many specialists.

### What research does this lead one to?

On days where I'm thinking the top-down is the best approach -- i.e. when waiting 48 hours for a P100 to finish training and wondering if a giant block of *if*'s may do the trick -- I'm lead to a certain subset of CS research. Specifically, computational linguistics, hierarchical planning, knowledge representation, database systems, supervised learning methods, computer vision, haptics, formal logic, and knowledge graph embeddings. **Together, these may be the tools needed to piece together a human.**

## Counter points to top-down

On the other hand, one could argue that no matter how many subcomponents you piece together, you'll never have true AGI. It is certainly true that our brains are not declarative, not hierarchically planned, and not separately pieced together.

Another issue is that there seem to be two prerequisites for AGI: intuitive physics and intuitive psychology [(Tenenbaum's group and others, various)](http://phys.csail.mit.edu/). Together, they form the basis for common sense. Without these two things, you'd need an impossible number of rules, e.g. "Birds can fly because they have wings." Intuitive physics and psychology serve to compress world-knowledge immensely. But how do you create a schema for common sense? I've thought about this problem quite a bit and am writing another post on it. It's actually a lot harder than you'd think, as [Davis et al., 1998](http://groups.csail.mit.edu/medg/ftp/psz/k-rep.html#role5) point out:


> The theory [i.e. any schema you try and conjure up] is fragmentary in two distinct senses: (i) the representation typically incorporates only part of the insight or belief that motivated it, and (ii) that insight or belief is in turn only a part of the complex and multi-faceted phenomenon of intelligent reasoning.


## My opinion

I don't know. I think I'll be long dead by the time bottom-up is computationally feasible. However, I agree top-down is lacks the "common sense" or "intelligent reasoning" component.

## Middle-out?

Maybe the solution is to think of AGI a a swiss-army knife. You could put RL at the centre, with many pre-trained modules (e.g. speech-recognition, vision) at the edges, and give the RL controller the ability to resume training of the modules or create new modules. I think this is roughly equivalent to a human baby, who innately has the ability to smell, see, touch, hear, talk, but has to figure out how to use all his subsystems effectively. This still leaves the problem of an appropriate reward function.
