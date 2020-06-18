---
title: Open Files in Other Editor From Emacs
description: How to take a file in Emacs and open it in another Editor
published: true
date: 2020-06-18T02:02:51.864Z
tags: emacs, vim
editor: markdown
---

# Open Files in Other Editor

## Elisp Functions
The Following can be used to open files in another editor:

> `~/DotFiles/DoomEmacs/.doom.d/config.el`
```elisp
(defun my-open-current-file-in-zettlr ()
  (interactive)
  (async-shell-command
   (format "zettlr  %S"
           (shell-quote-argument buffer-file-name))))

(defun my-open-current-file-in-marktext ()
  (interactive)
  (async-shell-command
   (format "marktext %S"
           (shell-quote-argument buffer-file-name))))

(defun my-open-current-file-in-typora ()
  (interactive)
  (async-shell-command
   (format "typora %S"
           (shell-quote-argument buffer-file-name))))
          
```

## Vim

In Vim we can specify the line number as well:

```elisp
(defun my-open-current-file-in-vim ()
  (interactive)
  (async-shell-command
                                        ;  (format "gvim +%d %s"
   (format "~/.local/kitty.app/bin/kitty -e nvim +%d %s"
           (+ (if (bolp) 1 0) (count-lines 1 (point)))
           (shell-quote-argument buffer-file-name))))
```

## VSCode

In VSCode we can also specify a folder to open:


```elisp
(defun my-open-current-file-in-vim ()
  (interactive)
  (async-shell-command
                                        ;  (format "gvim +%d %s"
   (format "~/.local/kitty.app/bin/kitty -e nvim +%d %s"
           (+ (if (bolp) 1 0) (count-lines 1 (point)))
           (shell-quote-argument buffer-file-name))))
```


## Elisp Shortcuts

### Generic

A shortcut generically can be set by:

```elisp
(global-set-key (kbd "C-c v") 'my-open-current-file-in-vim)
```

### Doom Specific

#### Global

#### Local

If the keybinding is local then the 




















