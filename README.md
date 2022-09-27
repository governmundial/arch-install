# arch-install

`loadkeys es`

`ping 8.8.8.8`

**CTRL+C**

`iwctl`

`device list`

`station wlan0 get-networks`

`station wlan0 connect WIFINAME`

**TYPE THE WIFI PASSWD**

`station wlan0 show`

**CTRL+C**

`ping 8.8.8.8`

**CTRL+C**

`lsblk`

`cfdisk /dev/XXXX`

`CREATE PARTITIONS: ONE LARGE [/]; ONE 512M [/BOOT/EFI]; ONE 4-8G [SWAP]`

`lsblk`

`mkfs.vfat -F32 /dev/XXXX`

`mkfs.ext4 /dev/XXXX`

`mkswap /dev/XXXX`

`swapon`

`mount /dev/XXXX[/] /mnt`

`cp /etc/pacman.d/mirrorlist /etc/pacman.d/mirrorlist.bak`

`pacman -Sy`

`pacman -S pacman-contrib`

`rankmirrors -n 10 /etc/pacman.d/mirrorlist.bak > /etc/pacman.d/mirrorlist`

`cat /etc/pacman.d/mirrorlist`

`mkdir /mnt/boot`

`mkdir /mnt/boot/efi`

`mount /dev/XXXX[/boot/efi] /mnt/boot/efi`

`pacstrap /mnt linux linux-zen linux-headers linux-firmware base base-devel sudo git sassc wget curl neofetch htop bpytop cmatrix pulseaudio nano os-prober grub networkmanager dhcpcd efibootmgr netctl wpa_supplicant dialog`

`genfstab /mnt >> /mnt/etc/fstab`

`arch-chroot /mnt`

`echo laughtale > /etc/hostname`

`ln -sf /usr/share/zoneinfo/Europe/Madrid /etc/localtime`

`nano /etc/locale.gen`

**UNCOMMENT ca_ES.UTF-8 & es_ES.UTF-8; THEN CTRL+O & ENTER & CTRL+X**

`locale-gen`

`hwclock -w`

`date`

`echo KEYMAP=es > /etc/vconsole.conf`

`echo LANG=ca_ES.UTF8 > /etc/locale.conf`

`pacman -S dosfstools mtools`

`nano /etc/default/grub`

**UNCOMMENT 'GRUB_DISABLE_OS_PROBER=false'; THEN CTRL+O & ENTER & CTRL+X**

`grub-install --efi-directory=/boot/efi --target=x86_64-efi --bootloader-id=grub_uefi --recheck`

`grub-mkconfig -o /boot/grub/grub.cfg`

`passwd`

**ROOT PASSWD & RETYPE PASSWD**

`useradd -m palo`

`passwd palo`

**USER PASSWD & RETYPE PASSWD**

`usermod -aG wheel palo`

`nano /etc/sudoers`

**UNCOMMENT %wheel ALL=(ALL:ALL) ALL; THEN CTRL+O & ENTER & CTRL+X**

`exit`

`umount -R /mnt`

`reboot`

**EJECT THE USB DRIVE & LOG IN WHEN REBOOT IS DONE**

`neofetch`

`sudo su` + **PASSWD**

`systemctl start NetworkManager.service`

`systemctl enable NetworkManager.service`

`systemctl start dhcpcd.service`

`systemctl enable dhcpcd.service`

`ìp link`

`ip link set XXX up`

`nmcli dev wifi connect WIFINAME password WIFIPASSWD`

`ping 8.8.8.8`

`pacman -S xf86-video-intel intel-ucode`

`pacman -S xorg-server xorg-xinit mesa mesa-demos`

`pacman -S gnome gnome-extra tilix`

`pacman -S gdm`

`systemctl enable gdm.service`

`reboot`
