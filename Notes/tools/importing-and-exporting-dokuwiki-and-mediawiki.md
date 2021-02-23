---
title: Importing and Exporting Mediawiki and Dokuwiki
description: Tecniques and strategies to importing and exporting from dokuwiki
published: true
date: 2021-02-23T02:08:08.800Z
tags: 
editor: markdown
dateCreated: 2021-02-23T02:08:08.800Z
---

# Exporting and Importing from Dokuwiki and MediaWiki

## Dokuwiki

This is assuming that the [Mathjax
Plugin](https://www.dokuwiki.org/plugin:mathjax) is installed [^1].

See
[using make and falkon to live preview dokuwiki](using make and falkon to live preview dokuwiki)

### Summary

-   ***Import***
    -   Go into HTML+Mathjax first, when that works turn that into
        Dokuwiki and it should just work.
        -   From org-mode `C-c C-c e h H V G y` then
            `x -o | pandoc -f html -t dokuwiki | x`
        -   From Markdown+Mathjax[^2]
            `x -o | pandoc -f markdown+raw_tex -t html --mathjax -s   | pandoc -f html -t dokuwiki | x
            `
    -   If not use the filters described below
-   ***Export***
    -   Going straight to `org-mode` seems to work, then export that
        -   `x -o | pandoc -f dokuwiki -t org | cat - <(echo "#+OPTIONS: H:6") | pandoc -f org -t markdown | x`
        -   When exporting org-mode from emacs you must have
            `#+OPTIONS: tex:t` as well as `#+OPTIONS: H:5` (using
            ox-markdown is usually better than pandoc).
    -   Append `&do=export_xthmlbody` to the page and download using
        `<kbd>Ctrl</kbd>+<kbd>s</kbd>`{=html}, with that downloaded file
        use pandoc to recognise the math inside the `<p>` tags like so:
        `pandoc downloaded.html -f html+raw_tex+tex_math_dollars+tex_math_single_backslash -t html --mathjax -s  --extract-media ./media  -o out.html
        `, this is arguably the simplest approach [^3].
    -   If not just use `render.php` to get a html `      # HTML
              x -o | sudo php /srv/http/dokuwiki/bin/render.php |\
              pandoc -f html+raw_tex+tex_math_single_backslash+tex_math_dollars -t html -s --mathjax -o /tmp/file.html

              # LaTeX
              x -o | sudo php /srv/http/dokuwiki/bin/render.php |\
              pandoc -f html+raw_tex+tex_math_single_backslash+tex_math_dollars -t latex
        `{.bash}
    -   See also
        [Static Html Dump of Dokuwiki](Static Html Dump of Dokuwiki)

Current Quick Scripts are:

-   `~/bin/dw2org`
-   `~/bin/html2dw`
-   `/home/ryan/bin/ImportHtml2Dokuwiki.sh`
-   `~/bin/pandoku`
    -   As a fallback

### Import

#### Command Line Text

There are two pathways into dokuwiki with pandoc:

-   From Mathjax HTML, which just works (recommended)
-   From org-mode using a filter

#### HTML File

Importing a HTML+Mathjax file with pandoc seems to leave the math
untouched so that\'s not an issue, just do:

``` {.bash}
pandoc input.html -t dokuwiki
```

##### Media

It is worth noting however that relative links to media inside
`/dokuwiki/data/pages/` actually go to `/dokuwiki/data/media`. This is
super confusing but fixing it with symlinks makes the media manager have
a bunch of txt files in it so there isn\'t an easy fix.

Instead I just [wrote a
script](https://github.com/RyanGreenup/pandoku/blob/main/ImportHtml2Dokuwiki.sh)
that imports a HTML file into dokuwiki.

#### From Org Mode

Using the scripts located
[here](https://github.com/RyanGreenup/pandoku/blob/main/ImportHtml2Dokuwiki.sh):

``` {.bash}
cat file.org | pandoc -f org -t dokuwiki --filter dokuwiki_math_raw_filter.py
```

Or

``` {.bash}
cat file.md | pandoc -f markdown+raw_tex+tex_math_dollars+tex_math_single_backslash -t json | python json_fix_stdin.py | pandoc -f json -t latex
```

Or use the [ox-wk.el](https://github.com/w-vi/ox-wk.el) publishing
backend for org-mode.

### Export

#### Export the WikiText

##### Using Command Line Tools

Dokuwiki provides many [Comand Line
Tools](https://www.dokuwiki.org/cli), the `render.php` script can be
used to convert dokuwiki text to html. If the [Mathjax
Plugin](https://www.dokuwiki.org/plugin:mathjax) is used the
`render.php` script will not touch the math (otherwise it will so you
will need to have this plugin installed!).

``` {.bash}
sudo \
php /srv/http/dokuwiki/bin/render.php < /home/ryan/Sync/pandoc/file.dw |\
pandoc -f html+raw_tex+tex_math_dollars+tex_math_single_backslash -t latex
```

to go into html, remember to use the =-s \--mathjax= options like so:

``` {.bash}
sudo \
php /srv/http/dokuwiki/bin/render.php < /home/ryan/Sync/pandoc/file.dw |\
pandoc -f html+raw_tex+tex_math_dollars+tex_math_single_backslash -t html -s --mathjax -o /tmp/file.html
```

The `render.php` script was added in 2010, yet, in 2011 a
[dokucli.php](https://www.dokuwiki.org/tips:dokuwiki_parser_cli) script
was listed in the dokuwiki tips, I don\'t know what this brings to the
table though.

to use it create a `dokucli.php` file in
`/srv/http/dokuwiki/bin/dokucli.php` [^4] like so:

``` {.php}
<?php
if ('cli' != php_sapi_name()) die();

ini_set('memory_limit','128M');
if(!defined('DOKU_INC')) define('DOKU_INC',realpath(dirname(__FILE__).'/../').'/');
define('NOSESSION',1);
require_once(DOKU_INC.'inc/init.php');
require_once(DOKU_INC.'inc/common.php');
require_once(DOKU_INC.'inc/parserutils.php');


$source = stream_get_contents(STDIN);
$info = array();
echo p_render('xhtml',p_get_instructions($source),$info);
?>
```

Then to use it:

``` {.bash}
PATH_TO_DOKUWIKI="/srv/http/dokuwiki"
php $PATH_TO_DOKUWIKI/bin/dokucli.php < input.txt > output.html
```

This still does not seem to add the MathJax in, but the following does:

``` {.bash}
sudo php /srv/http/dokuwiki/bin/dokucli.php < file.dw |\
pandoc -f html+raw_tex+tex_math_dollars+tex_math_single_backslash -t html --mathjax
```

Why this works but using pandoc like this does not

`   <details>       <pre class="sourceCode bash">           <span id="cb1-1"><span class="bu">   pandoc file.dw -f dokuwiki -t html |\   pandoc -f html+raw_tex+tex_math_dollars+tex_math_single_backslash -t html --mathjax           </span>       </pre>   </details> `{=html}

is I think due to the fact that pandoc pollutes the math with `<br>`
symbols etc.

##### Using Pandoc

So the issue is that `pandoc` doesn\'t recognise the `$$` as math for
dokuwiki, going into HTML and then trying to use the
`+raw_tex+tex_math_dollars+tex_math_single_backslash` does not help
either. The only solution to use pandoc is to go into `org-mode` (and
maybe other formats like muse or textile) where the math is simply left
as is.

This doesn\'t seem like a robust solution.

##### Using Latexport plugin

I can\'t find anyway to use this from the command line, but, appending
one of the following to the end of the URL will give a latex copy of a
page:

-   `?do=export_latexport_tex`
-   `&do=export_latexport_tex`

#### Export the File

This is going to be the same as section
[\#portable-wiki-php](#portable-wiki-php) above but with some extra
steps to extract Media, this is on my todo list.

Actually this is easy, check out these two links:

1.  <https://www.dokuwiki.org/export>
2.  <https://www.dokuwiki.org/tips:export_html>

The following export options are available by default:

-   `&do=export_raw`
    -   Returns the page\'s source as `text/plain`
    -   Example: <https://www.dokuwiki.org/export?do=export_raw>
    -   If DokuWiki uses it as link to a new page
        wiki:export_do_export_raw then switch in the configuration area
        \'\' URL rewriting\'\' to DokuWiki.
-   `&do=export_xhtml`
    -   Returns the rendered page as simple XHTML without any
        navigational elements
    -   Example: <https://www.dokuwiki.org/export?do=export_xhtml>
    -   Example 2:
        <https://www.dokuwiki.org/doku.php?id=export&do=export_xhtml>
-   `&do=export_xhtmlbody`
    -   Returns the rendered XHTML of the page only.
    -   No head or body tags are added. No contenttype headers are sent.
    -   Useful to include the rendered output into some other website
    -   Example: <https://www.dokuwiki.org/export?do=export_xhtmlbody>

#### Images

##### With Local Server

If you spin up a local PHP server with:

``` {.bash}
cd /srv/http/dokuwiki
sudo php -S localhost:8888
```

then go to a dokuwiki page in firefox and append:

-   `&do=export_xhtml`, or
-   `?do=export_xhtml`

ad finally download that page, the downloaded HTML file will have the
original images and they will be resized using the HTML
`<img src="" width=42>` parameters.

The easiest way to download is to use the [single
file](https://addons.mozilla.org/en-US/firefox/addon/single-file/)
extension, but even just saving with
`<kbd>Ctrl</kbd>+<kbd>s</kbd>`{=html} is sufficient to get a HTML file
with the original images scaled in a similar fashion. Without a local
server this doesn\'t work, clearly a security measure implemented by
*Apache* to stop recursively retreiving files.

```{=html}
<!---
This could possibly be improved by using wget, but it doesn't seem to download the images as well, so just save the page in the browser I guess.

<code bash>
wget \
     --recursive \
     --no-clobber \
     --page-requisites \
     --html-extension \
     --convert-links \
     --restrict-file-names=windows \
     --domains website.org \
     --no-parent \
    --post-data="u=ryan&p=rectangle%20nearness%20brim%20crinkle%20vineyard%20unreached%20karaoke" \
    'http://localhost:8888/doku.php?id=predictive_modelling_with_python&do=export_xhtml'
</code>

--->

```
This could be used with[a shell
script](https://www.dokuwiki.org/tips:offline-dokuwiki.sh) to dump the
whole wiki, see [offline dokuwiki copy](offline dokuwiki copy)

##### Without Local Server

So images can get confusing, they can still be exported by appending
`&do=export_xhtml` to the wiki page and then using
[Monolith](https://github.com/Y2Z/monolith) or [single
file](https://addons.mozilla.org/en-US/firefox/addon/single-file/) to
get a self-contained HTML file [^5], but, there are two important things
to note:

1.  The image retreived will be the image provided on that page
    1.  i.e. if the image was scaled to 200 pixels on the html page, the
        export will also be scaled
2.  The hyperlink attached to that image will be preserved in that HTML
    file, which can be a bit confusing.

So there will be two images of concern the one from the HTML file and
the target of the link. It is not clear to me at the moment how I could
resize an image in the page and have the export provide the original
image with HTML scaling instructions [^6].

The HTML used to insert the image is:

``` {.html4strict}
<img src="/dokuwiki/lib/exe/fetch.php?w=200&amp;tok=089afc&amp;media=4b9f8411ad6ddada6fc93172a1121f41433a21d8.png>
```

If this could be modified with regex like so:

``` {.bash}
echo 'd8.png"><img src="/dokuwiki/lib/exe/fetch.php?w=200&amp;tok=089afc&amp;media=4b9f8411ad6ddada6fc93172a1121f41433a21d8.png" ' | rg 'w=\d+' -r ''
```

Before it was given to single file, we\'d be off to the races.

<http://username:password@localhost/dokuwiki>

I was able to curl the page down by using POST and Basic Auth like so:

``` {.bash}
curl -d "u=username&p=password" --cookie-jar cjar 'http://username:httpBasicPassword@localhost/dokuwiki/doku.php'
```

This cjar file can be reused like so:

```bash
curl --cookie ./cjar --cookie-jar ./cjar 'http://ryan:my%20http%20pass@localhost/dokuwiki/doku.php'
```

and contains the following:

```bash
# Netscape HTTP Cookie File
# https://curl.se/docs/http-cookies.html
# This file was generated by libcurl! Edit at your own risk.

#HttpOnly_localhost FALSE   /dokuwiki/  FALSE   0   DW84669e0b736a85c6eeda0cf5b0a2b382  cnlhbg%3D%3D%7C0%7C%2FXT8wknuTqVSoLeMeJrsqgKBAC0n4Cb9hzY%2BMkdjWlZelaBoZ11QBotcQwAZb%2Bbm21VDX6KP5qymesMuMaFOY0vg%2F%2B2sDaxZgAzSdx8b7KU%3D
#HttpOnly_localhost FALSE   /dokuwiki/  FALSE   0   DokuWiki    vd5ludt12vgp36aigaa591sd5v
```

##### Solution

-   Don\'t resize images when you include them to begin with
-   Include Images as a link to an external webDAV Server
    -   Downsize to this is that you will not be able to run dokuwiki
        offline
-   Manually change image links before exporting
    -   This could be automated, copy the text, run a script[^7], paste
        the text back, save, export and then revert.
-   Manually copy the images back out, this can be automated with some
    `bash` [^8]

## MediaWiki

### Import

you've gotta use the plugin, it works quite well but only on iOS

### Export

#### Export the Wiki Text

Just use `pandoc`

#### Export the Page

There is a similar thing to dokuwiki, just append `?action=render` to
the end of a page [^9]

See [this page
generally](https://www.mediawiki.org/wiki/Publishing_from_MediaWiki)

This can be wrapped with `~/bin/ImportHtml2Dokuwiki.sh` or the mediawiki
import function to pull in wikipedia pages.

## Downloading a Website

[Tikzit](https://tikzit.github.io/#paths) is a really nice program to
build simple TiKz diagrams quickly, it does not however provide docs as
a PDF, so to fix that I did the following:

``` {.bash}
# Use Wget to download the Website
wget --page-requisites --convert-links --wait=3 -e robots=off  --no-directories  'https://tikzit.github.io/#paths'

# Make an .org file because html often fails
pandoc -f html -t org index.html --extract-media="media" -o index.org

# Make LaTeX out of the Org File
pandoc -s --self-contained index.org --listings --toc -H ~/Dropbox/profiles/Templates/LaTeX/ScreenStyle.sty --pdf-engine=xelatex --pdf-engine-opt=-shell-escape -o /tmp/note.pdf ; xdg-open /tmp/note.pdf & disown

# Write the commands down for sanity sake
FILE="${~/Downloads/tikzit_Docs.sh}" && echo '#!/bin/bash' > "${FILE}"
history | head -n 10 | tac >> "${FILE}"
```

## Downloading Mediawiki

### Org Mode

So to import this I exported the org document like so:

``` {.bash}
# Change directory to note location
# cd "${HOME}"; cd "$(fd | sk | xargs dirname)"
cd ~/Notes/Org
# Make Temp directory
mkdir /tmp/0mw
# Use pandoc to extract the media
  # The media will now have absolute paths
pandoc Research-Outline.org --extract-media /tmp/0mw/media -o /tmp/0mw/out.org
# Change Directory to temp directory
cd /tmp/0mw/
# Media Directory MUST be Capitals and MUST NOT be prefixed with a `./`
pandoc out.org -f org -t html --mathjax -s --extract-media='Media' -o out.html
rm -r media out.org
zip -r Out.zip *
realpath Out.zip | x
```

This HTML file can then either be used wit the Media wiki Special pages
import HTML or with the `~/bin/ImportHTML2Dokuwiki` script that is
designed to replicate that. Link

The media directory can't be prefixed with `./` because the importer
will take the directory path from the html file and make it the name of
the media files but it will capitalise things.

So having a link `./media/pic.png` extract the image to a name of
`/Media/pic.png`, so not having a capital or using a `./` will break the
link in the html.

For the same reason you can't just do `--extract-media='./'`.

Pandoc cannot extract media that is relatively linked (which most would
be) unless it is in the same directory as the file.

#### Download Wikipedia

Append `?action=render` and then use *Firefox* or `wget`:

``` {.bash}
wget --page-requisites --convert-links --wait=3 -e robots=off  --no-directories 'https://en.wikipedia.org/wiki/Golden_angle?action=render'
```

-   `--page-requisites` will download images even if they go to Wikipdia
    File Links
    -   This is unlike *Firefox* which doesn't actually do that
-   `--convert links` \| `-k`
    -   will make the links to the downloaded images work
-   `-O` `filename.html` will put everything into a single file but does
    not work with images from *Wikipedia*.

## Related

-   [Locate Orphaned Media](Locate Orphaned Media)
-   [Talk:Fractal
    Dim](http://ryansnotes.org/mediawiki/index.php/Talk:Fractal-dimensions)
-   [Talk:Research
    Outline](http://ryansnotes.org/mediawiki/index.php/Talk:Research_Outline_for_Quantitative_Project)
-   [Automatically generating export file name from heading
    text](export_org_mode_per_heading)
-   [Monolith](https://github.com/Y2Z/monolith) A tool to turn a website
    into a single HTML file, really good for then importing into
    *Dokuwiki*.
-   [suan\'s instant markdown preview in vim](suan's instant markdown preview in vim)

#### Importing `.docx`

``` {.fish}
for i in (ls *docx)                                                                       
                       pandoc $i -o $i.html -s -t html --mathjax --extract-media ./media
                   end
for i in (ls *html)                                                                      
                       /home/ryan/bin/ImportHtml2Dokuwiki.sh $i
                   end
cp -r /tmp/dokuwiki_import/data /srv/http/dokuwiki/data
sudo chown -R http:http /srv/http/dokuwiki; sudo systemctl restart httpd    
php /srv/http/dokuwiki/bin/indexer.php -h   
```

[^1]:  The Mathjax plugin must be installed otherwise using `render.php`
    will alter the math environments, if it\'s installed it will *just
    work*\\(\^{\\mathrm{TM}}\\) See also
    [pandoku](https://github.com/RyanGreenup/pandoku/blob/main/ImportHtml2Dokuwiki.sh)
    for code that I was using while playing around with this

[^2]:  i.e. using `suan/vim-instant/markdown` or ReText

[^3]:  If you convert this to org-mode `pandoc` get\'s confused and
    makes images a link to the URL with the file name as a description,
    this needs to be fixed which is a little annoying

[^4]:  or `/var/www-data/` on *Ubuntu*

[^5]:  The media can then be extracted with
    `pandoc input.html -o html --mathjax --extract-media ./media`

[^6]:  i.e. something like `<a src="file.png" width=200>`

[^7]:  Some cleverness with `sed` required here

[^8]: 
    `cat pages/cost_function_of_classification.txt  | grep '{{.*}}' | rg -o --pcre2 '(?<={{\:).*.png' | sed 's!:!\/!' 
    `{.bash}

[^9]:  [Publishing from
    Mediawiki](https://www.mediawiki.org/wiki/Publishing_from_MediaWiki)
