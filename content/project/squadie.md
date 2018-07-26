+++
title = "Open IE Research"
date = 2018-07-24T14:27:01-04:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = []

# Project summary to display on homepage.
summary = "Learning to Extract Implicit Information via Reading Comprehension Datasets"

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


What is Open Information Extraction (OpenIE)?
---
OpenIE is the [Natural Language Processing task](https://github.com/sebastianruder/NLP-progress) of extracting machine-readable information from free text (e.g. books, news, etc). Concretely, most OpenIE systems generate \<subject, relation, object\> tuples, e.g. "Barack Obama was President of the United States." becomes \<Barack Obama, was President of, the United States\> or \<Barack Obama, was, President of the United States\>. OpenIE is useful for knowledge-base construction, fact-checking, 

What are the issues with existing systems?
---
Current systems fail to extract tuples for *implicit* relations, e.g. "U.S. President Barack Obama said yesterday..." should imply \<Barack Obama, is , U.S President\>. While some parse-based methods can handle simple implicit relations like this, the problem is quickly exasterbated.
