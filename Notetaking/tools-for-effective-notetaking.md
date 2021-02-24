---
title: Tools for Effective Notetaking
description: Tools that are useful for effective notetaking
published: true
date: 2021-02-24T00:36:40.249Z
tags: 
editor: markdown
dateCreated: 2021-02-23T22:41:43.587Z
---

## Note taking Tools

### The Simplest Approach

- Use Vnote and/or Notable

- Use MD Files

- Consider using [Dokuwiki](https://github.com/splitbrain/dokuwiki) and using [Syncthing](https://github.com/syncthing/syncthing) to keep everything in sync, this will scale well.
   - See also: [WikiJS Vs Dokuwiki](/wikijs-vs-dokuwiki)

## Just Files

Use [*Marktext*](https://github.com/marktext/marktext) to go through your notes and use vscode/vim/emacs for better editing.

Use `grep` and for a better search use Recoll.

These can all be set up with bindings.

### Alternative Markdown Tools

There is a lot, some that come to mind:

- [ThiefMD](https://thiefmd.com/)
- [GitHub - fabiocolacio/Marker: 🖊 A gtk3 markdown editor](https://github.com/fabiocolacio/Marker)
- [MindForger](https://www.mindforger.com/)
- [Manuel Genovés / Apostrophe · GitLab](https://gitlab.gnome.org/somas/apostrophe)
- [Remarkable - Linux](https://remarkableapp.github.io/linux.html)
- [Stack Edit](https://stackedit.io/app#)
- [Zettlr](https://github.com/Zettlr/Zettlr)
  
  - JS so cross platform

see also:

- [this list of NoteTaking Tools](https://wiki.archlinux.org/index.php/list_of_applications#Notes)

- [this list of Markdown Tools]([List of applications - ArchWiki](https://wiki.archlinux.org/index.php/list_of_applications#Markdown))

## Other Tools

- Whiteboard one note style
  - [Markdown Editor Readability Improvements · Issue #216 · MicroPad/MicroPad-Core · GitHub](https://github.com/MicroPad/MicroPad-Core/issues/216)
- Markdown with a Data Base:
  - Boostnote and Joplin
    - Both are very nice but lock all your files in a database which sucks
- Markdown With a DataBase
  - Notable
    - Good but uses YAML tags instead of directories and is not Open-Source
  - [MikiDown](https://shadowkyogre.github.io/mikidown/#split)
    - Written in Python, so a little slow + depe

### Joplin

So as far as a replacement for Evernote, Joplin is pretty good, but it does have some weaknesses:

- The documents are locked in a DB
- The text search only uses Sqlite, which is generally far worse than Recoll at matching document queries [source](https://partyondata.com/2009/07/06/a-comparison-of-open-source-search-engines-and-indexing-twitter/)
  - It is also worse at matching fuzzy matches than fzf/skim/vscode
- No version control  
- Syncing with WebDAV rather than Git is a nuisance (i.e. merges are painful)
- Web Clipper is really good but arguably inferior to monolith.

## Related

- [Task Management Tools](journal.university.taks-management.md)
- 
