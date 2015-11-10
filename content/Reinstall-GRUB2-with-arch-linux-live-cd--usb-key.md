---
title: Reinstall GRUB2 with arch linux live cd / usb key
author: Tim Kleinschmidt
date: 2013-03-30 18:23
category: Linux
---

So I had to reinstall my Windows 8 in my dual boot system with Arch
Linux. After the reinstall I had the default boot manager of Windows
back in place of GRUB2.

My way to fix it, was to install on my USB key the current live CD of
archlinux [Download here][#f1]. Burn it to CD or copy it to your USB key with

``` sh
    dd bs=4M if=/path/to/archlinux.iso of=/dev/sdx
```

After the installing of the live CD to my USB key. I was restarting my
PC to boot from it. Afterwards I got the default arch Linux shell.

* * * * *

1.  I was creating a root point for my root disk in /mnt/root/

``` sh
    mkdir /mnt/root/
```

2.  Now I can mount the root partition to this point

``` sh
    mount /dev/sdXX /mnt/root
```

3.  Now I had to change the root. This command also adds the necessary
    folders like (proc, dev,…)

``` sh
    arch-chroot /mnt/root
```

4.  I have a separate boot partition so I had to mount this also to my
    chroot system

``` sh
    mount /boot
```

5.  Regenerate the **grub.cfg**

``` sh
    grub-mkconfig -o /boot/grub/grub.cfg
```

6.  So, it’s nearly done! I had only to install Grub back in the MBR

``` sh
    grub-install /dev/sdXX
```

Last not but least. Rebooted and it was working

[#f1]: https://www.archlinux.org/download/ "Current live cd from Archlinux"
