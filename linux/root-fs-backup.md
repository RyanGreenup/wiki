---
title: root file system backup
description: 
published: true
date: 2020-06-06T14:45:44.370Z
tags: 
editor: undefined
---

The reason of the advices to not backup the "`/`" folder is this: typically, there are many virtual (and, sometimes, physical) filesystems attached to it. A virtual filesystem is like a `/proc`: it doesn't have physical files on the hard disk, instead listing/reading/writing their file structure manipulates some data structures of the kernel. For example, writing 1 into `/sys/bus/pci/rescan` doesn't write anything to anywhere on a hard disk, instead it re-scans the PCI bus for new devices.

Backing them up would be meaningless or they might be even harmful.

If your goal is to back up *everything*, then the best what you can do is that you *back up everything*. However, backing up `/` might be problematic because of the problem above.

However, there is a simple trick to solve that. Linux knows the thing so-named [bind mount][1]: it means, that you can mount a filesystem multiple times.

For example, a

    mount /dev/sda7 /mnt/root

will mount your root filesystem (considering if your root is, for example, `sda7`) to the directory `/mnt/root`. You will see everything in it, *except any sub-mounts, including the virtual filesystems*.

The trick is this: *after that, you can safely backup `/mnt/root` with any tool you wish to, including `rsync`*.

Note also, this is only a recursive file copy. You have no protection for possible file inconsistency issues what happen. Imagine if a database has two files, for example, `/var/lib/postgresql/11/main/base/13731` and `/var/lib/postgresql/11/main/base/13732` which refer to eachother. If the database engine writes something into the first and to the second, *while your backup process runs*, then it is possible that the first will be backed up and the second won't. Thus, your database will become crap after a restoration.

This is also a reason, why you will probably find contra-arguments (sometimes quite vehement ones) against backing up your system on this way. However, in practical, user-level use cases, a real problem such this exists only very rarely, maybe the most typical one is when you are playing with a database for some web development task. In a home environment, I simply ignore this problem. In a professional environment, it is practical to use another, different backup for your data which is sensitive for this.

  [1]: https://unix.stackexchange.com/questions/198590/what-is-a-bind-mount