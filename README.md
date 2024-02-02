# slackware

Slackware install on Lenovo p1 gen 4

> After installing goto shell

## GRUB

```bash
chroot /mnt
source /etc/profile

modprobe efivarfs
mount -t efivarfs efivarfs /sys/firmware/efi/efivars
efibootmgr

mount /dev/nvme0n1p1 /boot/efi

grub-install --target=x86_64-efi --efi-directory=/boot/efi/ --bootloader-id=slackware

grub-mkconfig -o /boot/grub/grub.cfg

umount -a
reboot
```




## Extra

https://sbopkg.org/downloads.php

Download by clicking here (prebuild package)

As root:
```bash
installpkg sbopkg-0.38.2-noarch-1_wsr.tgz

sbopkg
```

sync

Search for the libconfig package and install it.
Search for sboui and install it.
