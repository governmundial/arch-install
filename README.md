# arch-install

`loadkeys es`

`ping 8.8.8.8`

**CTRL+C**

`iwctl`

`device list`

`station wlan0 get-networks`

`station wlan0 connect WIFINAME`

*PASSWORD*

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

`mkdir /mnt/boot`

`mkdir /mnt/boot/efi`

`mount /dev/XXXX[/boot/efi] /mnt/boot/efi`

`pacstrap /mnt linux linux-zen linux-headers linux-firmware base base-devel sudo git sassc wget curl neofetch htop bpytop cmatrix pulseaudio intel-ucode nano os-prober grub networkmanager dhcpcd efibootmgr netctl wpa_supplicant dialog`

`genfstab /mnt >> /mnt/etc/fstab`

`arch-chroot /mnt`

`echo laughtale > /etc/hostname`

`ln -sf /usr/share/zoneinfo/Europe/Madrid /etc/localtime`

`nano /etc/locale.gen`

**UNCOMMENT ca_ES.UTF-8 & es_ES.UTF-8 - CTRL+O ENTER CTRL+X**

`locale-gen`

`hwclock -w`

`date`

`echo KEYMAP=es > /etc/vconsole.conf`

`echo LANG=ca_ES.UTF8 > /etc/locale.conf`

`grub-install --efi-directory=/boot/efi --bootloader -id='Arch Linux' --target=x86_64-efi`

