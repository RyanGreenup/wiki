---
title: Open Files in Other Editor From Emacs
description: How to take a file in Emacs and open it in another Editor
published: true
date: 2020-06-18T04:05:34.419Z
tags: 
editor: undefined
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
(defun my-open-current-file-in-vscode ()
  (interactive)
  (save-window-excursion
   (async-shell-command

    (format "code --add ~/Notes/MD/notes --goto %S:%d"
            (shell-quote-argument buffer-file-name)
            (+ (if (bolp) 1 0) (count-lines 1 (point)))
            ))
   ))
```


## Elisp Shortcuts

### Generic

A shortcut generically can be set by:

```elisp
(global-set-key (kbd "C-c v") 'my-open-current-file-in-vim)
```

### Doom Specific

#### Global
I also included some of my own bindings for inspiration:

```elisp
(map! :leader
;; #' delimits namespace, i.e. local var
      "h L" #'global-keycast-mode
      "f t" #'find-in-dotfiles
      "f T" #'browse-dotfiles
      "f k" #'darkroom-mode ;; Just use zen mode with SPC t z
      "i n" 'open-wiki-index
      "r o" 'helm-org-rifle-org-directory ;; [[89238]] ord-dir is different to agenda
      "f z" 'counsel-fzf
      "r b" 'helm-org-rifle-current-buffer
      "r d" 'helm-org-rifle-directories
      "o !" 'open-all-org-agenda-files
      "/"   'helm-rg
      "r hh" 'helm-org-in-buffer-headings
      "r ha" 'helm-org-agenda-files-headings
      "f mz" 'my-open-current-file-in-zettlr
      "f mt" 'my-open-current-file-in-typora
      "f mm" 'my-open-current-file-in-marktext
      "f mc" 'my-open-current-file-in-vscode
      )
```

#### Local

If the keybinding is local then the shortcut must be prefixed by <kbd>SPACE </kbd> <kbd> m </kbd>


```elisp
(map!  :after markdown-mode
        :map markdown-mode-map
        :localleader
        "f z" 'my-open-current-file-in-zettlr
        "f t" 'my-open-current-file-in-typora
        "f m" 'my-open-current-file-in-marktext
        "f c" 'my-open-current-file-in-vscode
 )
```



















