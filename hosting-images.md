---
title: Hosting Images
description: 
published: true
date: 2020-08-30T23:20:41.678Z
tags: 
editor: undefined
---

2. Put all the images on a local server, see for instance this image:



  * ![Example of Image on a server](https://ryansnotes.org/webdav/screenshot_from_2020-05-10_14-35-35.png =100x)

  

  * See [Hosting Images](/hosting-images.md)

  * This does permanently solve the image problem, but, there are a few pitfalls (I think you could use `git` or `webdav`, either should be fine).

    * all the links will be relative to the domain, this means you MUST, have a domain name and you must be prepared to rename every image in the event that your domain name expires.

    * You can only access images if you're online, (even if you were offline, the images will follow the path to the domain, even if they were accessible on `localhost`, this also requires some manual interrvention.

    * This does however mean that images will either all work or all not work (as opposed to the current mess of half and half), and sharing MD/HTML files will be much easier if the path is to a public site

    * This also means that the images will be public

    * Maybe I can find a self-hosted `imgur` program to try and streamline it?

      * One such example is [airlift](https://github.com/moshee/airlift/) but I can't figure out how to proxy apache to it????

      * WebDav works with the *Document's* app

        * This is arguably the simplest solution and the most likely to always have support

      * I could also just use nextcloud:

        * ![this is an inage](https://ryansnotes.org/nextcloud/index.php/s/QBCWTpekEJwjRSt/preview =100x)

        * [See this issue, they implemented preview links](https://github.com/nextcloud/server/pull/6599)

      * There's also [Koken](https://github.com/koken)

      * Also there's [Cheverto](https://write.corbpie.com/chevereto-a-self-hosted-imgur-alternative/)

      * piwigo is another




## Lifetime Domains
These are not a thing, can't be done, but it might not matter, if you use a simple webdav then a domain name can be fixed, essentially, with `sed`, it's not ideal but if you just did something like replacing this  `\!.*\[.*\]\(.*ryansnotes.org.*)` with `\!.*\[.*\]\(.*newdomain.org.*)` you'd be set, so it probably doesn't matter toooo much, but it's fucking invonient for sure

## Nextcloud
This kinda ties you to nextcloud though so ehh, but it makes more sense than something like airlift

## Using wikiJS
This is a weird way to go about it, but given the problem is created by WikiJS you could just translate the image into a path to the image on WikiJS:

> `https://ryansnotes.org/nextcloud/index.php/s/QBCWTpekEJwjRSt/preview`
> ![This is on WikiJS [here](https://ryansnotes.org/nextcloud/index.php/s/QBCWTpekEJwjRSt/preview)](https://ryansnotes.org/nextcloud/index.php/s/QBCWTpekEJwjRSt/preview =100x)














