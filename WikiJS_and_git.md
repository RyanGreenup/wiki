---
title: WikiJS Git Integration
description: 
published: true
date: 2020-09-22T06:33:01.186Z
tags: 
editor: undefined
---


Basically follow [the documentation](https://docs.requarks.io/storage/git), strictly, but instead of the path use the contents of the key, everything else MUST be
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

### Deleting Files
You might find life easier if you delete files from inside WikiJS, but, With 3/4 syncs and a `touch filename.md` in between it eventually worked but YMMV 


## File Names
Dont use Camel Case or Snake Case, spaces are indicated by hyphens just like lisp, e.g.:

| File Name | Wiki JS Interpertation |
|---|---|
| `foo-bar` | `foo bar` |
| `foo_bar` | `foo_bar` |
| `foobar` | `foobar` |
|`foo bar` | I don't know, and I don't care, this would only make life more difficult and make links less useable |

## Potential Gotchyas
Images will be imported, but /WikiJS/ doesn't use folders (per se), it uses a flat folder structure with long names where any words delimited by `/` are treated like folders.

In practice this will behave exactly the same, except, for when you reference an image trying to use `./`, then it will obviusly not catch it.

See for example [the SWA PCA article](/University/Social_Web_Analytics/05_Visualisation_PCA_MDS):

```markdown
![20200423103234597_1312556818.png](./20200423103234597_1312556818.png)
![20200423103234597_1312556818.png](/University/Social_Web_Analytics/media/20200423103234597_1312556818.png)
```
> In this example the top image image will not render because of the naming weirdness, but, the bottom will, you can fix this by manually re-inserting the links but it's a pita.
{.is-danger}

### How to fix this
> Currently I'm just re-adjusting the images, but, this means that the wiki WILL BE INCOMPATIBLE, with waht I'm doing, because the images will never line up.
{.is-danger}
1. Use a flat file structure and change where root is mounted, then the images will render locally?
  * This sounds awful
2. Put all the images on a local server, see for instance this image:

  * ![Example of Image on a server](https://ryansnotes.org/webdav/screenshot_from_2020-05-10_14-35-35.png =100x)
  
  * See [Hosting Images](/hosting-images.md)
  
  
> images cannot be included relatively, e.g. `./image.png` will fail, so will, `./filename.md`, however `/file.md` will work, so im not sure how i can use that to make this work bInwant to include links just like you would in the `git` repo see e.g.:

> * [Note-Taking-Applications](./University/Note-Taking-Applications.md)
> * [hosting-images](hosting-images)
> * [./hosting-images.md](./hosting-images.md)
> * [/hosting-images.md](/hosting-images.md)
> * [hosting-images.md](hosting-images.md)

> observe that these work in the preview pane in the ditor but not in the actual page, this is clearly a bug  
{is-warning}



## Footnotes

[^why]: If you do a path you\'re going to have to `ssh` into the docker
    container to create the key, if you have `ssh` into whatever is
    running the container this can get confusing so don\'t do that.
































