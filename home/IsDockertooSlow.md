---
title: Is Docker too Slow
description: 
published: true
date: 2020-06-05T10:00:11.027Z
tags: 
editor: undefined
---

# Is Docker Too Slow?

So Docker was super easy to set up `sudo snap install docker`, and, if I want to wipe it I can just do `docker rm wiki`.

Would it be better if I bit the bullet and set up *WikiJS* on a proper installation for want of performance?

Would that make the set up more or less portable?

Portability Considerations
==========================

It sounds like one of the advantages to Docker is that [data is storedin the container](https://docs.docker.com/engine/faq/#do-i-lose-my-data-when-the-container-exits),
this means that when I want to move or back up my wikiJS all I need to
do is take the whole container, I don\'t have to backup a SQL database
or import it or move it, or worry about where media data went and all
that shit.

In saying that though, maybe getting used to databases could be wise, they do bring something to the table over just plain text (backlinks, painless search etc.).

Migrating
---------

To copy a docker image over all you have to do is export it[^1]

``` {.bash}
docker save image-name > image-name.tar
```

and then it\'s just a matter of importing it with:

``` {.bash}
cat image-name.tar | docker load    
```

Footnotes
=========

[^1]: [ways to move Docker container to another
    host](https://bobcares.com/blog/move-docker-container-to-another-host/)

This was converted from =org= to =md= using =pandoc -t gfm= at time: 
2020-05-10T22-13-34

