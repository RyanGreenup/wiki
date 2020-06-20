---
title: How to Write Macros in Emacs
description: A walkthrough of the El Macro Package
published: true
date: 2020-06-20T07:30:22.996Z
tags: 
editor: markdown
---

The easiest way to do this would be a macro, more information can be found on the [emacswiki](https://www.emacswiki.org/emacs/KeyboardMacros), but essentially all you would do is:

1. `C-x (`
  * Start Recording a Macro
2. `C-c a a C-c C-x C-c`
  * Open the Agenda in column view
3. `C-x )`
  * End the Macro
4. `M-x name-last-kbd-macro my-day-page`
  * Give the macro a name
5. `M-x insert-kbd-macro`
  * Insert the Macro
6. `(global-set-key (kbd "C-c b") 'my-day-page)`


That macro function and keybinding can now be added to your `~/emacs.d/init.el` file and pressing `C-c b` should now open up the day-page.

All together it might look like this:

    ;; Macro for Day View
    (global-set-key (kbd "C-c a") 'org-agenda)
    (fset 'my-day-page
    (kmacro-lambda-form [?\C-c ?a ?a ?\C-c ?\C-x ?\C-c] 0 "%d"))
    (global-set-key (kbd "C-c b") 'my-day-page)



### -- EDIT by OP --

If you want to see what a macro is really doing, use the package [elmacro](https://emacs.stackexchange.com/questions/70/how-to-save-a-keyboard-macro-as-a-lisp-function), which turns your macro into a elisp function. In your case, after installation of `elmacro` from `melpa`, run `elmacro-mode`.

Define the macro as usual `<f3>C-c a a d R C-c C-x C-c<f4>`, and run the magical `M-x elmacro-show-last-macro`. It will generate a buffer with the elisp function!

```
(defun last-macro ()
  (interactive)
  (org-agenda-list nil)
  (org-agenda nil)
  (org-agenda-day-view nil)
  (org-agenda-clockreport-mode)
  (org-agenda-columns))
```

Please note that this result is not completely satisfactory. You want to get rid of `(org-agenda nil)` from the function, ending up give you

```
(defun the-macro-you-like ()
  (interactive)
  (org-agenda-list nil)
  (org-agenda-day-view nil)
  (org-agenda-clockreport-mode)
  (org-agenda-columns))
```

Finally, put this function in your config file, and bind it to `<f10>` for example by

`(global-set-key (kbd "<f10>") 'the-macro-you-like)`
