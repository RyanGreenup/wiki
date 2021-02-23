---
title: Notetaking Tools and Wikis
description: A list of notetaking tools and wikis (open source generally)
published: true
date: 2021-02-23T23:18:14.297Z
tags: 
editor: markdown
dateCreated: 2021-02-23T22:28:37.340Z
---


# Note taking Tools and wikis

[See Strategy](./NoteTakingStrategy.md)


This page was just dumped from my personal notes, it needs to be restructured significantly, you can help with that.

## General

So I'm not sure if a live preview fuzzy search

| Program                              | FOSS   | Fuzzy Search | Live Update        | Preview  |
| ------------------------------------ | ------ | ------------ | ------------------ | -------- |
| `Abricotine`                         | YES    | NO           | NO                 | NO       |
| `Typora`                             | NO     | NO           | NO                 | YES      |
| `Notable`                            | Was [^838]   | YES          | YES                | YES      |
| *Boostnote*                          | YES    | YES*         | YES                | YES      |
| *SimpleNote*                         | YES    | YES          | YES                | YES      |
| *Obsidian*                           | NO     | NO*          | NO                 | YES      |
| `remnote.io`                         | NO     | NO*          | NO                 | YES      |
| `Joplin`                             | YES    | NO           | NO                 | YES      |
| `emacs`                              | YES    |              |                    |          |
| `atom`                               | YES    | maybe        |                    |          |
| `VSCode`                             | Maybe? | YES          | YES                |          |
| `Ranger`                             | Yes    | Probably     | Maybe?             | Not Yet? |
| `Ranger Alt?`                        | YES    |              |                    |          |
| *InkDrop*                            | NO     | maybe        |                    |          |
| Bear                                 |        |              |                    |          |
| Zettlr [^z]                          | YES    | Yes          | Live-Preview so No | Yes      |
| unevaluated                          | ---    | ---          | ---                | ---      |
| mikidown                             |        |              |                    |          |
| mynoteX                              |        |              |                    |          |
| outwikir                             |        |              |                    |          |
| pervane [^1]                         | YES    | YES          | YES                | YES      |
| WikiMD [^2]                          | YES    | NO           | Yes                | YES      |
| Tettra                               |        |              |                    |          |
| Neuclino                             |        |              |                    |          |
| logseq [^69]                         |        |              |                    |          |
| [Neuron](https://neuron.zettel.page) |        |              |                    |          |

[^69]:  [GitHub - logseq/logseq: A privacy-first, open-source platform for knowledge sharing and management.](https://github.com/logseq/logseq)

[^838]: To be fair, the developer continues to contribute to many open source libraries, anybody could recreate Notable, but they would have to glue together all the pieces. He's one guy and that's a reasonable approach so I include it here, but generally, unless a tool is particularly relevant, it should not be included here.

* Zim is a nice tool for quick notes that are out of the way
  * but the lack of math and non-standard syntax is a shame, as a way to get
    similar behaviour just use cadmus with marktext.
* [Notational FZF Vim](https://github.com/alok/notational-fzf-vim) is quite good
  as well, generally writing markdown in vim and preiewing in the browser is
  smoother than emacs and `org-mode`.
* Basically setting up a server is the best way, and, after doing that setting
  up [MediaWiki](../Document%20Authoring/Hosting_Server.md) (I prefer that over
  TiddlyWiki tbh) and you're off to the races, but having everything in
  `org-mode` and/or markdown is desirable, look at a static site generator.
* Gollum wiki is great but requires, I believe, a smaller more focused Git repo
  (otherwise it lags) (I should look into implementing that anyway)
  * It's a little slow and the mathematics doesn't always render though
    * plus you'd have to VPN in if you wanted to use HTTP auth (which might be
      easier anyway)
    * Other than that though it works really well on mobile and if the server
      starts at boot it's frictionless (I should run it on the Raspberry Pi)
* I should also see if there is a simple way too host TiddlyWiki (the dropbox
  solutions was too clums)
  * Yeah the easiest way is to just do:

```bash
npm install -g tiddlywiki
cd /path/to/TWFolder
tiddlywiki wikiname --init server
```

Then start the server:

```bash
tiddlywiki mywiki --listen port=9267 host=0.0.0.0
```

> This still gave me errors, TiddlyWiki is just too complicated, yeah sure, *MediaWiki* requires you to deal with the folder of files and a database (as opposed to a single file), but, it's also frictionless to host with *Apache* and frictionless to access from multiple devices.

There's actually a really good list [on the *Arch-Wiki*
here](https://wiki.archlinux.org/index.php/List_of_applications/Documents#Readers_and_viewers).

 [using pandoc and lynx ](https://tosbourn.com/view-markdown-files-terminal/)
 our even Firefox? Might be the way to go, [look at
 this](https://github.com/ranger/ranger/wiki/Image-Previews)

> Maybe if I just use `| firefox -` then scope will jam firefox in there??

 The flow being basically 'scope.sh -> pandoc -> lynx'

## Programs

A lot of these programs just don't make sense compared ot using org-mode which is more fully featured, the only advantage is that markdown is slightly more commonplace. For markdown purposes though just use Joplin because it syncs with WebDav VNote (although very good) don't make any sense when org-mode+recoll already works better.

* **VNote**
  
  * Most Full Features
  
  * Kinda Slow
  
  * the search doesn't give a preview which can be annoying.
  
  * Can't make or follow links grr
  
  * Although it creates `.json` files everywhere that get out of sync, they can
    be regenerated by removing all of them and re-selecting the directory as a
    notebook, so something lik:
    
    ```bash
    find ~/Notes/MD -name '*.json' -exec rm {} \;
    mkdir /tmp/CantUsemktempNoDotsAllowed; cd CantUsemktempNoDotsAllowed
    cp -r ~/Notes/MD ./
    vnote ./ # Now import this directory
    ```

* **Joplin**
  
  * Not Plain Text Files
  * Not as featureful as a full blown wiki

* **Notable**
  
  * Only a Flat File structure is supported is a nuisance
  * Not great Navigation unless you're set on definitely using links
    * Although I could tolerate that I would need a decent mobile solution to
      make it seam bearable
      * GitJournal doesn't support math Yet, but it'd be worth looking at.

* **VSCode** 
  * This is the best solution really, Outside of Joplin and Org-Mode this is the best way to work with and edit Markdown, use grep/recoll for searching and extensions for backlinks (see [[VSCode-Tips-Tricks.md]]) For Mathjax use Markdown-Preview-Enhanced, then markdown math can be used with pandoc by doing:

      ```bash
      pandoc -f markdown+raw_tex+tex_math_single_backslash -t html --mathjax -s -o /tmp/file.html

      ```

* MikiDown
  
  * This looks promising
  * Very Simple Program Structure

* Boostnote old
  
  * Really Nice Layout
  * Absolutely retarted File Management

* Boostnote New
  
  * No Links
  * No Mobile (No search capacity)
  * Local Storage not Yet Implemented

* Standard Notes
  
  * Really Nice Layout just like Boostnote
  * Free and Open Source
  * Extensions are a little pricey but not ridiculous.
  * Self hosting is an option which is really nice
  * Takes like a second to open each note
  * No capacity to interlink notes
  * Overall the app just feels clunky and super confusing. e.g. joplin is really simple to use but the mobile UI sucks, standard notes has a slightly better UI but not much better and the multiple different editors can feel a little bit clunky and overwhelming.
    * I like it but I couldn't imagine using it unless the User Experience was vastly improved, currently it doesn't bring much to the table over just using dokuwiki or joplin.
    


* Git Jounal and mweb

* Dnote is interesting in that it is just one sqlite file, but in the end that's essentially all joplin is as well.

* Zim has poor math support and offers no advantages over just using dokuwiki or Joplin

## Self Hosted

One of the issues with self-hosted note taking solutions is that they just don't make any sense over just using Dokuwiki though. 

* WizNote
  * Couldn't fid a way to host it on Apache without using docker
  * didn't appear to have any iOS appear
    * Not sure that matters tbh, because the alternative is Mediawiki mobile,
      but, in saying that still it's a issue minor
  * Search was meh.
* [LeaNote](https://github.com/leanote/leanote)
  * Has an iOS app which is nice.
  * Apparently support is fairly limited unless you speak chinese
  * _I should look into this more closely when time permits_
* Pervane is kinda cool
  * Might as well just use WikiJS though
* Joplin
  * If this was the route you were gonna take, you'd just use *Joplin*, it's
    hard to trust Chinese software and the support will be limited
    * /*VNote* is the exception because it's zero-lock in and I've had a few
      responses to *GitHub*

## Wiki Software

An advantage to wiki software is you avoid link rot, but I'm not sure that's a real concern given that I have `fzf` scripts and unique names.

### Database

* MediaWiki
  * [Reasonable Syntax](./MediaWiki-Syntax.md)
  * Reasonable Interface
  * Very Scalable
  * Well Supported
  * Non-Standard Syntax makes it totally seperate
  * Tables and Math looks great!
  * EXTREMELY complicated to use with VisualEditor, arguably non functional
    * See [[MediaWiki/BlueSpice-Wiki]] for more info
* [WikiJS](./wikiJS.md)
  * Integrates with Git as plain files
  * Very cluncky and requires docker to use.
* I like how it looks and feels, but
  * Compared to wikiJS it does not feel good to use, there is no gitsync and no
    planting so it like isn’t suitable.

### No Database

> DB has the advantage of scaling well but, flat files using a search index (think elasticsearch) can make performance pretty good and read/edit is much faster.

#### Wikis

See Generally [Comparison of Wiki
Software](https://en.wikipedia.org/wiki/Comparison_of_wiki_software)

- Dokuwiki
  - This is what I would recommend using over Mediawiki, it has a similar feel
    and layout but it isn't complicated by the need of a database and more
    importantly than that it isn't hard to get material in and out.
- PMWiki
- gitit
  - A little finicky with file names
  - search only looks for whole words
    - Dokuwiki looks for fragments, but it is much slower.
* Pepperminty
  * Search isn't too bad
  * Non standard use of links though
    * I'm not sure if there's anyway to integrate my current notes with it
      TBH
  * It's essentially a lighter version WikiJS /of/
* [wikitten](https://wikitten.vizuina.com/)
  * This supports YAML Tags!
  * [See there GitHub](https://github.com/victorstanciu/Wikitten)
  * I’m not sure it has acceptable search though
* TiddlyWiki
  * I'm not a big fan but if you use `rclone` for *WebDAV* and the Tiddlywiki is there, it *just works* which is really nice.

#### Static Site Watchers / Git integration

* [GitWiki](http://www.drassil.org/git-wiki/main_page)
* [Jingo](https://github.com/claudioc/jingo)
  * This looks like it is essentiall a replacement for Gollum but better.
* Gollum
  * Slow to manipulate and Search
  * Search is innacurate
* Docsify, kinda
  * MDWiki
    * See also this [wikitten and mdwiki
      merge](https://github.com/zohead/wikitten-and-mdwiki)
* [Neuron](https://neuron.zettel.page)
  * this looks like a better alternative to mkdocs, but, I had trouble seeing it up. 

### Static Site

* Grav
* Hugo

### Local Wikis

- MDyna

- Trilium

- Zim
  
  ## Not FOSS
  
  ### Desktop Wiki / Note Taking Apps
  
  These deserve a special category, because although the code base is not open
  fully, the authors contribute to, and create, other open libraries used for the software.

The design is also zero lock in, meaning, these can be a good pathway to get
people to use a FOSS solution, `cadmus` is proof that creating one isn't too
hard, these tools also allow migration into *DokuWiki*, so, this is a much
better choice for somebody to make than *OneNote*.

- Notable
- Obsidian

### SASS

* [Tettra](https://tettra.com/)
* Neuclino
* [remnote](https://www.remnote.io/homepage)
  * this looks promising
* Notion

## Markdown Editors

There's a trade-off between capacity to edit text and readability, at least in
the corrent suite of software (although I would love something that previews as
well as marktext but edits as well as vim).

In order of most powerful editor, the markdown editors to use are:

You may want to use editors towards the bottom of the list in order to get the
capacity to drag/drop images in.

1. Vim
2. Emacs
3. VSCode (see [making-vscode-decent](./../Programming/JavaScript/making-vscode-decent.md))
   1. `ext:`Markdown Memo
      1. Works well, no tags support, no graph
         1. use `tchayen.markdown-links` for a graph
   2. `ext:`Foam
      1. Has a Graph
   3. `ext:`VSNotes
4. 1. `ext:`Markdown Notes
5. Atom
6. Zettlr
7. Typora
   1. Is NOT FOSS
8. Ghost Writer
9. MoeWriter
10. Marktext
11. [See Also This List on Arch
    Wiki](https://wiki.archlinux.org/index.php/list_of_applications#Markdown)
12. Moe
13. [qlin-app](https://github.com/qilin-editor/qilin-app)

### Markdown Viewers

Really though given that vim and emacs are so good at editing, what is really
needed is something to view the markdown:

* ~~Iamcco's markdown preview is simple but limited~~
  
  * Check out this new rust add on called [vim-markdown-composer](https://github.com/euclio/vim-markdown-composer) which is powered by a markdown parser called [aurelius](https://github.com/euclio/aurelius)
    * TODO Depedning on how this deals with links ill determine whther  not to prurs

* markserv on `npm` is quite good!
  
  * there's also allmark, python markdown-server and pervane but I don't think
    they're as nice

* ~~Maybe Consider using [The Julia Static Site Gen
  Franklin.jl](https://franklinjl.org/), it will allow for a live reload just
  like `markserv` but because it's in *Julia* it's gotta be fast, it's a good
  opportunity to learn julia and it may work better than `markserv` anyway.~~
  
  * Obviously I could do the same thing with `mkdocs` but it's really 
    slow so I gave up.
    * Also the live reload only really works with a dirty reload and that brakes
      the search anyway.
    * It may be necessary [to review the source code as an
      exemplar](https://github.com/tlienart/franklindocs/blob/master/index.md)~~

* Honestly VS Code, like the editor is subpar but the preview is fin, this is
  another case of needing a tiling window manager not needing a better editor.

* [MarkServ](./MarkServ.md) is really nice and very simple, I should:
  
  * Serv the notes globally and vpn into my home network
  * Edit the notes over ssh with emacs / vscode server
  * publish to md when I'm satisfied
  
  preview the way you expected it.

## Using VS Code for Browsing Notes

with the [NoteSearch](https://github.com/ryangreenup/cadmus) script I wrote, vscode is actually fairly well
equipped to browse notes:

* Vscode
  * foam
  * dendrom
  * markdown-notes
  * markdown-memo
* Neuron

## The Solution

1. Wiki
   2. Use DokuWiki or MediaWiki with PHP
2. Markdown
   1. Notable and VNote give a Guided Suite with flat files
   2. cadmus and/or VSCode with markdown-memo, foam and vs-markdown-notes is a good option for just plain text files
      3. See also Marktext, emacs and Atom.
   3. More DB Solution is Joplin or Boostnote 
3. Org-Mode
   - You don't have a choice here, it's just soo good

## A bunch of Electron Note Taking Apps Exist

You can see all the different [Electron Based Note taking apps here](https://www.electronjs.org/apps?q=note), there's a tonne.

Most of these don't support math and don't bring anything to the table over [the solution](#the-solution), but they're interesting all the same:

\-[Deer \| Apps \| Electron](https://www.electronjs.org/apps/deer)

- [MonteNote \| Apps \|
  Electron](https://www.electronjs.org/apps/montenote)
- [Opus \| Apps \| Electron](https://www.electronjs.org/apps/opus)
- [Knowte \| Apps \| Electron](https://www.electronjs.org/apps/knowte)
- [Recollectr \| Apps \|
  Electron](https://www.electronjs.org/apps/recollectr)
- [Geeks Diary \| Apps \|
  Electron](https://www.electronjs.org/apps/geeks-diary)
- [Code Notes \| Apps \|
  Electron](https://www.electronjs.org/apps/code-notes)
- [Znote \| Apps \| Electron](https://www.electronjs.org/apps/znote)
- [Flawesome \| Apps \|
  Electron](https://www.electronjs.org/apps/flawesome)
- [MDyna \| Apps \| Electron](https://www.electronjs.org/apps/mdyna)
- 

For Dokuwiki there are things like [Singlebox \| Apps \|
Electron](https://www.electronjs.org/apps/singlebox) that can wrap an
app in a single window which is super nice

### Todo

- Minder or org-mode is the best
  
  ### BibTeX
  
  [[https://www.electronjs.org/apps/biblio][Biblio | Apps | Electron]]

### Misc

ArchIvy is more like a bookmark manager, I personally like SingleFile

[^1]: [pervane](https://github.com/hakanu/pervane)

[^2]: [MD Wiki](https://dynalon.github.io/mdwiki/#!index.md)

[^z]: Unfourtunately the search for zettlr is totally inadequate and the links
are opened in an external editor by default, this makes it a bit of a bummer
to use.

## VNote

VNote is an amazing program, I initially dispensed with it because I had an enormous amount of trouble dealing with the bloody `.json` files everywhere, particularly when making new files in other apps.

This issue can be avoided by making new files in only `vnote`, but that's a bit of a pain because Vnote won't make a new file from a `[link](./to-file.md)` and will not watch the directory for moved files and stuff.

The solution to this is to remove all the `.json` files:

```bash
DIR="${HOME}/Notes/MD"
cd "${DIR}"
find ./ -name '*vnote.json' -exec rm {} \;  
```

And then add a new notebook:

![vnote1](_media/20200929135918104_2022338352.png)

![](_media/20200929142520827_1458169049_400.png)

When you set the directory it will recursively scan all the files.

### Images

Make sure you manually resize all the images, my recommended approach would be to do something like this:

```bash
# cd (dirname (fd . $HOME | sk)) 
NOTE="/path/to/note.md"
DIR="$(dirname "${NOTE}")"
MEDIA="./rel/path/media.png"

cd "${DIR}"

# Image Magick will respect Aspect ratio and only roughly match 500x500
convert -density 1000 -quality 100 -resize 500x500 "${MEDIA}" "500_${MEDIA}"
```

#### Location of Media

Remember to change the location of all the media to something reasonable like `_media` but it doesn't matter [^1] that much, `pandoc` can `--extract-media` so it's fixable

[^1]: Use a directory name like `_media` that way you can move directories with `sed`, e.g. `sed s/_media/_pics/g && mv _media pics`.

## See also 

> [Converting Documents to Markdown with
> Pandoc](./Using-Pandoc-to-Convert-Documents.md)
{.is-info}
