---
title: Using Elastic Search
description: 
published: true
date: 2020-06-17T13:37:28.592Z
tags: 
editor: undefined
---

# Elastic Search Via Docker
Basically just run this:

```bash
$ docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elasticsearch:tag
```
and then tell the search module to use:

```
http://localhost:9200
```

And it *just works*.