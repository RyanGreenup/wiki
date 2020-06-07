---
title: Install Arch Linux
description: 
published: true
date: 2020-06-06T14:45:42.765Z
tags: 
editor: undefined
---

# Installation Notes
## BTRFS
Make sure to use `btrfs` for better integration with *TimeShift*

## EFI
Double Check where to put *EFI* stuff, nowdays it should go in `/efi`, I think this has changed recently but this is now the standard.

## Set up SubVolumes
Ok just [read the notes on using btrfs Subvolumes I've made here](/linux/arch/btrfs_subvolumes_and_dmcrypt)

## Grub
I found with grub I had to do this

```bash

grub-install --target=x86_64-efi --bootloader-id=GRUB --efi-directory=/boot/efi --no-nvram --removable
grub-install --target=x86_64-efi --bootloader-id=GRUB --efi-directory=/boot/efi
```

## Microcode
Leave out `intel-microcode` at first just to see if it causes any issues.


 So I wasn't having luck with `grub` because it just wouldn't install `refind` is a lot simpler and I prefer that it watches for changes so I don't have to remember to hit `update-grub`.
 
 To get `refind` working through the live USB do:
 
 ```bash
 mount /dev/nvme0n1p7 /mnt
 mount /dev/nvme0n1p1 /mnt/efi
 arch-chroot /mnt
 pacman -S refind
 refind-install
 ```
 
 What this does is specify kernel parameters in `/boot/refind_linux.conf` as described [here](https://wiki.archlinux.org/index.php/Kernel_parameters#rEFInd), but, those parameters correspond to the *ISO* not the actual OS, so, you will need to go in there and edit them manually.
 
 First List the drives by UUID ([as described here](https://wiki.archlinux.org/index.php/Persistent_block_device_naming#by-uuid)), the drive your interested in is the one to which `pacstra` was pointed, i.e. the OS drive, pipe the output to vim:
 
 ```bash
 pacman -S vim
 # blkid -s PARTUUID -o value /dev/sda1 | vim - 
 blkid -s PARTUUID -o value /dev/nvme0n1p7 | vim -
  ```
  > There is a difference between UUID and PARTUUID, be aware of that, the kernel paramemters need to point to `PARTUUID`, although `LABEL` is supported in the kernel parameters it ends up looking for the `UUID` and nothing happens, you MUST use the `PARTUUID` in the kernel parameters.
 > > PARTUUIDs are a component of GUID Partition Tables (GPT) which are a replacement for Master Boot Record (MBR) related disk partitioning. (i believe ` /etc/fstab ` can use either so be aware
  
 
 ### Specify the Kernel Parameters {.tabset}
 If you're using `btrfs` you'll have to use kernel paramters with subvolumes specified as described in [Using BTRFS Subvolumes](/linux/arch/btrfs_subvolumes_and_dmcrypt)
 
 #### Without Encryption
 
 Now from within vim press <kbd>Ctrl</kbd>+<kbd>w</kbd> <kbd>v</kbd> (`C-w v`) to split the window, <kbd>y</kbd>ank the *UUID* to the clipboard and then `:e /boot/refind_linux.conf` to get up the kernel parameters that `refind` will use,put the following into the file (as described [here](https://wiki.archlinux.org/index.php/REFInd#refind_linux.conf)):
 
 ```
 "Boot using default options"     "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw add_efi_memmap initrd=boot\intel-ucode.img initrd=boot\amd-ucode.img initrd=boot\initramfs-%v.img"
"Boot using fallback initramfs"  "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw add_efi_memmap initrd=boot\intel-ucode.img initrd=boot\amd-ucode.img initrd=boot\initramfs-%v-fallback.img"
"Boot to terminal"               "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw add_efi_memmap initrd=boot\intel-ucode.img initrd=boot\amd-ucode.img initrd=boot\initramfs-%v.img systemd.unit=multi-user.target"
 ```
 > omit the `amd-ucode.img` obviously, you'd only use that if the microcode was for that processor.
 
 #### With Encryption
 If however you used `cryptsetup` as described in [BTRFS Subvolumes](/linux/arch/btrfs_subvolumes_and_dmcrypt), you will need to do something different (as discussed [on this wiki page](https://wiki.archlinux.org/index.php/User:Altercation/Bullet_Proof_Arch_Install#Encrypt_System_Partition):
 
 ```bash
 # /boot/refind_linux.conf

"Boot with standard options"  "rd.luks.name=*FILL IN UUID FROM PARTITION*=cryptsystem root=UUID=*UUID FROM encrypted root subvolume* rootflags=subvol=@root initrd=/intel-ucode.img initrd=/initramfs-linux.img"
 ```
 
 Now you're not out of the woods yet, that kernel parameter had a `%v` call, this marks a variable that will be expanded to match the kernel, this is disabled by default in *Arch* and you'll need to enable it by following [these](https://wiki.archlinux.org/index.php/REFInd#For_kernels_automatically_detected_by_rEFInd) instructions:
 
 1. open `/efi/EFI/refind/refind.conf` with vim
 2. simply uncomment the lin e that reads like this:
    ```bash
    extra_kernel_version_strings linux, linux-fallback
    ```
 Now reboot and it should let you get into *Arch*, what you should do now is pass the kernel parameters for the intel microcode as described [here](https://wiki.archlinux.org/index.php/Microcode#rEFInd).
 
 
 Now you should be good to go now, but, I had also to pass a kernel paramater because of a bug as described [here](https://bbs.archlinux.org/viewtopic.php?id=251157) but I think that was unnecessary, I should instead refer to [the laptop page on the wiki](https://wiki.archlinux.org/index.php/Lenovo_ThinkPad_X1_Carbon_(Gen_7)#Audio)
 
 ### GUI
 #### Display Server
 + Can I installl both `xorg` and *Wayland* and run one or the other?
   + I need `xorg` for *Pop-Shell* but I'd rather use the newer *Wayland*.
 #### Window Manager
 + Can I use `i3` with:
   + Pantheon
   + Cinnamon
   + KDE
   + XFCE
   + Gnome?
 + Is there a way to get more features in i3?
 #### Desktop Environment
 + Does Pantheon Work?
 + Does Cinnamon Work?
 + Does Gnome3 with Pop-Shell Work?
 
 
 ## Set up Snapper
 Finally set up snapper as described [here](file://~/Notes/Org/roam/20200524210841-btrfs.org)
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 3
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 3
 
 
 
 
 
 
 