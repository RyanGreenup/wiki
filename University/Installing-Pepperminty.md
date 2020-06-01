---
title: Installing Pepperminty
description: 
published: true
date: 2020-06-01T15:46:18.739Z
tags: 
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


<Files "/srv/http/peppermint/peppermint.json">
AllowOverride None
Order Deny, Allow
Deny from All
</Files>
// Extra Sanity
RedirectMatch 404 /srv/http/peppermint/peppermint.json
```