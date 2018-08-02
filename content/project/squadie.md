+++
title = "Open IE Research"
date = 2018-07-24T14:27:01-04:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = []

# Project summary to display on homepage.
summary = "Learning to Extract Implicit Information via Reading Comprehension Datasets."

# Optional image to display on homepage.
image_preview = "npc.jpg"

# Optional external URL for project (replaces project detail page).
external_link = ""

# Does the project detail page use math formatting?
math = false

# Does the project detail page use source code highlighting?
highlight = true

# Featured image
# Place your image in the `static/img/` folder and reference its filename below, e.g. `image = "example.jpg"`.
[header]
image = ""
caption = ""

+++


## What is Open Information Extraction (OpenIE)?

OpenIE is the [Natural Language Processing task](https://github.com/sebastianruder/NLP-progress) of extracting machine-readable information from free text (e.g. books, news, etc). Concretely, most OpenIE systems generate \<subject, relation, object\> tuples, e.g. "Barack Obama was President of the United States." becomes \<Barack Obama, was President of, the United States\> or \<Barack Obama, was, President of the United States\>. OpenIE is useful for knowledge-base construction, fact-checking, and other downstream NLP applications [(Stanovsky et al., 2015)](http://www.aclweb.org/anthology/P15-2050).

## What are the issues with existing systems?

Current systems fail to extract tuples for *implicit* relations, e.g. "U.S. President Barack Obama said yesterday..." should imply \<Barack Obama, is , U.S President\>. While some parse-based methods can handle simple implicit relations like this, longer sentences pose problems.

## What I've been workin on

I've created several tools towards implicit OpenIE and am currently working on a paper.

1. Converted the SQuAD and NewsQA datasets to OpenIE datasets https://github.com/NPCai/Squadie
2. Created an attention seq2seq model https://github.com/NPCai/Nopie
3. Catalogued and examined previous works https://github.com/NPCai/Open-IE-Papers
4. Updated a previously existing benchmark to Python 3 and improved it https://github.com/NPCai/oie-benchmark
5. Other misc tools at https://github.com/NPCai

I'll be doing an Independent Study at Penn Engineering Fall 2018 semester.
