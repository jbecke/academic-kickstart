+++
title = "Search Penngine"
date = 2018-08-17T18:21:54-04:00
draft = false

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = []

# Project summary to display on homepage.
summary = "A search engine built from scratch (distributed crawler, stream processing engine, page rank, TFIDF)."

# Optional image to display on homepage.
image_preview = "penngine.png"

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

{{< figure src="/img/search1.png" title="Search results for Robert Mueller" >}}

CIS 555 is a project elective at Penn where groups of students builds a search engine ("Google clone") from scratch. Most of the semester is done individually until the last month, where students come together and build the final product.

The semester started by building a server that accepted HTTP requests using Java's TCP Socket and SocketFactory classes. This involved a deep dive into the HTTP 1.0/1.1 spec to ensure my system was compliant. I soon extended the server to a multithreaded implementation that used my own blocking queue and thread pool implementation. I benchmarked to ensure accuracy and ability to handle concurrent requests of different content types. Following this, I build a servlet container according to the Java spec, on top of my server. Next, I layered on a multithreaded crawler that adhered to polite web crawling standards. In a bit of a detour, I built a stream processing engine (Apache Storm clone) that pushed content from the crawler to users based on their subscriptions (like RSS). On top of the stream processing engine, I build a MapReduce engine that would be the basis for our final PageRank and TFIDF implementations. This all took about 4 months of individual work before groups were formed.

While other groups decided to move to Amazon for their final project, we decided to only use our own code. Our final project, Search Penngine, had a distributed, polite, crash-fault-tolerant crawl queue and a distributed filesystem. We were able to crawl thousands of URLs per minute using a cluster of five EC2 machines. One of the workers was also a master node that displayed diagnostics of the system. The master wasn't a point of failure however, as each node routed links to the appropriate node based on the hash of the URL. I built the front end (including some Twitter search integration for fun), the distributed crawler, and made most of the architectural decisions. I learned the importance of good documentation, planning, and future-proofing code.

One hiccup we ran into was slow PageRank and TFIDF runtimes. I found the issue was coming from my underlying MapReduce engine caching intermediate (key, value) pairs on disk instead of in memory. This is not necessarily a bad thing (indeed, were were instructed to do this during the semester) but caused significant delays in the two operations that used the engine. To solve this we upgraded our EC2 machines to 32 GB of RAM and switched to using a hash map to cache intermediate results. The following morning refrained from telling the guys what I'd done (I was administering the EC2 nodes), just saying that somehow TFIDF/PageRank sped up by 100x overnight! The in-memory caching allowed us to examine much more of the 1.6 million URLs we crawled and stored.

I refrain from sharing code for this project because the class runs every year, but here is another screenshot!

![search penngine screenshot cars](/img/search2.png)
