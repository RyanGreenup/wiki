---
title: Installing Wiki JS for Local Use
description: How to install WikiJS for use as a Personal Wiki
published: 1
date: 2021-02-22T13:45:06.891Z
tags: notetaking
editor: markdown
dateCreated: 2021-02-22T13:26:09.837Z
---

# Installing Wiki JS for Local Use

1. Install `node`

2. [Install elasticsearch](https://wiki.archlinux.org/index.php/Elasticsearch) and use [enable](https://wiki.archlinux.org/index.php/systemd#Enabling) the daemon
   
   - record the port that it's using [^1]

3. unpack the tarball and set up as [described in the documentation](https://docs.requarks.io/install/linux)
   
   - Modify the `yml` so it looks like this:

    ```yml
    db:
      type: sqlite
      # SQLite only:
      storage: db.sqlite
    ```

- Consider modifying the IP address to listen on (see line ~100, look for variable `bindIP`
  
  | ip        | description                       |
  | --------- | --------------------------------- |
  | 0.0.0.0   | Anybody on the network can see it |
  | 127.0.0.1 | Only the computer can see it      |
4. Run `node server`
5. go to settings --> search, choose elastic search, choose the version and set the the server to localhost and the port to what elasticsearch is running on [^1]
6. In the `git` section, choose `basic` authentication and point the wiki to the `http` address of the `git` repo.
   - Then press all the import buttons below
   - it worked for GitHub when the username and password was provided
     - The open question is whether or not it will work well for a local repo using a `py`/`node` server.
       
       <details>
       <ul><li> The solution here would be a script to start seperate node servers on the repo and on the wiki, then all the notes would be imported/exported from the wiki into that directory seamlessly </li>
        <li> merge conflicts could be handled with <p><a href="https://meldmerge.org/">meld</a></p>
       </li></ul>
       </details>

[^1]: [the default](https://wiki.archlinux.org/index.php/Elasticsearch#Configuration) is `9200`
