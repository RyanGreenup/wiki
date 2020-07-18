---
title: Fish Shell
description: Tips and Tricks for using Fish Shell
published: true
date: 2020-07-18T01:41:31.006Z
tags: linux, fish
editor: markdown
---

# Fish Shell

## Helpful Functions

> *FISH* doesn't have `alias` only functions, however alias is itself a function to create functions using a similar syntax as `bash`, you just have to remember, that after using to then call `funcsave name` to save it, for example:
> ```bash
> alias x='xclip -selection clipboard'
> funcsave x
> ```
> {.is-info}

### `cd` with an `ls`

```bash
command -v exa >/dev/null 2>&1 || { echo >&2 "I require exa but it's not installed, install with cargo install exa.  Aborting."; exit 1; }
echo "
# Defined in - @ line 1
function f --wraps='cd ; exa -RGL 3' --description 'alias f=cd; exa -RGL 3'
  cd $argv ; exa -TL 2 ; exa ;
end
" > $HOME/.config/fish/functions/f.fish; exec fish

```

Then change directories with `f /` and you'll notice that it changes directories, prints a tree and prints the files.

### `ls` everything

```bash
alias ls!='ls -ultrah'; funcsave ls!    
```

### Switch to NeoVim

Use this relatively shell agnostic way to avoid having vim installed.

```bash
exec bash
echo '
#!/bin/bash
nvim "${@}' >> '$HOME/bin/vim'

if [[ ":$PATH:" != *":$HOME/bin:"* ]]; then
    mkdir "$HOME/bin" &>/dev/null
    echo '
export PATH="$PATH:$HOME/google_appengine"
' >> '$HOME/.profile
fi  
exec fish
```

### fuzzy interactive fast grep

save the following in `/usr/bin` (or `$HOME/bin`) as `fif`, then you can type `fif` to start an interactive grep in the current directory:

> use <kbd>Ctrl</kbd>+<kbd>q</kbd> to switch to filtering by file name
{.is-info}

```bash
#! /usr/bin/env bash
#
# Author: Ryan Greenup <ryan.greenup@protonmail.com>

# * Shell Settings
set -o errexit  # abort on nonzero exitstatus
set -o nounset  # abort on unbound variable
set -o pipefail # don't hide errors within pipes

# * Main Function
main() {

    check_for_dependencies
    setVars
    readFirstArgument "${@}"
    SkimNotes "${@}"

}

# ** Helper Functions
# *** Check for Dependencies
check_for_dependencies () {

    for i in ${DependArray[@]}; do
        command -v "$i" >/dev/null 2>&1 || { echo >&2 "I require $i but it's not installed.  Aborting."; exit 1; }
    done


}

# **** List of Dependencies

declare -a DependArray=(
                      "rg"
                      "sk"
                      "mdcat"
                      "xclip"
                       )


# *** Set variables below main
setVars () {
    readonly script_name=$(basename "${0}")
    readonly script_dir=$( cd "$( dirname "${BASH_SOURCE[0]}" )" && pwd )
    IFS=$'\t\n'   # Split on newlines and tabs (but not on spaces)
}

# **** Print Help
Help () {


    echo
    echo -e "    \e[3m\e[1mNoteFind.sh \e[0m; Helpful Shell Scripts for Markdown Notes"
    echo -e "    \e[1;31m--------------------------\e[0m "
    echo
    echo -e "    \e[3m\e[1m• Usage \e[0m "
    echo
    echo -e "       "${script_name}"   [<path/to/notes>]"
    echo -e "       "${script_name}"   [-h]"
    echo -e "       "${script_name}"   [--help]"
    echo
    echo -e "           \e[3m By Design: No Options; No other Arguments\e[0m"
    echo
    echo -e "    \e[3m\e[1m• Key Bindings\e[0m "
    echo
    echo
    echo -e "        \e[1;91m    \e[1m Binding \e[0m\e[0m \e[1;34m┊┊┊ \e[0m Description "
    echo -e "        ..............\e[1;34m┊┊┊\e[0m........................................... "
    echo -e "        \e[1;95m Ctrl - q \e[0m \e[1;34m   ┊┊┊ \e[0m \e[1m Search \e[0m with \e[0m\e[3mripgrep\e[0m"
    echo -e "        \e[1;93m Ctrl - w \e[0m \e[1;34m   ┊┊┊ \e[0m \e[1m Copy \e[0m the Full Path to the Clipboard"
    echo -e "        \e[1;93m Alt  - w \e[0m \e[1;34m   ┊┊┊ \e[0m \e[1m Copy \e[0m the Relative Path to the Clipboard"
    echo -e "        \e[1;94m Alt  - e \e[0m \e[1;34m   ┊┊┊ \e[0m \e[1m Open \e[0m in Emacs"
    echo -e "        \e[1;94m Alt  - v \e[0m \e[1;34m   ┊┊┊ \e[0m \e[1m Open \e[0m in VSCode"
    echo -e "        \e[1;94m Ctrl - o \e[0m \e[1;34m   ┊┊┊ \e[0m \e[1m Open \e[0m in Default Program"
    echo

    echo -e "    \e[3m\e[1m• Compatability \e[0m "
    echo
}


# *** Read First Argument
readFirstArgument () {

    if [[ "${1:-}" == "-h" ]] || [[ "${1:-}" == "--help" ]] || [[ "${1:-}" == "" ]]; then
        Help && exit 0
    fi

}
# *** Skim and Grep, the important stuff
SkimNotes () {

    ## Change directory if One was specified, exit if no directory exists
   
    cd "${1}"

    FILE="$(SkimGrep)"
    if [[ $FILE != "" ]]; then
        realpath $FILE && exit 0
    fi

    exit 0

}

# **** Skim with Grep
SkimGrep () {

sk --ansi -i -m -c 'rg -l -t markdown --ignore-case "{}"'    \
    --preview "bat {} 2> /dev/null                             \
        --color=always --line-range :500                       \
        --terminal-width 80                                    \
        --theme=TwoDark                                       |\
            rg --pretty --colors  --context 20 {cq}                \
                --no-line-number --ignore-case                     \
                --colors 'match:fg:21,39,200'                      \
                --colors 'line:style:nobold'                       \
                --colors 'match:style:bold'                        \
                --colors 'match:bg:30,200,30'"                     \
     --bind 'ctrl-f:interactive,pgup:preview-page-up,pgdn:preview-page-down'    \
     --bind 'ctrl-w:execute-silent(echo {}    |\
         xargs realpath                       |\
         xclip -selection clipboard)'                                           \
     --bind 'alt-w:execute-silent(echo {} | xclip -selection clipboard)'        \
     --bind 'alt-v:execute-silent(code -a {}),alt-e:execute-silent(emacs {})'   \
     --bind 'ctrl-o:execute-silent(xdg-open {})'                                \
     --bind 'alt-y:execute-silent(cat {} | xclip -selection clipboard)'         \
     --bind 'alt-o:execute-silent(cat {}      |\
         pandoc -f markdown -t html --mathml  |\
         xclip -selection clipboard)' \
     --bind 'alt-f:execute-silent(echo {}        |\
         xargs dirname                           |\
         xargs cd; cat {}                        |\
         pandoc -f markdown -t dokuwiki --mathml |\
         xclip -selection clipboard)'            \
     --color=fg:#f8f8f2,bg:-1,matched:#6272a4,current_fg:#50fa7b,current_bg:#381070,border:#ff79c6,prompt:#bd93f9,query:#bd93f9,marker:#f1fa8c,header:#f1fa8c

}


# * Call Main Function
main "${@}"

```


## Ryan's *FISH* RC

> *FISH* doesn't have a `~/.fishrc`, instead it has a `~/.config/fish/config.fish`, this is in line with new standards ==SOURCE???==, for example `emacs 28.0` makes this change.
{.is-info}

This is what I have in my *FISH* startup, [you can see it on *GitHub*](https://github.com/RyanGreenup/DotFiles/tree/master/Shells).

```bash
set PATH /home/ryan/.local/bin $PATH
set PATH /home/ryan/bin $PATH
set PATH /home/ryan/.cargo/bin $PATH

# Defined in - @ line 1
function f --wraps='cd ; exa -RGL 3' --description 'alias f=cd; exa -RGL 3'
  cd $argv ; exa -TL 2 ; exa ;
end


## Search for installable Packages
function f --wraps='cd ; exa -RGL 3' --description 'alias f=cd; exa -RGL 3'
  cd $argv ; exa -TL 2 ; exa ;
end


## Better LS
function ls! --wraps='ls -ultrah' --description 'alias ls!=ls -ultrah'
  ls -ultrah $argv;
end


## Easier Xclip
function x --wraps='xclip -selection clipboard' --description 'alias x=xclip -selection clipboard'
  xclip -selection clipboard $argv;
end


## Cadmus Bindings
function ns --wraps='cadmus note search' --description 'alias ns=cadmus note search'
  cadmus note search $argv;
end


function nf --wraps='cadmus note find' --description 'alias ns=cadmus note find'
  cadmus note find $argv;
end


function wa --wraps='cadmus misc w' --wraps='cadmus misc wa' --description 'alias wa=cadmus misc wa'
  cadmus misc wa $argv;
end


function wr --wraps='cadmus misc w' --wraps='cadmus misc waR' --description 'alias wr=cadmus misc wR'
  cadmus misc wR $argv;
end

function no --wraps='cadmus misc code' --description 'alias no=cadmus misc code'
  cadmus misc code $argv;
end

function ng --wraps='cadmus misc atom' --description 'alias ng=cadmus misc atom'
  cadmus misc atom $argv;
end
```