---
title: WikiJS Git Integration
description: 
published: true
date: 2020-05-31T04:12:56.224Z
tags: git
---

Basically follow [the
documentation](https://docs.requarks.io/storage/git), strictly, but
instead of the path use the contents of the key, everything else MUST be
exactly as described here

 | Parameter                | Value                                                                                                      | 
| ---                      | ---                                                                                                        | 
| Authentication Type      | SSH                                                                                                        | 
| Repo URL                 | `git@github.com:RyanGreenup/wiki.git`                                                                       | 
| Branch                   | master                                                                                                     | 
| SSH Private Key Mode     | Content  [^why]                                                                                      | 
| SSH Private Key Contents | Put the key contents in here, so like =cat github.pem=                                                     | 
| Username                 | Absolutely MUST be left blank, if you ever put something here see [*Removing Bad Config*](#Removing-Bad-Config)  to reset it          | 
| Email                    | Apparently the email must be the same as what's linked to GitHub, no clue but I did that to save heartache | 
| Local Repo Path          | I don't think this matters, it's usally =./data/repo=                                                      | 
| Synd Direction           | Bi-Directional                                                                                             | 

------

When you add the public key (i.e. `github.pem.pub`) to *GitHub*, make
sure you give it write permissions as well.

## Removing Bad Config

If you create a bad config WikiJS won\'t wipe it out which is super
annoying.

1.  List the docker containers:

    ``` {.bash}
    sudo docker container ls
    ```

2.  ssh into the docker container:

    ```bash
    sudo docker exec -it \ /bin/bash
    ```
    
1.  go to the repo (probably `/wiki/./data/repo`) and `rm -rf repo`

2.  exit the container and restart it

    ```bash
    exit sudo docker restart \
    ```

## Adding / Importing Files
The only way I could get it to work is if I first removed the YAML from the =.md= file, then let *WikiJS* import it.

After that I could modify the YAML however I liked

### Tags
Yeah Don't Touch these

### Renaming
Renaming Works as well

### YAML Title
Changing the YAML Title does work though.

## Footnotes

## File Names
Dont use Camel Case or Snake Case, spaces are indicated by hyphens just like lisp, e.g.:

| File Name | Wiki JS Interpertation |
|---|---|
| `foo-bar` | `foo bar` |
| `foo_bar` | `foo_bar` |
| `foobar` | `foobar` |
|`foo bar` | I don't know, and I don't care, this would only make life more difficult and make links less useable |

[^why]: If you do a path you\'re going to have to `ssh` into the docker
    container to create the key, if you have `ssh` into whatever is
    running the container this can get confusing so don\'t do that.
