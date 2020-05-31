---
title: Using BTRFS Subvolumes and `dm_crypt`
description: 
published: true
date: 2020-05-31T03:35:41.221Z
tags: 
---

# Setting up BTRFS File System
There are x basic steps (they were addapted from [this wiki post](https://wiki.archlinux.org/index.php/User:Altercation/Bullet_Proof_Arch_Install#Encrypt_System_Partition):

1. Set up `dm_crypt`
2. create a `btrfs` partition
3. create subvolumes
4. unmount everything and mount the subvolumes instead
5. install to the subvolumes
6. generate the fstab.

## Set up BTRFS
Boot of the live usb and investigate the filesystem with `lsblk`, you'll get something like:

```bash
sda      8:0    0 8G  0 disk 
├─sda1   8:1    0   499M  0 part 
├─sda2   8:2    0     7G  0 part /

sdb      8:16   0   1.8T  0 disk 
├─sdb1   8:17   0 264.6G  0 part /
└─sdb3   8:19   0   1.6T  0 part 
```
but you'll probably have `nvme0n1p3` or something like that, on my laptop i had `nvme0n1p7` as the partition I wanted to put *Arch* on so that's what i'll use here.



### Create the BTRFS Sub Volumes


#### Format the Drive
now you have to take the new volume you just mounted from the encryption and format it, we'll format it with the label `system` which might seem ambiguous but in practice it won't be an issue.
```bash
mkfs.btrfs --force --label system /dev/mapper/system
```

#### Set options
now we want to temporarily mount this so we can make subvolumes, the idea of subvolumes is that the will allow us to use snapshots (and if we use the names `@home` and `@root` we can use *TimeShift* snapshots which gives us a nice *GUI*.

First however we'll set some variables to describe options so things don't get too confusing with long commands later:


```bash
o=defaults,x-mount.mkdir
o_btrfs=$o,compress=lzo,ssd,noatime
```

#### Mount the Drive
now we can use those to mount the drive we made, we called it `system` so rather than specifying `/dev/mapper/system` (which is the unlocked point for `dev/nvme0n1p7`) we can just say `system` which is a little less confusing:

```bash
mount -t btrfs LABEL=system /mnt
```
#### Create the Subvolumes
Now all we have to do is to create subvolumes (you'll notice I called them `@root` and `@home` this is necessary for *TimeShift* to work with them, but the names are confusing *IMO* because you're never sure if you have to escape the `@` character, I don't think you do though.)

```
btrfs subvolume create /mnt/@root
btrfs subvolume create /mnt/@home
btrfs subvolume create /mnt/@snapshots
```

### Unmount drive and mount the subvolumes instead
Now just unmount everything and remount the subvolumes:

```bash
umount -R /mnt 
mount -t btrfs -o subvol=@root,$o_btrfs LABEL=system /mnt

## Notice here that these subvolumes are both being 
## mounted underneath the root subvolume:
mount -t btrfs -o subvol=@home,$o_btrfs LABEL=system /mnt/home
mount -t btrfs -o subvol=@snapshots,$o_btrfs LABEL=system /mnt/.snapshots
````

### Install Arch
Now install the base *Arch* system using `pacstrap` which should install to `/` which corresponds to the subvolume `@root`, just follow the [Installation Guide](https://wiki.archlinux.org/index.php/Installation_guide#Partition_the_disks) up until the `fstab`.

### Create the `fstab`
To create the `fstab` just run the following:

```bash
genfstab -L -p /mnt >> /mnt/etc/fstab
```

### Refind
To allow kernel auto detection on a Btrfs subvolume uncomment and edit also_scan_dirs in refind.conf.

```bash
## esp/EFI/refind/refind.conf
## ...
also_scan_dirs +,@root/boot
```
> here `@root` represents the subvolume that contained the root file system

> Again, if you were doing encryption, an easy way to do it is to mount efi at /boot and that way all the arch kernel stuff goes in there, meaning rEFInd will see a linux kernel inside esp/EFI/ (because in Arch thats /boot) and then the kernel parameters will tell it to open the `dm_crypt`.

#### Kernel Parameters
You will also need to specify the `@root` subvolume in the kernel parameters:

```bash
## /boot/refind_linux.conf

"Boot using standard options"  "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw rootflags=subvol=@root initrd=@root/boot/initramfs initrd=@root/boot/initramfs-%v.img"
```

### Encryption hook
You will need to create a hook for the encryption


Now `fstab` should have done everything correctly and you're done, now you just need to finish the install and then setup the  [boot loader and microcode](/linux/installArch).

## rEFInd
Install `refind` and then make sure to mount the `esp` (probably to `/efi` but if you're doing full disk encryption do `mount /dev/sda1 /boot` that way all the boot stuff will be stored on the efi partition unencrypted.

run `refind-install` and it should do most of the work, but, if you're in a `chroot` environment all the kernel parameters will be wrong.

### Kernal Parameters
So the trick with the kernel parameters is remembering to tell linux about the subvolume, execute the following and then do `:e /boot/refind_linux.conf`:

```bash
blkid -s UUID -o value /dev/nvme0n1p7 | vim -
```
Put the kernel parameters in like this [as described in the arch-wiki](https://wiki.archlinux.org/index.php/REFInd#Btrfs_subvolume_support):

```bash
"Boot using default options"     "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rootflags=subvol=@root rw add_efi_memmap initrd=@root/boot/intel-ucode.img initrd=@root/boot/amd-ucode.img initrd=boot\initramfs-%v.img"
"Boot using fallback initramfs"  "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rootflags=subvol=@root rw add_efi_memmap initrd=@root/boot/intel-ucode.img initrd=@root/boot/amd-ucode.img initrd=@root/boot/initramfs-%v-fallback.img"
"Boot to terminal"               "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rootflags=subvol=@root rw add_efi_memmap initrd=@root/boot\intel-ucode.img initrd=@root/boot/amd-ucode.img initrd=@root/boot/initramfs-%v.img systemd.unit=multi-user.target"
```

### Make rEFInd Scan Subvolumes
Now the next issue is that refind isn't gonna look for subvolumes by default (which is absurd, why not make it simple), it also doesn't know how to interpret the `%v` above, so we can fix that by editing `esp/EFI/refind/refind.conf`:

```bash
## esp/EFI/refind/refind.conf
timeout 20                                     # Time
#include themes/rEFInd                         # Look for themes
extra_kernel_version_strings linux-lts,linux   # Interpret %v
also scan_dirs +,@root/boot                    # Look for subvolumes
use_graphics_for  windows                      # Something about a simpler 'mac-style' behaviour
```

## Encryption
I could not get full disk encryption to work with rEFInd and `btrfs`, I just gave up, i'll use `ecryptfs` later on `~/home` and deal with full disk encryption later, the focus at the moment should be robust system-restore points using `btrfs`.

I think though the reason I was having trouble was because I hadn't told refind to scan the subvolumes.

### Encrypt the Partition
Encrypt the partition by doing:

```bash
mkfs.btrfs --label cryptsystem /dev/nvme0n1p7
cryptsetup luksFormat --align-payload=8192 -s 256 -c aes-xts-plain64 /dev/disk/by-partlabel/cryptsystem
```

In my case I couldn't get that to work so I didn't use labels which would have been nicer:

```bash
cryptsetup luksFormat --align-payload=8192 -s 256 -c aes-xts-plain64 /dev/nvme0n1p7
```

Then open that partition and give it a name, the name chosen here is `system` and this means when it is mounted by `cryptsetup` it will end up in `/dev/mapper/system`:

```bash
cryptsetup open /dev/disk/by-partlabel/cryptsystem system
```











