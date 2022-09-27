# arch-install

`loadkeys es`

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
