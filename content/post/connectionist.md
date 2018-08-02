+++
title = "The Tragedy of the Partially Observable Connectionist"
date = 2018-07-08T22:39:23-04:00
draft = true
summary = "Our minds are the Partially Observable Connectionist; brilliant distributed machinery, yet unable to introspect about its physical state. In this post, I examine some \"ah ha\" theories I've came across in Machine Learning. These strange papers fall out rank to propose models of consciousness, jokes, strong AI, and neuroscience."

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

This post is a collection of viewpoints and ideas on NNs, ML, psychology and neuroscience that should be of interest to anyone interested in AGI. These ideas have made me go "ahah", made me stop and ponder, do a double-take, or think about in the wee hours. The title reflects the opinion that these insights would be obvious, if only I could introspect on the firings of my neurons.

## A model of the brain
One can think of the brain as a large collection of inaccessible machinery combined with a small window of accessible area ("conscious" portion) [(Manuel Blum, 2018)](https://simons.berkeley.edu/events/can-machine-be-conscious-towards-conscious-ai#). Our introspective abilities -- without external tools -- are limited to the conscious portion. For example,  we cannot access the distributed representation of objects/concepts in our brain (assuming stored knowledge is not declarative, which I think is fair to make). Nor can we feel the internal firings of our neurons. However, we can describe certain logical aspects of the machinery, whether by evolutionary, logical, or folk explanations. To make this more concrete with an example:

__I ask you to think of all possible objects like a stool.__

Maybe you thought of a pedestal, a chair, a stair, a platform, etc.

Why did your unconscious machinery produce those discrete concepts?

Consider first the fact that I didn't ask for a specific relation to the discrete concept of 'chair', I just asked for similar objects. Perhaps the most salient relation of a stool is it's *purpose* (as opposed to form, size, color, etc), and so you conjured concepts of similar purpose. Whatever the reason, your [adaptive compressor](http://people.idsia.ch/~juergen/interest.html) has compressed those distributed representations to be close together.

When we build ANNs, we're using similar observations (AKA introspection, intuition) of epiphenomena. For example, the "attention mechanism" of seq2seq models comes from an intuition that a human translator has dynamic attention over the input sentence [(Bahdanau et al., 2014)](https://arxiv.org/abs/1409.0473). Is is from this intuition what we infer a plausible structure. One problem I see with this is that there could be so many intermediate processes (i.e. that are not apparent to us) about the brain, that our intuition isn't disposed to discover. Another problem is that there's so many  

---

## Imbue or teach?


At the end of (this talk at MSR)[https://youtu.be/Yr1mOzC93xs?t=59m13s], Yoshu Bengio has a good line.

"We are using our intuition, maths, and insights to build in the kind of priors evolution has optimized. And we are starting to use the same kind of mechanisms that evolution uses, like meta-learning. [. . .] Ultimately we can use some of [meta-learning] to discover the underlying discovery, but we'd also like to do it in a way that we understand the principles that give rise to good machine learning."

## But we understand the brain because neuroscience!

Because of our limited understanding of neuroscience (or, at the very least, the limited understanding by AI researchers) I think it's a fair approximation to say that we have little introspective ability beyond the conscious part. Use of intuitions has far exceeded neuroscience in ANN literature. I'd argue, even when neuroscience is used, it is as an explanation to justify initial intuitions.
