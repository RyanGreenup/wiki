---
title: Alternative Wikis
description: My thoughts on Using a wiki like WikiJS or media Wiki as opposed to or in conjuction to org-roam/org-deft and markdown.
published: true
date: 2020-07-17T03:02:46.310Z
tags: 
editor: undefined
---

# Using Wikis
So what i like about wiki's like WikiJS is that:

## Advantages

1. They have the same look and interface everywhere
2. I don't have to fuck around with publishing
3. I don't have to fuck around with making a search engine or with ripgrep
  + So this might be relatively easy with *Notable* which has an intelligent search algorithm but that isn't FOSS
  + This isn't too bad with [recoll](https://www.lesbonscomptes.com/recoll/) either to be honest.
 4. Sharing is really simple because I can tag pages as public or private
 5. *Mediawiki* and *WikiJS* both offer autocomplete for notes to insert
   + `org-mode` and *Vim* both have that but it isn't quite as seamless
   + although `org-roam` via `SPC n r i` is fairly painless
6. Even though `org-roam` is really cool and markdown is pleasant because it's local, I love that a wiki is wrapped all into just one working application, I feel save using it, the search will always work, the links will always work, it's well it's safe.
  + [Should this affect My desire to use Docker?](/home/IsDockertooSlow)
  + Is there a wiki with the features of Roam? see [Alternative Wikis](NoteTaking/Alternative-Wikis)
  + Certain Apps like Nextcloud and WikiJS can run in self-contained windows on iOS and corresponding to the web app, that makes them feel way way more native
    + This does not work for mediawiki
7. Tags can work out of the box which is soooo nice.  
8. cross platform support
9. Privacy
	+ I can VPN into home and use a wiki without having to worry about syncing files or about privacy 

 
 ## Disadvantages
 + The editing does sort of suck
   + but using an external editor is fine
   + Integrating WikiJS into Git fixes this.
 + It can lead to fragmentation, like right now these are all the notes I have on databases and Apache:
   + [MediaWiki](http://ryansnotes.org/mediawiki/index.php/Exporting)
   + [WikiJS](/home/todo/Apache-Server))
   + [Org](https://ryansnotes.org/Org/roam/20200514132606-apache2.html)
   + [Markdown](http://ryansnotes.org/MD/Document%20Authoring/Hosting_Server.html)
 + It can be a little slow to load pages but it's not actually too bad, it's not as quick as something like *OneNote* which can run locally on multiple devices.
   + I should look at **_D_**-Note and <i>Lea</i>Note

## Neutral
+ Things are locked in a database
+ You'd have to create a text database index anyway (*MkDocs*)
+ You'd have to create a relation index (`org`-*Roam*)

| Pros         | Cons                |
|--------------|---------------------|
| quick search | No Grep             |
| Back Links   | Trickier to back up |


















---
---
---
.
## Documentation

[Tikz](./University/Documentation/Tikz.md)
    * [upmath](/University/Documentation/Tikz/upmath)
    
* [Comparing-Wikis](/Notes/Comparing-Wikis)

## Wiki Stuff
 * [Using Elastic Search in WikJS](./Notes/Using-Elastic-Search.md)
 * [Kroki](./wikijs/kroki.md)
 
### Markdown Editors
I just lost some work when the laptop crashed, the markdown editors I was considering where listed on the arche wiki, the one I was interested in was moeeditor. 

With regards to notetaking and wikis, O need to consider how clumsy it is to get material in and out and frankly the most painless tool is WikiJS, I’m not super happy with its mobile interface though. 

I may play with Moin moin simply because it doesn’t require a dB. 

 ideally Id use editors with interlinking support, recoll for searching (fzf ns script is perfect) and tmsu for tagging  
 
 I like notable but because ots not FOSS I dont want to get to wrapped up in it (I should keep an eye on zim and boostnote though)  
 
 
 
 $$
 \int 1+6
 $$
 
 
 
 
 
