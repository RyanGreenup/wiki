---
title: Fish Shell
description: Tips and Tricks for using Fish Shell
published: true
date: 2020-07-17T09:08:39.321Z
tags: linux, fish
editor: markdown
---

# Fish Shell

## Helpful Functions

### CD with an ls

```bash
command -v exa >/dev/null 2>&1 || { echo >&2 "I require exa but it's not installed, install with cargo install exa.  Aborting."; exit 1; }
echo "
# Defined in - @ line 1
function f --wraps='cd ; exa -RGL 3' --description 'alias f=cd; exa -RGL 3'
  cd $argv ; exa -TL 2 ; exa ;
end
" > $HOME/.config/fish/functions/f.fish; exec fish

```