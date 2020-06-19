---
title: Solf Hosted Applications / Ideas to implement
description: 
published: true
date: 2020-06-19T02:14:55.131Z
tags: 
editor: markdown
---

# Ideas for Self Hosting

> [Currently implemented](./home/Currently-Implemented-Self-Hosting.md)
> There's a cool list [here](https://github.com/awesome-selfhosted/awesome-selfhosted)

+ [paperless](https://github.com/the-paperless-project/paperless)

  + This is basically the OCR feature of Evernote, it means I can just dump every PDF I've ever had in there.
  
  + It might not work as well as evernote but it's FOSS
  
+ Seafile or NextCloud
  + I'd never have to pay for *Dropbox* again
    + I wonder if I could access the data on the iPad so it's actually accessible?
      + Or would I just be better off with git?
      
+ ~~[Standard Notes](https://app.standardnotes.org/) is kinda cool but I don't see how it's different from *WikiJS* (see also [OpenNotes](https://github.com/FoxUSA/OpenNote))~~
* OneNote Reading List
* Evernote File Dump
* One Note or Evernote notes app
  * maybe just a wiki tbh, because managing files and sharing is a pita that i can offload.
  * theres also joplin synced with nextcloud and ore webdav  
  
  ## Missing Features

+ so another feature I'm missing from one  note is  To Do Lists,  like Reading List etc.   after paperprss  and todo  through   

  + there's [Tracks](https://www.getontracks.org/) and also there's also [volition](https://github.com/usevolition/volition/blob/master/README.md) which looks good, but ultimately the nextcloud tasks app might be the simplest (I should also look at setting up nextcloud markdown editors) i should also look at setting up something like [trello](https://wekan.github.io/) and a [calendar](https://www.calendarserver.org/ccs-calendarserver/)

+ the only other thing would be like plex or a media server
  + Actually I really really want like a music/media server, something like apple music or spotify that actually works

+ oh also a reading list, like for ios, but available ever (this is more like a todo app though, really the important part is an app so its all painless)

oh and a books manager would be nice so i can access textbooks from anywhere (webDav maybe?)

 + [ebook managwr](https://getpolarized.io/) and or consider using [webdav](./usingwebdav), something so I can quickly find all my books on all devices, maybe honestly just nextcloud with full text search (or paperless)
   + I tried Calibre but it was just too slow
     + [a nice tutorial on nextcloud](https://websiteforstudents.com/setup-nextcloud-on-ubuntu-18-04-lts-beta-with-apache2-mariadb-and-php-7-1-support/)
  
-   you can host a [hackmd Now CodiMd](https://demo.codimd.org/) which is really cool but im not sure what id do with it   theres also [this katex editor](https://josephernest.github.io/writing/) thats way way smoother  



## File Dump and Search


## Note Taking Apps and Wikis
* [leanote](http://leanote.org/) looks really interesting, with mathjax and native apps!
Again though, with recoll abd org mode and mkdocs [as discussed here](https://ryansnotes.org/Org/manual.html) this is superflous  
throwing in a wiki for painless sharing with webdav, nextcloud and ssh only compounds that  

also check out wiznote



* I've [heard good things](https://www.reddit.com/r/selfhosted/comments/6imt64/what_self_hosted_wiki_has_the_best_mobile_app/dj8w7xm/) about [BookStack](https://www.bookstackapp.com/)

* I should take another look at `dnote` because I thought that email was a nice touch.
* I looked at *BookStack* but they haven't implemented math yet (and even then it will only be katex.
* I should really look into [Gollum](https://github.com/gollum/gollum), 
	* I will need to reduce the size of the individual git repos perhaps though.
* [Connected Text](https://www.connectedtext.com/) Is another one.
* [GitIt](https://github.com/jgm/gitit) might be an alternative to `gollum`

Basically you just want to have a quick run through [note software](https://www.google.com/search?client=firefox-b-d&q=note+taking+software++arch+wiki) and [wiki](https://wiki.archlinux.org/index.php/Category:Wiki_software) and pick one / two keepers ( I really like VNote, integration with Notable Isn't bad either, it's just a little slow, although on Vidar, but that is *Ubuntu*)

## Code Snippets
[only fo code but nice interface](https://demo.docpht.org/page/php-7/loops)

I like *Plex* but is there a way I could share access to my *Plex* library?



## ToDo App
I want to stay with *ToDoist* because of the killer features, but, I have difficulty trusting it.

In saying that though, there are ZERO nice alternatives other than `org-mode` so I may as well just use both and try and set up `ssh` with emacs.

I'll just tend towards whatever is convenient.

> This can be the one non-FOSS app I use, and, to be fair, the dev seems like a real person who posts on `ycombinator`.

## TODO drawing and diagrams
you want to integrate [this](https://github.com/jgraph/drawio) as if it was onenote.

There's also XournalPP and Gournal.

## Media Server
I like *Plex* but is there a way I could share access to my *Plex* library?



> [See the list](https://github.com/awesome-selfhosted/awesome-selfhosted#video-streaming)

+ Jellyfish is one them

+ [Olaris Discussion is where to start](https://www.reddit.com/r/selfhosted/comments/givr4j/the_olaris_team_wants_your_input_foss_plex/)'




## Document Server
Mayan EDMS [As Discussed here](https://ryansnotes.org/Org/todo.html) is Actually really easy to set up and works really well, I love that it's stupid simple.

Basically what I want is full-text search for nextcloud that works really really well, but, in saying that, I don't want the super complicated overheads of configuring *NextCloud* to do that (although I might just have to eat that), see the [todo item](https://ryansnotes.org/Org/todo.html#orgf61687d) on it.

Ohhh you can download it, but the ios UI sucks balls

+ [Papermerge](https://github.com/ciur/papermerge) Looks the nicest for sure!
  + The docs suggest that without docker I wouldn't get Auto OCR?
  + It has a nice search
    + Not live :(
    + But a much better layout than teedy
  + It OCR's everything
+ [Teedy](https://github.com/sismics/docs) Is another really nice option, with a clear business strategy.
  + ~~This doesn't let you highlight the text from within the webapp.~~ It does for some actually
  + You have to prefix searches with `full:`, this will get annoying.

