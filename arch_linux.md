<div style="text-align:center"></a><img src="cover.jpg" /></div>

<div style="page-break-after: always;"></a></div>

# <a name="Title"></a> **Arch Guide 2020**

---

Covers Installation, Configuration and beyond.

Written by Adam Jones, Sources: Experience and from the [Arch Linux Website](https://www.archlinux.org/)  

Initially written 2020 during lockdown.

---

## <a name="TOC"></a> **Table of Contents**

**[Initial Setup](#1)**  

---

[Optional Install Script](#1-a)
[Boot the Live Environment](#1a)  
[Set the Keyboard Layout](#1b)  
[Verify the Boot Mode](#1c)  
[Connect to the Internet](#1d)  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Setup Wi-FI](#1da)*  
[Update the System clock](#1e)  

---

**[Disk Setup](#2)**  

---

[Example Layouts](#2a)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[BIOS with MBR](#2aa)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[UEFI BIOS With GPT](#2ab)*  
[Creating Partitions](#2b)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Create New Table](#2ba)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Create Partitions](#2bb)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Set Partition Type](#2bc)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[!!! Write Changes to Disk !!!](#2bd)*  
[Format the Partitions](#2c)  
[Mount the File Systems](#2d)  

---

**[Installation](#3)**  

---

[Select the Mirrors](#3a)  
[Install Essential Packages](#3b)  

---

**[Configure the System](#4)**  

---

[Fstab](#4a)  
[Chroot](#4b)  
[Timezone](#4c)  
[Set Localization](#4d)  
[Network Configuration](#4e)  
[Initramfs](#4f)  
[Root Password](#4g)  
[Create User & Enable Sudo](#4h)  
[Additional Changes](#4i)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Enable Multilib](#4ia)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Optimise Mirrors](#4ib)*  
[Boot Loader](#4j)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[MBR](#4ja)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[UEFI](#4jb)*  
[Microcode](#4k)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[GRUB](#4ka)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[rEFInd](#4kb)*  
[Reboot](#4l)  

---

**[Software Packages](#5)**  

---

[Base Packages](#5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Essential](#5a1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[File System](#5a2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[File System Optional](#5a2a)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[CPU](#5a3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Bootloader](#5a4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[CLI Text Editors](#5a5)  
[Additional Packages](#5b)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[System Utilities](#5b1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Networking](#5b2)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[General](#5b2a)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Wi-Fi](#5b2b)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Bluetooth](#5b2c)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Video](#5b3)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[General](#5b3a)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Nvidia](#5b3b)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[AMD](#5b3c)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Sound](#5b4)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Printing](#5b5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Xorg](#5b6)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Xorg Apps](#5b6a)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Fonts](#5b6b)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Display Managers](#5b7)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[GDM](#5b7a)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[LightDM](#5b7b)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[LXDM](#5b7c)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[SSDM](#5b7d)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[XDM](#5b7e)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Desktop Environments](#5b8)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Budgie](#5b8a)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Cinnamon](#5b8b)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Deepin](#5b8c)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Gnome](#5b8d)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[KDE Plasma](#5b8e)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[MATE](#5b8f)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[XFCE](#5b8g)* 

---

**[Post Installation](#6)** 

--- 

[Internet access](#6a)  
[Basic Config](#6a1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Enable Services](#6a1a)*  
[Lightdm Login Manager](#6b)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Aether Theme Installation](#6ba)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Enable Numlock On at Boot](#6bb)*  
[Yay](#6e)  
[Themes & Icons](#6f)  
[Plank](#6g)  
[Grub Themes](#6h)  
[Other Apps](#6i)  
[Gaming](#6j)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Steam](#6ja)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Lutris](#6jb)*

---

**[Extras](#7)**  

---

[Enable Root File Manager](#7a)  
[Cinnamon Menu Fonts](#7b)  
[Cannot Access SMB Shares](#7c)  
[gpg keyserver receive failed general error](#7d)  
[Cinnamon Hi-DPI Not Working Fully](#7e)  
[Add Shares to FStab](#7f)  
[Timeshift Issues](#7g)  
[Resolution issues](#7h)  
[Nautilus or Nemo Missing Image Previews](#7i)  
[Audio Delay](#7j)  
[Identify USB Devices in use](#7k)  
[“No object for D-Bus interface” When trying to access other partition](#7l)  
[Possibly missing firmware for module: aic94xx/wd719x](#7m)  

---

**[Useful Commands](#8)**  

---

[SystemD](#8a)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Listing Services](#8aa)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Logging](#8ab)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Identify Boot Delays](#8ab)  
[CLI Extras](#8b)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Password Astrisk](#8ba)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Export Man Pages to HTML](#8bc)
<div style="page-break-after: always;"></a></div>

## <a name="1"></a> **Initial Setup**

Obtain the latest ISO from the: 

***[Arch Linux Website](https://www.archlinux.org/)***

Further Information:

***[Installation Process Wiki Page](https://wiki.archlinux.org/index.php/Category:Installation_process)***

***[Back to Table of Contents](#TOC)***

### <a name =1-a> **Optional Install Script**

***[Archfi Install Script](#https://github.com/MatMoul/archfi)***  

Just a simple bash script wizard to install Arch Linux after you have booted on the official Arch Linux install media.

With this script, you can install Arch Linux with two simple terminal commands.

This wizard is made to install minimum packages (Base, bootloader and optionally archdi).

At the end of this wizard, you can install or launch archdi (Arch Linux Desktop Install) to install and configure desktop packages.

<mark>***IMPORTANT***</mark>

Ensure you have Network Connectivity before proceeding,jump to ***[Connect to the Internet](#1d)***

First, boot with the last Arch Linux image with a bootable device.

Then make sure you have Internet connection on the Arch iso. If you have a wireless connection the wifi-menu command might be useful to you. You can also read the Network configuration from the Arch Linux guide for more detailed instructions.

Then download the script with from the command line:

`wget archfi.sf.net/archfi`

If SourceForge is down, use this instead:

`wget matmoul.github.io/archfi`

Finally, launch the script:

`sh archfi`

Then follow the on-screen instructions to completion.

If you require extra help, visit the provided video playlist and follow my example.

### <a name="1a"></a> **Boot the Live Environment**

The live environment can be booted from a USB flash drive, an optical disc or a network with PXE. For alternative means of installation, see:  

[Live Environment Options](https://wiki.archlinux.org/index.php/installation_guide#Boot_the_live_environment)

>### **Setup SSH if Installing Remotely**
>- Check to see if your online with `ip a` find the relevant adaptor and make a note of the IP, if nothing is there continue on the machine itself.
>- Set the sudo password with `passwd`
>- Enable SSH with `systemctl start sshd.service
>- Now connect from your other machine.

***[Back to Table of Contents](#TOC)***

### <a name="1b"></a> **Set the Keyboard Layout**

The default console keymap is US. Available layouts can be listed with:

`ls /usr/share/kbd/keymaps/**/*.map.gz`

Alternatively for a better view use:

`ls /usr/share/kbd/keymaps/**/*.map.gz | less`

As the keyboard is US by default `|` will be on the key `Shift + #`

The default UK layout is `uk.map.gz`

To modify the layout, append a corresponding file name to loadkeys(1), omitting path and file extension. For example:

`loadkeys uk`

Console fonts are located in `/usr/share/kbd/consolefonts/` and can likewise be set with `setfont(8)`.

This is temporary for the installation, we can make it permanent by running the following command:

`echo KEYMAP=uk > /etc/vconsole.conf`

***[Back to Table of Contents](#TOC)***

### <a name="1c"></a> **Verify the Boot Mode**

If UEFI mode is enabled on an UEFI motherboard, Archiso will boot Arch Linux accordingly via systemd-boot. To verify this, list the efivars directory:  

`ls /sys/firmware/efi/efivars`</a></a>

If the directory does not exist, the system may be booted in BIOS or CSM mode. Refer to your motherboard's manual for details.  

***[Back to Table of Contents](#TOC)***

### <a name="1d"></a> **Connect to the Internet**

To check if the driver for your card has been loaded, check the output of the `lspci -k` or `lsusb -v` command, depending on if the card is connected by PCI(e) or USB.

Ensure your ***[Network Interface](https://wiki.archlinux.org/index.php/Network_interface)*** is listed and enabled, for example with ***[ip-link](https://jlk.fjfi.cvut.cz/arch/manpages/man/ip-link.8)***.

`ip link`

Connect to the network and Plug in the Ethernet cable or connect to the [wireless LAN](#1da).

Configure your network connection:

- ***[Static IP address](https://wiki.archlinux.org/index.php/Network_configuration#Static_IP_address)***
- ***[Dynamic IP address](https://wiki.archlinux.org/index.php/DHCP)***

*Note: The installation image enables dhcpcd (dhcpcd@interface.service) for wired network devices on boot.*  

<mark>**Important**</mark>: To use DHCP you need a DHCP server in your network and a DHCP client, you need to install one of the following:

**dhcpcd**
***Package***: dhcpcd
***Archiso***:Yes
***Note***: DHCP, DHCPv6, ZeroConf, static IP
***Systemd Units***: dhcpcd.service, dhcpcd@interface.service

**ISC dhclient**
***Package***:dhclient
***Archiso***:Yes
***Note***: DHCP, DHCPv6, BOOTP, static IP
***Systemd Units***: dhclient@interface.service

The connection may be verified with ping:

`ping archlinux.org`

#### <a name="1da"></a> **Setup Wi-FI**

- *Check Driver*

To check if the driver for your card has been loaded, check the output of the `lspci -k` or `lsusb -v` command, depending on if the card is connected by PCI(e) or USB.

- *Get the name of the interface*

`iw dev`

The name of the interface will be output after the word "Interface". For example, it is commonly wlan0.

- *Get the status of the interface*

To check link status, use following command.

`iw dev interface link`

- *If set to UP, Change to DOWN.*

`ip link set interface down`

- *Run the setup tool.*

`wifi-menu`

- *Ping Test*

>If `wifi-menu` fails, then disable dhcpcd via `systemctl stop dhcpcd` and `systemctl disable dhcpcd` and also set the adaptor to down, for example `ip link set wlan0 down` and then re-run the `wifi-menu` command

`ping www.google.co.uk`

`ctrl-C` (Cancel)

***[Arch Linux Wireless Configuration Page](https://wiki.archlinux.org/index.php/Network_configuration/Wireless)***

***[Back to Table of Contents](#TOC)***

### <a name="1e"></a> **Update the System clock**

Use ***[`timedatectl(1)`](https://jlk.fjfi.cvut.cz/arch/manpages/man/timedatectl.1)*** to ensure the system clock is accurate.

`timedatectl set-ntp true`

To check the service status, use timedatectl status`.

***[Back to Table of Contents](#TOC)***

## <a name="2"></a> **Disk Setup**

When recognized by the live system, disks are assigned to a block device such as `/dev/sda` or `/dev/nvme0n1`. To identify these devices, use `lsblk` or `fdisk`.

`fdisk -l`

Results ending in `rom`, `loop` or `airoot` may be ignored.

The following partitions are required for a chosen device:

- One partition for the root directory /.
- If UEFI is enabled, an EFI system partition.

***[UEFI Information](https://wiki.archlinux.org/index.php/Unified_Extensible_Firmware_Interface)***

***[Back to Table of Contents](#TOC)***

### <a name="2a"></a> **Example Layouts**

***[Partition Layouts Examples Page](https://wiki.archlinux.org/index.php/Partitioning#Example_layouts)***

#### <a name="2aa"></a> **BIOS With MBR**

|**Mount Point**|**Partition**|**Partition Type**|**Suggested Size**|
|:-----:|:-----:|:-----:|:-----:|
|`/mnt`|  `/dev/sdX1`|Linux|Remainder of device|
|`[SWAP]`|`/dev/sdX2`|Linux Swap|More than 512Mib|

#### <a name="2ab"></a> **UEFI BIOS With GPT**

|**Mount Point**|**Partition**|**Partition Type**|**Suggested Size**|
|:-----:|:-----:|:-----:|:-----:|
|`/mnt/boot` or `/mnt/efi`|`/dev/sdX1`|EFI System Partition|260-512 Mib|
|`/mnt`|`/dev/sdX2`|Linux x86-64 root (/)|Remainder of device|
|`[SWAP]`|`/dev/sdX3`|Linux Swap|More than 512Mib|

> **Note:** if your on a system that already has an efi partition (Duel Booting) then leave that along, you can use that partition for the bootloader if needed, setting up `grub` and using `os-prober` will find any other operating systems.

Use `fdisk` or `parted` to modify partition tables, for example `fdisk /dev/sdX`.

				>You can also use `cfdisk` which a more user friendly experience and you will need to setup the partitions as above tables, again ensuring you change type of each partition and writing them to disk before exiting.

***[Back to Table of Contents](#TOC)***

### <a name="2b"></a> **Creating Partitions**

To list partition tables and partitions on a device, you can run ***[fdisk](https://wiki.archlinux.org/index.php/Fdisk)***, where device is a name like `dev/sda`.

`fdisk -l /dev/sda`

>*Note: If the device is not specified, fdisk will list all partitions in /proc/partitions.*

The first step to partitioning a disk is making a partition table. After that, the actual partitions are created according to the desired partition scheme. See the partition table article to help decide whether to use MBR or GPT.

Before beginning, you may wish to backup your current partition table and scheme.

Start fdisk against your drive as root. In this example we are using ``/dev/sda`:

`fdisk /dev/sda`

This opens the fdisk dialogue where you can type in commands.

***[Back to Table of Contents](#TOC)***

#### <a name="2ba"></a> **Create New Table**

To create a new partition table and clear all current partition data type o at the prompt for a MBR partition table or g for a GUID Partition Table (GPT). Skip this step if the table you require has already been created.

***[Back to Table of Contents](#TOC)***

#### <a name="2bb"></a> **Create Partitions**

Create a new partition with the n command. You enter a partition type, partition number, starting sector, and an ending sector.

When prompted, specify the partition type, type p to create a primary partition or e to create an extended one. There may be up to four primary partitions.

The first sector must be specified in absolute terms using sector numbers. The last sector can be specified using the absolute position in sectors or using the + symbol to specify a position relative to the start sector measured in sectors, kibibytes (K), mebibytes (M), gibibytes (G), tebibytes (T), or pebibytes (P); for instance, setting +2G as the last sector will specify a point 2GiB after the start sector. Pressing the Enter key with no input specifies the default value, which is the start of the largest available block for the start sector and the end of the same block for the end sector.

***[Back to Table of Contents](#TOC)***

#### <a name="2bc"></a> **Set Partition Type**

Select the partition's type id. The default, Linux filesystem, should be fine for most use. Press l to show the codes list. You can make the partition bootable by typing a.

***[Back to Table of Contents](#TOC)***

#### <a name="2bd"></a> **!!! Write Changes to Disk !!!**

Write the table to disk and exit via the w command.

***Additional***

>*Warning: Partitions can only be moved while offline. Because moving a partition requires the whole partition to be rewritten on disk, it is a slow and potentially hazardous operation. Backups are strongly recommended! According to the sfdisk man page, "this operation is risky and not atomic."*

***[Back to Table of Contents](#TOC)***

### <a name="2c"></a> **Format the Partitions**

Once the partitions have been created, each must be formatted with an appropriate file system. For example, if the root partition is on /dev/sdX1 and will contain the ext4 file system, run:

`mkfs.ext4 /dev/sdX1`

If you created a partition for swap, initialize it with mkswap:

`mkswap /dev/sdX2`
`swapon /dev/sdX2`

For EFI partitions run the following:

`mkfs.fat -F32 /dev/sdxY`

If you get the message WARNING: Not enough clusters for a 32 bit FAT!, reduce cluster size with ``mkfs.fat -s2 -F32 ...` or -`s1;` otherwise the partition may be unreadable by UEFI. See mkfs.fat(8) for supported cluster sizes.

***[mkfs.fat information](https://jlk.fjfi.cvut.cz/arch/manpages/man/mkfs.fat.8)***

***[Back to Table of Contents](#TOC)***

### <a name="2d"></a> **Mount the File Systems**

Mount the file system on the root partition to /mnt, for example:

`mount /dev/sdX1 /mnt`

Create any remaining mount points (such as `/mnt/efi`) and mount their corresponding partitions, swap partitions do not need to be mounted.

`mount /dev/sdX1 /mnt/efi`

Or you can mount it to boot as per below, but make sure you remember where you mounted it, this will be needed for the bootloader config later.

`mount /dev/sdX1 /mnt/boot/efi`

>**Boot Mount Points (For dual Booting)** 
>
>If Arch's filesystem layout only places grubx64.efi (and possibly the GRUB2 configuration file) to the EFI partition, 100 MB is fine.
>
>But if your layout mounts the EFI partition as /boot (rather than /boot/efi) or otherwise causes the entire kernel + initramfs files to be placed in there, you might run out of space with more than just one or two kernel versions installed. That is going to make kernel updates unnecessarily risky.
>
>You'll always want to have at least two kernels installed: the one you're currently using, and the previous one as a known good back-up. When you are installing a new kernel, that means you'll end up temporarily with three kernels installed: the old, the current and the new one.
>
>If you are brave, you can always delete the old kernel (+ its initramfs file) just before installing a new kernel, but in a production system I would not like to do that.

---

>**EFI Notes**
>
- /efi is a replacement[6] for the previously popular (and possibly still used by other Linux distributions) ESP mountpoint /boot/efi.
- The /efi directory is not available by default, you will need to first create it with mkdir(1) before mounting the ESP to it.
>`mkdir /efi` or `mkdir -p /mnt/boot/efi` (`-p` will create any parent folders if not already created)
	
***[Back to Table of Contents](#TOC)***
	
## <a name="3"></a> **Installation**
	
### <a name="3a"></a> **Select the Mirrors**
	
Packages to be installed must be downloaded from mirror servers, which are defined in /etc/pacman.d/mirrorlist. On the live system, all mirrors are enabled, and sorted by their synchronization status and speed at the time the installation image was created.
	
The higher a mirror is placed in the list, the more priority it is given when downloading a package. You may want to edit the file accordingly, and move the geographically closest mirrors to the top of the list, although other criteria should be taken into account.
	
This file will later be copied to the new system by pacstrap, so it is worth getting right.
	
***[Back to Table of Contents](#TOC)***
	
### <a name="3b"></a> **Install Essential Packages**
>**Error: failed retrieving file ‘core.db’**  
>
Prior to installing, ensure mirrors are correct by running: `pacman -Syyu` but do not update as your still on the live system

Use the pacstrap script to install the base package, Linux kernel and firmware for common hardware:

***[Pacstrap Script](https://projects.archlinux.org/arch-install-scripts.git/tree/pacstrap.in)*** 

`pacstrap /mnt base linux linux-firmware`

For a complete overview of system software, go to the software section here: **[Software Packages](#5)**

> <mark>**IMPORTANT**</mark>
Make sure you install a DHCP server, ie. `NetworkManager` and its also worth installing `sudo` to help further on with user creation.

***[Back to Table of Contents](#TOC)***

## <a name="4"></a> **Configure the System**

### <a name="4a"></a> **Fstab**

Generate an ***[fstab](https://wiki.archlinux.org/index.php/Fstab)*** file (use -U or -L to define by UUID or labels, respectively):

`genfstab -U /mnt >> /mnt/etc/fstab`

Check the resulting /mnt/etc/fstab file, and edit it in case of errors.

***[UUID Information](https://wiki.archlinux.org/index.php/UUID)***

***[Back to Table of Contents](#TOC)***

### <a name="4b"></a> **Chroot**

Change root into the new system with ***[chroot](https://wiki.archlinux.org/index.php/Installation_guide#Chroot)***:

`arch-chroot /mnt`

***[Back to Table of Contents](#TOC)***

### <a name="4c"></a> **Timezone**

Identify your ***[timezone](https://wiki.archlinux.org/index.php/Time_zone)*** with:

`timedatectl list-timezones | less`

For example: `Europe/London`

Set the time zone:

`ln -sf /usr/share/zoneinfo/Region/City /etc/localtime`

Run ***[hwclock(8)](https://jlk.fjfi.cvut.cz/arch/manpages/man/hwclock.8)*** to generate /etc/adjtime:

`hwclock --systohc`

This command assumes the hardware clock is set to ***[UTC](https://en.wikipedia.org/wiki/UTC)***. See System ***[time#Time](https://wiki.archlinux.org/index.php/System_time#Time_standard)*** standard for details.

***[Back to Table of Contents](#TOC)***

### <a name="4d"></a> **Set Localization**

Generate the ***[locales](https://wiki.archlinux.org/index.php/Locale)*** by running: 

`locale-gen`

Now edit `/etc/locale.gen` and uncomment `en_GB.UTF-8` `UTF-8` and other needed locales.

`nano /etc/locale.gen`

Uncomment the below or whichever applies: 

`LANG=en_GB.UTF-8`

>Alternativly run: 
`echo en_GB.UTF-8 UTF-8 >> /etc/locale.gen`

Create the locale.conf(5) file, and set the LANG variable accordingly: 

`nano /etc/locale.conf`

Add the following:

`LANG=en_GB.UTF-8`

>Alternativly run:
>`echo LANG=en_GB.UTF-8 > /etc/locale.conf`
>Then export the locale
>`export LANG=en_GB.UTF-8`

If you didn't set them pe rmenantly before you can set the keyboard layout now by adding the following to `vconsole.conf`

`nano /etc/vconsole.conf`

Add the following:

`KEYMAP=uk`

>Alternativly run:
>`echo KEYMAP=uk > /etc/vconsole.conf`

***[Back to Table of Contents](#TOC)***

### <a name="4e"></a> **Network Configuration**

Create the ***[hostname](https://wiki.archlinux.org/index.php/Hostname)*** file:

`/etc/hostname`
`myhostname`

>Alternativly run:
>`echo hostname > /etc/hostname`

Add matching entries to ***[hosts(5)](https://jlk.fjfi.cvut.cz/arch/manpages/man/hosts.5<)***:

`nano /etc/hosts`

|/etc/hosts||||
|---|---|---|---|
|127.0.0.1||localhost||
|::1||localhost||
|127.0.1.1||myhostname.localdomain|myhostname|

If the system has a permanent IP address, it should be used instead of 127.0.1.1.

Complete the ***[network configuration](https://wiki.archlinux.org/index.php/Network_configuration)*** for the newly installed environment, that includes installing your preferred ***[network management](https://wiki.archlinux.org/index.php/Network_management)*** software.

***[Back to Table of Contents](#TOC)***

### <a name="4f"></a> **Initramfs**

Creating a new ***[initramfs](https://wiki.archlinux.org/index.php/Arch_boot_process#initramfs)*** is usually not required, because mkinitcpio was run on installation of the kernel package with pacstrap.

For LVM, system encryption or RAID, modify ***[mkinitcpio.conf(5)](https://jlk.fjfi.cvut.cz/arch/manpages/man/mkinitcpio.conf.5)*** and recreate the initramfs image:

`mkinitcpio -P`

*Run it to make sure the kernel has been installed properly*

***[Back to Table of Contents](#TOC)***

### <a name="4g"></a> **Root Password**

Set the root ***[password](https://wiki.archlinux.org/index.php/Password)***:

`passwd`

***[Back to Table of Contents](#TOC)***

### <a name="4h"></a> **Create User & Enable Sudo**

First install `sudo` and `vim` to allow us to edit the sudoers file

`pacman -S vim sudo`

Now we run 

`visudo`

Uncomment the wheel group, this allows all users in the wheel group to run all commands.

`%wheel ALL=(ALL) ALL`

Add a user for a typical desktop system, eg: user that takes advantage of teh GUI desktop managers. /bin/bash specifies their login shell.

`useradd -m -G wheel -s /bin/bash userOne`

> **Additional**
>Change login name: `usermod -l newname oldname`
>Change Home directory: ``usermod -d /new/home/dir -m user0ne`
>Adding system user: `useradd -r -s /usr/bin/nologin user0ne`

***[Back to Table of Contents](#TOC)***

### <a name="4i"></a> **Additional Changes**

***[Back to Table of Contents](#TOC)***

#### <a name="4ia"></a> **Enable MultiLib**

To enable multilib repository, uncomment the `[multilib]` section in ``/etc/pacman.conf`:

`sudo nano /etc/pacman.conf`

`/etc/pacman.conf`
`[multilib]`
`Include = /etc/pacman.d/mirrorlist`

Now do an update via: `pacman -Syy`

***[Back to Table of Contents](#TOC)***

#### <a name="4ib"></a> **Optimise Mirrors**

This applies if `reflector` was installed just run the below command and change the country name if required.

`reflector --country 'United Kingdom' --age 24 --protocol https --sort rate --save /etc/pacman.d/mirrorlist`

This will ensure you have the fastest mirrors possible.

***[Back to Table of Contents](#TOC)***

### <a name="4j"></a> **Boot loader**

Choose and install a Linux-capable boot loader. If you have an Intel or AMD CPU, enable microcode updates in addition.

Recommended is the ***[Grub](https://www.archlinux.org/packages/?name=grub)*** bootloader.

***[Back to Table of Contents](#TOC)***

#### <a name="4ja"></a> **MBR**

If not already installed, ensure you have the below installed:

`sudo pacman -S grub os-prober`

*GRUB is the bootloader while os-prober will find other operating systems currently installed.*

The following command will install grub into the relevant folder on `/`.

`grub-install --target=i386-pc /dev/sdX`

where /dev/sdX is the disk (not a partition) where GRUB is to be installed. For example /dev/sda or /dev/nvme0n1, or /dev/mmcblk0.

Now you must generate the main configuration file. Use the ***[grub-mkconfig](https://wiki.archlinux.org/index.php/GRUB#Generate_the_main_configuration_file)*** tool to generate /boot/grub/grub.cfg:

`grub-mkconfig -o /boot/grub/grub.cfg`

To have grub-mkconfig search for other installed systems and automatically add them to the menu, the `os-prober` will do this when you re-run grub-mkconfig.

***[Back to Table of Contents](#TOC)***

#### <a name="4jb"></a> **UEFI**

If not already installed, ensure you have the below installed:

`sudo pacman -S grub os-prober efibootmgr`

*GRUB is the bootloader while ***[efibootmgr](https://www.archlinux.org/packages/?name=efibootmgr)*** is used by the GRUB installation script to write boot entries to NVRAM. While os-prober will find other operating systems.*

> - It is recommended to read and understand the Unified Extensible Firmware Interface, Partitioning#GUID Partition Table and Arch boot process#Under ***[UEFI](https://wiki.archlinux.org/index.php/Unified_Extensible_Firmware_Interface)*** pages.
- When installing to use UEFI it is important to boot the installation media in UEFI mode, otherwise efibootmgr will not be able to add the GRUB UEFI boot entry. Installing to the fallback boot path will still work even in BIOS mode since it does not touch the NVRAM.
- To boot from a disk using UEFI, an EFI system partition is required. Follow EFI system partition#Check for an existing partition to find out if you have one already, otherwise you need to create it.

***[GUID Partition Table Info](https://wiki.archlinux.org/index.php/Partitioning#GUID_Partition_Table)***
***[Arch Boot Process under UEFI Info](https://wiki.archlinux.org/index.php/Arch_boot_process#Under_UEFI)***


- Mount the EFI system partition and in the remainder of this section, substitute esp with its mount point.
- Choose a bootloader identifier, here named GRUB. A directory of that name will be created in esp/EFI/ to store the EFI binary and this is the name that will appear in the UEFI boot menu to identify the GRUB boot entry.
- Execute the following command to install the GRUB EFI application grubx64.efi to esp/EFI/GRUB/ and install its modules to /boot/grub/x86_64-efi/.

***[Mounting the EFI Partition Info](https://wiki.archlinux.org/index.php/EFI_system_partition#Mount_the_partition)***

`grub-install --target=x86_64-efi --efi-directory=esp --bootloader-id=GRUB`

After the above install completed the main GRUB directory is located at `/boot/grub/`. Note that grub-install also tries to create an entry in the firmware boot manager, named GRUB in the above example.

Remember to Generate the main configuration file after finalizing the configuration.

After the installation, the main configuration file /boot/grub/grub.cfg needs to be generated. The generation process can be influenced by a variety of options in /etc/default/grub and scripts in /etc/grub.d/.

If you have not done additional configuration, the automatic generation will determine the root filesystem of the system to boot for the configuration file. For that to succeed it is important that the system is either booted or chrooted into.

Use the ***[grub-mkconfig](https://wiki.archlinux.org/index.php/GRUB#Generate_the_main_configuration_file)*** tool to generate /boot/grub/grub.cfg:

`grub-mkconfig -o /boot/grub/grub.cfg`

To have grub-mkconfig search for other installed systems and automatically add them to the menu, ensure the os-prober package is installed and mount the partitions that contain the other systems. Then re-run grub-mkconfig.

> **Tip:** 
If you use the option `--removable` then GRUB will be installed to `esp/EFI/BOOT/BOOTX64.EFI` (or `esp/EFI/BOOT/BOOTIA32.EFI` for the `i386-efi` target) and you will have the additional ability of being able to boot from the drive in case EFI variables are reset or you move the drive to another computer. Usually you can do this by selecting the drive itself similar to how you would using BIOS. If dual booting with Windows, be aware Windows usually places an EFI executable there, but its only purpose is to recreate the UEFI boot entry for Windows.

---

> **Note:** 
>
>- `--efi-directory` and `--bootloader-id` are specific to GRUB UEFI, `--efi-directory` replaces `--root-directory` which is deprecated.
>- You might note the absence of a device_path option (e.g.: `/dev/sda`) in the `grub-install` command. In fact any device_path provided will be ignored by the GRUB UEFI install script. Indeed, UEFI bootloaders do not use a MBR bootcode or partition boot sector at all.
>- Make sure to run the `grub-install` command from the system in which GRUB will be installed as the boot looader. That means if you are booting from the live installation environment, you need to be inside the chroot when running `grub-install`. If for some reason it is necessary to run `grub-install` from outside of the installed system, append the `--boot-directory=` option with the path to the mounted `/boot` directory, e.g `--boot-directory=/mnt/boot`.

---

>**Dual Boot Tip (UEFI)**
>
If Grub does not load within a dual boot environment then within linux do the following:
>
- Run efibootmgr and get the number of the boot manager, ie. 0001.
- Run the following: `efibootmgr -b <number> --inactive`
- To delete do the following: `efibootmgr -b <number> -B`

***[GRUB UEFI Info](https://wiki.archlinux.org/index.php/GRUB#UEFI)***
***[UEFI Tips and Tricks - Further Reading](https://wiki.archlinux.org/index.php/GRUB/Tips_and_tricks#UEFI_further_reading)***

***[Back to Table of Contents](#TOC)***

### <a name="4k"></a> **Microcode**

Processor manufacturers release stability and security updates to the processor microcode. These updates provide bug fixes that can be critical to the stability of your system. Without them, you may experience spurious crashes or unexpected system halts that can be difficult to track down.

All users with an AMD or Intel CPU should install the microcode updates to ensure system stability.

For AMD processors, install the `amd-ucode` package.

For Intel processors, install the `intel-ucode` package.

If your Arch installation is on a removable drive that needs to have microcode for both manufacturer processors, install both packages.

***[Back to Table of Contents](#TOC)***

#### <a name="4ka"></a> **GRUB**

grub-mkconfig will automatically detect the microcode update and configure GRUB appropriately. After installing the microcode package, regenerate the GRUB config to activate loading the microcode update by running:

`grub-mkconfig -o /boot/grub/grub.cfg`

> **Note:** grub-mkconfig does not add the microcode images to the fallback initramfs boot entry. See FS#60999.

Alternatively, users that manage their GRUB config file manually can add /boot/cpu_manufacturer-ucode.img (or /cpu_manufacturer-ucode.img if /boot is a separate partition) as follows:

`/boot/grub/grub.cfg`
...
`echo 'Loading initial ramdisk'`
`initrd	/boot/cpu_manufacturer-ucode.img /boot/initramfs-linux.img`
...

Repeat it for each menu entry.

***[Back to Table of Contents](#TOC)***

#### <a name="4kb"></a> **rEFInd**

Edit boot options in /boot/refind_linux.conf and add initrd=boot\cpu_manufacturer-ucode.img (or initrd=cpu_manufacturer-ucode.img if /boot is a separate partition) as the first initramfs. For example:

`"Boot using default options"     "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw add_efi_memmap initrd=boot\cpu_manufacturer-ucode.img initrd=boot\initramfs-%v.img"`

> **Tip:** Users who previously did not specify an initrd kernel parameter will need to follow the steps described in rEFInd#Configuration to enable passing of multiple initrd parameters.

Users employing manual stanzas in esp/EFI/refind/refind.conf to define the kernels should simply add initrd=boot\cpu_manufacturer-ucode.img (or initrd=cpu_manufacturer-ucode.img if /boot is a separate partition) as required to the options line, and not in the main part of the stanza. E.g.:

`options  "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw add_efi_memmap initrd=boot\cpu_manufacturer-ucode.img"`

***[Back to Table of Contents](#TOC)***

### <a name="4l"></a> **Reboot**

Before rebooting, ensure you have at least a DHCP client installed and unmount your efi and root partitions:

`umount /dev/sdaX`

*amend for whatever setup you have*

***[Back to Table of Contents](#TOC)***

## **<a name="5"></a> Software Packages**

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

### <a name="5a"></a> **Base Packages**

Install these prior to rebooting into live system with `pacstrap /mnt` for example:

*`pacstrap /mnt base linux linux-firmware`*  

#### <a name="5a1"></a> **Essential**

`base`  
`linux / linux-lts / linux-zen / linux-hardened`  
`linux-firmware`  
`linux-headers`  
`dkms`  
`dosfstools`  
`pacman-contrib`  
`base-devel`  
`git`  
`sudo`  
`networkmanager`  
`usbutils`  
`pciutils`  

#### <a name="5a2"></a> **File System**

`fuse2`  
`fuse3`  
`ntfs-3g`  
`exfat-utils`  
`gvfs`  
`gvfs-smb`  
`nfs-utils`  
`findutils`  
`mlocate`  

##### <a name="5a2a"></a> ***File System Optional***

`btrfs-progs` (For btrfs filesystems)  
`xfsprogs` (For XFS filesystems)  
`f2fs-tools` (Tools for Flash-Friendly File System / F2FS)  
`jfsutils` (For JFS filesystems)  
`reiserfsprogs` (Reiser file system)  
`lvm2` (Logical Volume Manager)  
`dmraid` (Raid or Fake Raid Software)  

#### <a name="5a3"></a> **CPU**

`amd-ucode / intel-ucode` (Decide which is suitable)  

#### <a name="5a4"></a> **Bootloader**

`grub / refind` (Decide which is suitable)  
`os-prober`  
`efi-bootmgr`  

#### <a name="5a5"></a> **CLI Text Editors**

`less`  
`nano`  
`vim`  
`vi`  

*Set default with `export EDITOR=(PACKAGE)`*

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

### <a name="5b"></a> **Additional Packages**

The base package does not include all tools from the live installation, so installing other packages may be necessary for a fully functional base system. In particular, consider installing:

***[Back to Table of Contents](#TOC)***

#### <a name="5b1"></a>**System Utilities**

`openssh` (Enable service)  
`cronie` (Enable service)  
`xdg-user-dirs` (Enable service)  
`haveged` (Enable service)   
`man-db`  
`man-pages`  
`lsb-release`  
`polkit`  
`unrar`  
`zip`  
`unzip`  
`p7zip`  
`lzop`   
`bashtop`  
`neofetch`  
`mc`  
`nmon`  

***[Back to Table of Contents](#TOC)***

#### <a name="5b2"></a> **Networking**

##### <a name="5b2a"></a> **General**

`network-manager-applet`  
`net-snmp`  
`samba`  
`smbnetfs`  
`nmap`  
`smbclient`  
`rsync`  
`traceroute`  
`dnsutils`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b2b"></a> **Wi-Fi**

`dialog`  
`wpa_supplicant`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b2c"></a> **Bluetooth**

`blueman`  
`bluez-utils`  
`bluez`  
`bluez-libs`  

***[Back to Table of Contents](#TOC)***

#### <a name="5b3"></a> **Video**

|Brand|Type|Driver|OpenGL|OpenGL (Multilib)|Documentation|
|:---:|:---:|:---:|:---:|:---:|:---:|
|AMD/ATI|Open source|`xf86-video-amdgpu`|`mesa`|`lib32-mesa`|[AMDGPU](https://wiki.archlinux.org/index.php/AMDGPU)|
|AMD/ATI|Open source|`xf86-video-ati`|`mesa`|`lib32-mesa`|[ATI](https://wiki.archlinux.org/index.php/ATI)|
|Intel|Open source|`xf86-video-intel`|`mesa`|`lib32-mesa`|[Intel graphics](https://wiki.archlinux.org/index.php/Intel_graphics)|
|NVidia|Open source|`xf86-video-nouveau`|`mesa`|`lib32-mesa`|[Nouveau](https://wiki.archlinux.org/index.php/Nouveau)|
|NVidia|Proprietary|`nvidia`|`nvidia-utils`|`lib32-nvidia-utils`|[NVIDIA](https://wiki.archlinux.org/index.php/NVIDIA)|
|NVidia|Proprietary|`nvidia-390xx` *AUR*|`nvidia-390xx-utils` *AUR*|`lib32-nvidia-390xx-utils` *AUR*|[NVIDIA](https://wiki.archlinux.org/index.php/NVIDIA)|

***[Back to Table of Contents](#TOC)***

##### <a name="5b3b"></a> **Nvidia**

`nvidia-settings`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b3c"></a> **AMD**

`vulkan-radeon`  
`xf86-video-amdgpu`  
`catalyst`  
`catalyst=total-hd234k`  

***[Back to Table of Contents](#TOC)***

#### <a name="5b4"></a> **Sound**

`alsa-utils`  
`alsa-plugins`  
`lib32-alsa-plugins`  
`pulseaudio`  
`pulseaudio-alsa`  
`pulseaudio-bluetooth`  
`pulseaudio-equalizer`  

***[Back to Table of Contents](#TOC)***

#### <a name="5b5"></a>**Printing**

`cups`  
`cups-pdf`  
`hplip`  
`system-config-printer`  
`foomatic-db`  
`foomatic-db-engine`  
`foomatic-db-ppds`  
`foomatic-db-nonfree-ppds`  
`foomatic-db-nonfree`  
`foomatic-gutenprint-ppds`  
`gutenprint`  
`ghostscript`  

***[Back to Table of Contents](#TOC)***

#### <a name="5b6"></a> **XORG**

##### <a name="5b6a"></a> **XORG Apps**

`xorg`  
`xorg-xinit`  
`xorg-apps`  
`xorg-server`  
`xorg-drivers`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b6b"></a> **Fonts**

`font-bh-ttf`  
`font-bitstream-speedo`  
`gsfonts`  
`sdl_ttf`  
`ttf-bitstream-vera`  
`ttf-dejavu`  
`ttf-liberation`  
`xorg-fonts-type1`  
`ttf-ubuntu-font-family`  
`noto-fonts`  		
`ttf-opensans`  

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

#### <a name="5b7"></a> **Display Managers**

##### <a name="5b7a"></a> **[GDM](https://wiki.archlinux.org/index.php/GDM)**

GNOME display manager.  

`gdm` (Also included in `gnome` package group)  
`systemctl enable gdm.service`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b7b"></a> **[LightDM](https://wiki.archlinux.org/index.php/LightDM)**

Cross-desktop display manager, can use various front-ends written in any toolkit.  

`lightdm`  
`systemctl enable lightdm.service`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b7c"></a> **[LXDM](https://wiki.archlinux.org/index.php/LXDM)**

display manager. Can be used independent of the LXDE desktop environment.  

`lxdm` or `lxdm-gtk3` for the GTK3 version.  
`systemctl enable lxdm.service`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b7d"></a> **[SDDM](https://wiki.archlinux.org/index.php/SDDM)**

QML-based display manager and successor to KDM; recommended for Plasma and LXQt.  

`sddm` Optionally install `sddm-kcm` for KDE.  
`systemctl enable sddm.service`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b7e"></a> **[XDM](https://wiki.archlinux.org/index.php/XDM)**

X display manager with support for XDMCP, host chooser.  

`xorg-xdm`  
`systemctl enable xdm.service`  

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

#### <a name="5b8"></a> **Desktop Environments**

##### <a name="5b8a"></a> **[Budgie](https://wiki.archlinux.org/index.php/Budgie)** 
`budgie-desktop`  
`gnome`  
`gnome-extra`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b8b"></a> **[Cinnamon](https://wiki.archlinux.org/index.php/Cinnamon)**
`cinnamon`  
`metacity` and `gnome-shell` (Fallback mode)  

***[Back to Table of Contents](#TOC)***

##### <a name="5b8c"></a> **[Deepin](https://wiki.archlinux.org/index.php/Deepin)**
`deepin`  
`deepin-extra`  

*To be able to use the integrated network administration, the networkmanager package is required, and the NetworkManager.service must be started and enabled.*

***[Back to Table of Contents](#TOC)***

##### <a name="5b8d"></a> **[GNOME](https://wiki.archlinux.org/index.php/GNOME)**
`gnome`  
`gnome-extra`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b8e"></a> **[KDE Plasma](https://wiki.archlinux.org/index.php/KDE_Plasma)**
`plasma` or `plasma-meta` (Full)  
`plasma-desktop` (Minimal)  
`kde-applications` or `kde-applications-meta`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b8f"></a> **[MATE](https://wiki.archlinux.org/index.php/MATE)**
`mate`  
`mate-extra`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b8g"></a> **[XFCE](https://wiki.archlinux.org/index.php/Xfce)**
`xfce4`  
`xfce4-goodies`  

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

## <a name="6"></a> **Post Installation**

***[Back to Table of Contents](#TOC)***

### <a name="6a"></a>**Internet access**

`systemctl enable NetworkManager.service`
`systemctl start NetworkManager.service`
`systemctl enable wpa_supplicant`
`systemctl start wpa_supplicant`

If using ethernet test with a ping, if using Wi-Fil use the below commands:

List nearby wifi networks:

>nmcli device wifi list

Connect to a wifi network:

>nmcli device wifi connect *SSID* password *password*

Connect to a hidden network:

>nmcli device wifi connect *SSID* password *password* hidden yes

Connect to a wifi on the wlan1 wifi interface:

>nmcli device wifi connect *SSID* password *password* ifname wlan1 profile_name

Disconnect an interface:

>nmcli device disconnect ifname eth0

Reconnect an interface marked as disconnected:

>nmcli connection up uuid *UUID*

Get a list of UUIDs:

>nmcli connection show

See a list of network devices and their state:

>nmcli device

Turn off wifi:

>nmcli radio wifi off

**[netctl information page](https://wiki.archlinux.org/index.php/Netctl#Installation)**

***[Back to Table of Contents](#TOC)***

### <a name="6a1"></a> **Basic Config**

***[Back to Table of Contents](#TOC)***

Ensure you have the base packages from: **[Software Packages](#5)**

#### <a name="6a1a"></a> **Enable Services (If Applicable)**

Set the following services if required

`systemctl disable dhcpcd.service`  
`systemctl enable NetworkManager.service`  
`systemctl enable sshd.service`  
`systemctl enable cronie.service`  
`systemctl enable havegd.service`  
`systemctl enable bluetooth.service`  
`systemctl enable org.cups.cupsd.service`  

`systemctl enable gdm.service`  
`systemctl enable lightdm.service`  
`systemctl enable lxdm.service`  
`systemctl enable sddm.service`  
`systemctl enable xdm.service`  

***[Back to Table of Contents](#TOC)***

### <a name="6b"></a> **Lightdm Login Manager**

If you need lightdm as your display manager install it and enable it, see: **[Software Packages](#5)**

You will probably want to install a greeter. A greeter is a GUI that prompts the user for credentials, lets the user select a session, and so on. It is possible to use LightDM without a greeter, but only if an automatic login is configured; otherwise you will need to install xorg-server and one of the greeter packages below.

The official repositories contain the following greeters:

**lightdm-gtk-greeter:** this is the default greeter LightDM attempts to use when started unless configured to do otherwise.

**lightdm-deepin-greeter (deepin-session-ui):** A greeter from the Deepin project.

**lightdm-pantheon-greeter:** A greeter from the elementary OS project.

**lightdm-webkit2-greeter:** A greeter that uses Webkit2 for theming. It supersedes lightdm-webkit-greeterAUR.

**lightdm-webkit-theme-litarvan:** A modern and full-featured Webkit2 LightDM theme. this requires `lightdm-webkit2-greeter`

*If not already done, edit `/etc/lightdm/lightdm.conf` and set `greeter-session=lightdm-webkit2-greeter`.*
*Then edit `/etc/lightdm/lightdm-webkit2-greeter.conf` and set `theme` or `webkit-theme` to `litarvan` .*

Other alternative greeters are available in the AUR:

**lightdm-slick-greeter AUR:** A GTK based greeter focused more on appearance than lightdm-gtk-greeter, forked from lightdm-unity-greeterAUR, and default in Linux Mint.

**lightdm-unity-greeter AUR:** The greeter used by Ubuntu's Unity.

**lightdm-mini-greeter AUR:** A minimal, configurable, single-user greeter.

**lightdm-webkit-theme-aether AUR:** A sleek, straightforward Archlinux themed login screen written on lightdm and the lightdm-webkit2-greeter.

You can set the default greeter by changing the [Seat:*] section of the LightDM configuration file, like so:

>/etc/lightdm/lightdm.conf
[Seat:*]
...
greeter-session=lightdm-yourgreeter-greeter
...

Finally enable lightdm

`sudo systemctl enable lightdm`

And if required:

`sudo systemctl start lightdm`

***[Back to Table of Contents](#TOC)***

#### <a name="6ba"></a> **Aether Theme Installation**

**Install**

1. Install lightdm-webikit2-greeter
`sudo pacman -S lightdm-webkit2-greeter`

2. Get files
`git clone https://github.com/NoiSek/Aether.git`

3. Move to correct folder
`sudo cp --recursive Aether /usr/share/lightdm-webkit/themes/lightdm-webkit-theme-aether`

4. Config 1
`sudo sed -i 's/^webkit_theme\s*=\s*\(.*\)/webkit_theme = lightdm-webkit-theme-aether #\1/g' /etc/lightdm/lightdm-webkit2-greeter.conf`

5. Config 2
`sudo sed -i 's/^\(#?greeter\)-session\s*=\s*\(.*\)/greeter-session = lightdm-webkit2-greeter #\1/ #\2g' /etc/lightdm/lightdm.conf`

**Fix Avatar**

First obtain an avatar file as png or obtain the standard image from /usr/share/lightdm-webkit/themes/lightdm-webkit-theme-aether/Aether/src/img/default-user.png

Now copy this image to `/var/lib/AccountsService/icons/`

Now edit the users profile details

`sudo nano /var/lib/AccountsService/users/<username>`

Edit the following:

`[User]`
`Icon=/var/lib/AccountsService/icons/<filename>`

Now we need to set the permissions

`sudo chmod 644 /var/lib/AccountsService/users/<username>`
`sudo chmod 644 /var/lib/AccountsService/icons/<filename>`

Reboot and the Avatar should now show

***[Back to Table of Contents](#TOC)***

#### <a name="6bb"></a> **Enable Numlock On at Boot**

Install the `numlockx` package and then edit /etc/lightdm/lightdm.conf:

`sudo pacman-S numlockx`
`sudo nano /etc/lightdm/lightdm.conf`

>`[Seat:*]`
`greeter-setup-script=/usr/bin/numlockx on`

***[Back to Table of Contents](#TOC)***

### <a name="6e"></a> **Yay**

1. `pacman -S --needed base-devel`
2.  `sudo pacman -S git`
3. `git clone https://aur.archlinux.org/yay.git`
4. `cd yay`
5. `makepkg -si`

***[Back to Table of Contents](#TOC)***

### <a name="6f"></a> **Themes & Icons**

`yay sardi`  
`yay mint-themes`  
`yay mint-x-icons`  
`yay mint-y-icons`  
`yay mint-backgrounds`  
`yay volantes-cursors`  
`yay archlinux-artwork`

***[Back to Table of Contents](#TOC)***

### <a name="6g"></a> **Plank**

`sudo pacman -S plank`

> **Themes** - ***[Arco Linux Plank Themes](https://github.com/arcolinux/arcolinux-plank-themes)***
>1. `git clone https://github.com/arcolinux/arcolinux-plank-themes`
>2. `cd arcolinux-plank-themes/usr/share/plank/themes/`
>3. `sudo cp -r ./* ~/.local/share/plank/themes`
>4. all additional plank themes go into: `~/.local/share/plank/themes`

***[Back to Table of Contents](#TOC)***

### <a name="6h"></a> **Grub Themes**

- `git clone https://github.com/Se7endAY/grub2-theme-vimix.git`
- `cd grub2-theme-vimix`
- `sudo mv ./Vimix/ /boot/grub/themes`
- `sudo nano /etc/default/grub`

>`GRUB_THEME="/boot/grub/themes/Vimix/theme.txt"`

- Save and exit.
- Update Grub with the following:

`sudo grub-mkconfig -o /boot/grub/grub.cfg`

*Please note the Vimix is case sensetive with a capital V*

***[Back to Table of Contents](#TOC)***

### <a name="6i"></a> **Other Apps**

|**Command**|**Type**|
|:---:|:---:|
|`sudo pacman -S bleachbit`| *System Cleaner*|
|`yay pamac`| *Pacman GUI*|
|`sudo pacman -S gimp`| *Photo Editor*|
|`yay xviewer`| *Image Viewer*|
|`yay pix-git`| *Image Viewer*|
|`sudo pacman -S digikam`|*Raw Photo Tool*|
|`sudo pacman -S darktable`|*Raw Photo Tool*|
|`sudo pacman -S rawtherapee`|*Raw Photo Software*|
|`sudo pacman -S shotwell`|*Photo Manager*|
|`sudo pacman -S hugin`|*Panorma Software*|
|`sudo pacman -S gnome-screenshot`|*Screenshot*|
|`yay lollypop`| *Music Player*|
|`pacman -S cmus`|*Command Line Music Player*|
|`yay picard`|*Music Tagger*|
|`sudo pacman -S vlc`|*Media Player*|
|`yay spotify`|*Music Streaming*|
|`sudo pacman -S parcellite`| *Clipboard Manager*|
|`sudo pacman -S inkscape`| *Vector Image Editor*|
|`sudo pacman -S dconf-editor`|*Config Editor*|
|`yay google-chrome`|*Web Browser*|
|`sudo pacman -S firefox`|*Web Browser*
|`sudo pacman -S geary`|*E-Mail Client*|
|`sudo pacman -S evolution`|*E-Mail Client*|
|`yay msgviewer`|*Outlook msg viewer*|
|`yay teams`|*Microsoft Teams*|
|`yay whatsapp-nativefier-dark`|*Whatsapp*|
|`yay bitwarden`|*Password Manager*|
|`sudo pacman -S qbittorrent`|*Bittorrent client*|
|`yay thonny`|*Python IDE*|
|`yay timeshift`|*Recovery*|
|`sudo pacman -S libreoffice-fresh`| *Office Suite*|
|`yay freeoffice`| *Office Suite*|
|`sudo pacman -S xreader`| *Document Reader*|
|`sudo pacman -S galculator`|*Calculator*|
|`sudo pacman -S xed`| *Text Editor*|
|`yay focuswriter`|*Markdown / Text Editor*|
|`yay haroopad`|*Markdown Editor*|
|`yay remarkable`|*Markdown Editor*|
|`yay ghostwriter`|*Markdown Editor*|
|`yay multimarkdown`|*Markdown Export Tools*|
|`yay commonmark`|*Markdown Export Tools*|
|`sudo pacman -S pandoc`|*Markdown Export Tools*|
|`sudo pacman -S discount`|*Markdown Export Tools*|
|`yay kindlegen`|*eBook CLI Convertor*|
|`sudo pacman -S calibre`|*eBook Manager*|
|`yay koreader`|*Epub Reader*|
|`yay sigil`|*Epub Editor*|
|`yay joplin`|*Markdown Editor / Notebook*|
|`yay cherrytree`|*Notebook*|
|`sudo pacman -S grub-customizer`|*Grub Customizer*|
|`yay grub2-theme-vimix-git`|*Grub Arch Theme*|
|`sudo pacman -S xdg-utils`| *Editing Config Files*|
|`yay system-log`|*System Log GUI*|
|`yay gnome-system-monitor`|*System monitor GUI*|
|`sudo pacman -S tilda`| *Terminal*|
|`sudo pacman -S terminator`| *Terminal*|
|`sudo pacman -S sl`|*CLI Train*|
|`sudo pacman -S lolcat`|*CLI Rainbow Effect*|
|`sudo pacman -S gparted`|*Disk Partitioner*|
|`sudo pacman -S gnome-disk-utility`|*Disk Utility*|
|`sudo pacman -S baobab`|*Disk Usage*|
|`yay balena-etcher`|*USB Flasher*|
|`yay gtkhash`|*Hash Check Utility*|
|`sudo pacman -S gprename`|*File Renamer*|
|`sudo pacman -S yelp`|*Help*|
|`sudo pacman -S namcap`|*PKGBUILDs checker*|
|`yay ttf-ms-fonts`|*Microsoft Fonts*|
|`yay netdiscover`|*Network scanner with MAC vendors*|
|`pacman -S wavemon`|*CLI Wifi Scanner*|


***[Back to Table of Contents](#TOC)***

### <a name="6j"></a> **Gaming**

***[Back to Table of Contents](#TOC)***

#### <a name="6ja"></a> **Steam**

Enable the multilib repository (if not done already)

To enable multilib repository, uncomment the [multilib] section in /etc/pacman.conf:

`sudo nano /etc/pacman.conf`

>/etc/pacman.conf
[multilib]
Include = /etc/pacman.d/mirrorlist

Now install steam with `sudo pacman -S steam`

***[Back to Table of Contents](#TOC)***

#### <a name="6jb"></a> **Lutris**

Manage multiple game services with Lutris

`sudo pacman -S lutris`

>If you need to reset Lutris delete ~/.config/lutris & ~/.local/lutris

***[Back to Table of Contents](#TOC)***

## <a name="7"></a> **Extras**

### <a name="7a"></a> **Enable Root File Manager**

Install the following:

`yay libgksu`
`yay gksu`

Create a menu item or run command `gksu nemo` for example

***[Back to Table of Contents](#TOC)***

### <a name="7b"></a> **Cinnamon Menu Fonts**

Edit the following file `~/.themes/{THEME}/cinnamon/cinnamon.css` and change:

`stage` `font-family: sans, sans-serif;``}`

to

`stage {``}`

***[Back to Table of Contents](#TOC)***

### <a name="7c"></a> **Cannot Access SMB Shares**

Install the following if not done so already:

`sudo pacman -S gvfs gvfs-smb smbclient samba nmap smbnetfs`

Copy contents from smb.conf from:

***[Default Samba Conf](https://github.com/zentyal/samba/blob/master/examples/smb.conf.default)***

Add to: `/etc/samba/smb.conf`

Enable and start the relevant services:

`systemctl enable nmb.service`
`systemctl start nmb.service`

`systemctl enable smb.service`
`systemctl start smb.service`

`systemctl enable smbnetfs`
`systemctl start smbnetfs`

and now reboot, if that fails, edit `/etc/hosts` and add:

*`IP_Address* *Hostname`*

Access via:

 *`smb://IP_Address/Share`*

***[Back to Table of Contents](#TOC)***

### <a name="7d"></a> **gpg keyserver receive failed general error**

Take to failed keys and run the following:

`gpg --keyserver hkp://pgp.mit.edu --recv-keys {KEY}`

Additional Keyservers here: ***[https://sks-keyservers.net/](https://sks-keyservers.net/)***

***[Back to Table of Contents](#TOC)***

### <a name="7e"></a> **Cinnamon Hi-DPI Not Working Fully**

Under settings and Display, set the zoom level first to the desired level and enable Hi-DPI after, otherwise it will mess with the screen resolution.

***[Back to Table of Contents](#TOC)***

### <a name="7f"></a> **Add Shares to FStab**

*Ensure SMB Servies are installed*

First create folder to mount to:

`sudo mkdir /mnt/documents`

Now create your credentials folder if needed

`touch ~/.credentials`

Add the following, amend the details to suit:

`nano .credentials`

`username=username`
`password=password`

Now edit the fstab file: `sudo nano /etc/fstab` and add the following to suit, ensuring the paths are correct.

>`//IP_Address/Share`
>`/mnt/createdfolder`
>`cifs`
>`credentials=/PATH/TO/.credentials,iocharset=utf8,sec=ntlm,file_mode=0777,dir_mode=0777,noperm,vers=1.0`
>`0`
>`0`

If the share has a space in its name, replace the space with `\040` for example `Photography Data` would be `Photography\040Data`

***[Back to Table of Contents](#TOC)***

### <a name="7g"></a> **Timeshift Issues**

**Fails to start due to cron package**

Install: `sudo pacman -S cron

**Shows excessive data for backup**

Exclude the following folder: `/var/lib/dhcpcd/`

***[Back to Table of Contents](#TOC)***

### <a name="7h"></a> **Resolution issues**

If using a 4k monitor (3840 x 2160) do the following to ensure best display

In cinnamon got to settings, set zoom to `200%` and apply.

Now set the **Base Interface scale* to `Double (Hi-DPI)`

This will ensure the screen is sharp and games will work fine, zoom levels outside of 200% will mess up full screen apps, therefore 200% is best and scaling fonts and menus manually will yeild best results.

***[Back to Table of Contents](#TOC)***

### <a name="7i"></a> **Nautilus or Nemo Missing Image Previews**

A default limit to image files like .jpg, .png can be beween 1mb and 10mb, which stops them being previewed in Nautilus or Nemo file managers, to fix this do the following:

Install dconf-editor:

`sudo pacman -S dconf-editor`

Open dconf-editor and go to:

`org > gnome > nautilus or nemo > preferences > thumbnail limit`

Set `Use Default Value` to off and enter a higher size under `Custom Value`

Close the app to save and changes should be immediate

***[Back to Table of Contents](#TOC)***

### <a name="7j"></a> **Audio Delay**

To disable loading of the module-suspend-on-idle module, comment out the following line in the configuration file in use (~/.config/pulse/default.pa or /etc/pulse/default.pa):

`### Automatically suspend sinks/sources that become idle for too long`
`# load-module module-suspend-on-idle`

Finally restart PulseAudio to apply the changes.

`pulseaudio -k`
`pulseaudio --start`

***[Back to Table of Contents](#TOC)***

### <a name="7k"></a> **Identify USB Devices in use**

Find the device in:

`/dev/input/by-id`

Now run the following command to find the process ID:

`fuser /dev/input/by-id/{Device name}`

Either kill or make action to stop it being used.

***[Back to Table of Contents](#TOC)***

### <a name="7l"></a> **“No object for D-Bus interface” When trying to access other partition**

`systemctl --user restart gvfs-udisks2-volume-monitor`

***[Back to Table of Contents](#TOC)***

### <a name="7m"></a> **Possibly missing firmware for module: aic94xx/wd719x**

**aic94xx**

- `git clone https://aur.archlinux.org/aic94xx-firmware.git`  
- `cd aic94xx-firmware`  
- `makepkg -sri` 

**wd719x**

- `git clone https://aur.archlinux.org/wd719x-firmware.git`  
- `cd wd719x-firmware`  
- `makepkg -sri`  

Finally Run `mkinitcpio -p linux`.

## <a name="8"></a> **Useful Commands**

### <a name="8a"></a> **SystemD**

Source website: [Here](https://www.digitalocean.com/community/tutorials/systemd-essentials-working-with-services-units-and-the-journal)

***[Back to Table of Contents](#TOC)***

#### <a name="8aa"></a> **Basic Uses of SystemD**

**List systemd services**

Lists all active systemd services.  

`systemctl list-units`

Lists all of the units installed on the system, including those that systemd has not tried to load into memory.  

`systemctl list-unit-files`

Lists all possible systemd services which have loaded or attempted to load into memory, including those that are not currently active  

`systemctl list-units --all`

Lists all possible systemd services which have loaded or attempted to load into memory.  

`systemctl list-unit-files --state=enabled --no-pager`

**Enable / Disable systemd services**

`systemctl enable {ServiceName}.service`

`systemctl disable {ServiceName}.service`

**Check status of systemd services**

`systemctl status {ServiceName}.service`

***[Back to Table of Contents](#TOC)***
Check startup Applications for anything unnecessary.
#### <a name="8ab"></a> **Logging**


To see all log entries, starting at the oldest entry, type:

`journalctl`

By default, this will show you entries from the current and previous boots if `journald` is configured to save previous boot records. Some distributions enable this by default, while others do not (to enable this, either edit the */etc/systemd/journald.conf* file and set the *Storage=* option to “persistent”, or create the persistent directory by typing `sudo mkdir -p /var/log/journal`

If you only wish to see the journal entries from the current boot, add the -b flag:

`journalctl -b`

To see only kernel messages, such as those that are typically represented by dmesg, you can use the -k flag:

`journalctl -k`

Again, you can limit this only to the current boot by appending the -b flag:

`journalctl -k -b`

***[Back to Table of Contents](#TOC)***

#### <a name="8ac"></a> **Identify Boot Delays**

**Analyze boot times**

Check startup Applications for anything unnecessary.

`systemd-analyze`

`systemd-analyze blame`

Dumps the results into a graphical SVG file for details analysis.

`systemd-analyze plot > plot.svg`

***[Back to Table of Contents](#TOC)***

### <a name="8b"></a> **CLI Extras**

#### <a name="8ba"></a> **Password Astrisk**

Run `visudo` and add the following line:

>Defaults pwfeedback

***[Back to Table of Contents](#TOC)***

#### <a name="8bc"></a> **Export Man Pages to HTML**

`BROWSER=firefox man -H <command>`

***[Back to Table of Contents](#TOC)***