# slackware
Slackware install on Lenovo p1 gen 4


## GRUB

```bash
chroot /mnt
source /etc/profile

modprobe efivarfs
mount -t efivarfs efivarfs /sys/firmware/efi/efivars
efibootmgr

mount /dev/nvme0n1p1 /boot/efi

grub-install --target=x86_64-efi --efi-directory=/boot/efi/ --bootloader-id=slackware
```
