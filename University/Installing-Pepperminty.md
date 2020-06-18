---
title: Installing Pepperminty
description: 
published: true
date: 2020-06-17T13:37:35.030Z
tags: 
editor: undefined
---

# Installing Pepperminty
So follow [these](https://starbeamrainbowlabs.com/labs/peppermint/__nightdocs/04-Getting-Started.html) instructions.

## PHP and Apache
Set up an apache server with support for PHP, confirm that the php works, just follow the *arch Wiki* guide.

## Install Modules
It isn't clearly specified, but you need to

1. install the `php` modules through the package manager
2. enable them in `/etc/php/php.ini`

## Block Access
Next you'll need to block access to the `peppermint.json` file, you could acheive this with the following in the *Apache* config:

```
## /etc/http/conf/config ## Arch
## /etc/apache2/sites-available/000-default.conf ## Ubuntu


## This blockes by file name, it doesn't want a path which is quite confusing, but in practice it's usually fine.
    ## /srv/http/peppermin/peppermint.json

<Files "peppermint.json">
AllowOverride None
Order Deny, Allow
Deny from All
</Files>
// Extra Sanity
RedirectMatch 404 /srv/http/peppermint/peppermint.json
```