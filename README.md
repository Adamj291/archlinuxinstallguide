<div style="text-align:center"></a><img src="cover.jpg" /></div>

<div style="page-break-after: always;"></a></div>

# <a name="Title"></a> **Arch Guide 2020**

---

Covers Installation, Configuration and beyond.

Written by Adam Jones, Sources: Experience and from the [Arch Linux Website](https://www.archlinux.org/)  

Initially written 2020 during lockdown.

---

## <a name="TOC"></a> **Table of Contents**

**[Introduction](#0)**  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[About Arch Linux](#0a)*  

---

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

---

**[Software Installation](#5)**  

---

[Base Packages](#5)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Kernel](#5a0)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Essential](#5a1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[SCSI](#5a1a)  
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
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Applications](#5b9)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[System](#5b9a)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Office](#5b9b)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Internet](#5b9c)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Multimedia](#5b9d)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Codecs](#5b9da)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Photo / Image Editing](#5b9e)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;*[Misc](#5b9f)*  
[Boot Loader](#5c)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[MBR](#5ca)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[UEFI](#5cb)*  
[Microcode](#5d)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[GRUB](#5da)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[rEFInd](#5db)*  
[Reboot](#5e)  

---

**[Post Installation](#6)** 

--- 

[Internet access](#6a)  
[Basic Config](#6a1)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Enable Services](#6a1a)*  
[Lightdm Login Manager Configuration](#6b)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Aether Theme Installation](#6ba)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Enable Numlock On at Boot](#6bb)*  
[Yay](#6e)  
[Themes & Icons](#6f)  
[Plank](#6g)  
[Grub Themes](#6h)  
[Additional AUR Apps](#6i)  
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
[Identify Boot Delays](#7ma)  
[Unable to mount from fstab at boot (Dependencies Failed)](#7mb)
[Package Groups](#7n)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[base-devel](#7na)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[xorg](#7nb)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[xorg-apps](#7nc)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[xorg-drivers](#7nd)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[gnome](#7ne)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[gnome-extra](#7nf)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[deepin](#7ng)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[deepin-extra](#7nh)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[plasma](#7ni)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[kde-applications](#7nj)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[mate](#7nk)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[mate-extra](#7nl)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[xfce4](#7nm)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[xfce4-goodies](#7nn)    

---

**[Useful Commands](#8)**  

---

[SystemD](#8a)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Listing Services](#8aa)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Logging](#8ab)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Identify Boot Delays](#8ac)   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Crash Investigation](#8ad)  
[CLI Extras](#8b)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Password Astrisk](#8ba)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[Export Man Pages to HTML](#8bc)
<div style="page-break-after: always;"></a></div>

## <a name="0"></a> **Introduction**

### <a name="0a"></a> **About Arch Linux**

***[Back to Table of Contents](#TOC)***

## <a name="1"></a> **Initial Setup**

Before Proceeding, make sure you have the necessary information and any data currently on the system is fully backed up, this means backed up on either removable media or cloud storage. This should be standard practice however beyond this point any data stored locally is at risk, you have been warned! (I will not be liable for any data loss)

First you need to obtain the latest ISO from the: ***[Arch Linux Website](https://www.archlinux.org/)***

Now you can either burn this to CD/DVD (If your still using Optical media), Flash it to a USB drive or if your using a virtual machine mount the ISO, information on how to do this can be found on the ***[Arch Linux Wiki](https://wiki.archlinux.org/index.php/Category:Installation_process)*** or a quick search. I personally use the application Balena Etch which can be installed on Linux, Mac or Windows.

Before proceeding, its also worth having access to the ***[Arch Linux Wiki](https://wiki.archlinux.org/index.php/Category:Installation_process)*** this is an amazing resource and is considered the best wiki amoungst the Linux community.

***[Back to Table of Contents](#TOC)***

### <a name="1-a"></a> **Optional Install Script**

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

For a complete overview of system software, go to the software section here: **[Software Installation](#5)**

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

If you didn't set them permenantly before you can set the keyboard layout now by adding the following to `vconsole.conf`

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

|/etc/||||
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

*Run it to make sure the kernel has been installed prope&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Enable Multilib](#4ia)*  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; *[Optimise Mirrors](#4ib)*  rly*

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

To save and exit from vim use : and wq to write and Quit

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

## **<a name="5"></a> Software Installation**

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

### <a name="5a"></a> **Base Packages**

Install these prior to rebooting into live system with `pacstrap /mnt` for example:

*`pacstrap /mnt base linux linux-firmware`*  

#### <a name="5a0"></a> **Kernel**

**Standard**

Vanilla Linux kernel and modules, with a few patches applied.

|**Name**|**Description**|
|:---:|:---:|
|`linux`|The Linux kernel and modules|
|`linux-docs`|Documentation for the Linux kernel|
|`linux-headers`|Headers and scripts for building modules for the Linux kernel|

**LTS**

Long-term support (LTS) Linux kernel and modules.

|**Name**|**Description**|
|:---:|:---:|
|`linux-lts`|The LTS Linux kernel and modules|
|`linux-lts-docs`|Documentation for the LTS Linux kernel|
|`linux-lts-headers`|Documentation for the LTS Linux kernel|
|`nvidia-lts`|NVIDIA drivers for linux-lts|

**Zen**

Result of a collaborative effort of kernel hackers to provide the best Linux kernel possible for everyday systems. Some more details can be found on https://liquorix.net (which provides kernel binaries based on Zen for Debian).

|**Name**|**Description**|
|:---:|:---:|
|`linux-zen`|The Linux ZEN kernel and modules|
|`linux-zen-docs`|Documentation for the Linux ZEN kernel|
|`linux-zen-headers`|Headers and scripts for building modules for the Linux ZEN kernel|

**Hardened**

A security-focused Linux kernel applying a set of hardening patches to mitigate kernel and userspace exploits. It also enables more upstream kernel hardening features than linux.

|**Name**|**Description**|
|:---:|:---:|
|`linux-hardened`|The Security-Hardened Linux kernel and modules|
|`linux-hardened-docs`|Documentation for the Security-Hardened Linux kernel|
|`linux-hardened-headers`|Headers and scripts for building modules for the Security-Hardened Linux kernel|

#### <a name="5a1"></a> **Essential**

These are required no matter what, ignore any of these and your system may not boot properly.

Please decide on one of the linux kernals in bold as to how you want your system setup, ie more stable, etc.

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`base`|Minimal package set to define a basic Arch Linux installation.|N|
|`linux-firmware`|Firmware files for Linux.|N|
|`linux-headers`|Headers and scripts for building modules for the Linux kernel.|N|
|`dkms`|Dynamic Kernel Modules System.|N|
|`pacman-contrib`|Contributed scripts and tools for pacman systems.|N|  
|`base-devel`|Core Linux Utilities, see [base-devel](#7na) for details.|N|
|`git`|the fast distributed version control system.|N|
|`sudo`|Give certain users the ability to run some commands as root.|N|
|`networkmanager`|Network connection manager and user applications.|Y| 
|`usbutils`|	USB Device Utilities.|N|
|`pciutils`|PCI bus configuration space access library and tools.|N|
|`pkgfile`|a pacman .files metadata explorer.|N|
|`diffutils`|Utility programs used for creating patch files.|N|
|`logrotate`|Rotates system logs automatically.|N|
|`smartmontools`|Control and monitor S.M.A.R.T. enabled ATA and SCSI Hard Drives.|N|
|`dialog`|A tool to display dialog boxes from shell scripts.|N|

#### <a name="5a1a"></a> **SCSI**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`lsscsi`|A tool that lists devices connected via SCSI and its transports.|N|
|`hdparm`|A shell utility for manipulating Linux IDE drive/driver parameters.|N|
|`sdparm`|A utility similar to hdparm but for SCSI devices.|N|
|`sg3_util`|Generic SCSI utilities.|N|

#### <a name="5a2"></a> **File System**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`fuse2`|A library that makes it possible to implement a filesystem in a userspace program.|N|
|`fuse3`|A library that makes it possible to implement a filesystem in a userspace program.	|N|
|`ntfs-3g`|NTFS filesystem driver and utilities.|N|
|`exfatprogs`|exFAT filesystem userspace utilities for the Linux Kernel exfat driver.|N|
|`gvfs`|Virtual filesystem implementation for GIO.|N|
|`gvfs-smb`|Virtual filesystem implementation for GIO (SMB/CIFS backend; Windows client).|N|
|`gvfs-afc`|Virtual filesystem implementation for GIO (AFC backend; Apple mobile devices).|N|
|`gvfs-goa`|Virtual filesystem implementation for GIO (Gnome Online Accounts backend; cloud storage).|N|
|`gvfs-gphoto2`|Virtual filesystem implementation for GIO (Gnome Online Accounts backend; cloud storage).|N|
|`gvfs-google`|Virtual filesystem implementation for GIO (Google Drive backend).|N|
|`gvfs-mtp`|	Virtual filesystem implementation for GIO (MTP backend; Android, media player).|N|
|`gvfs-nfs`|Virtual filesystem implementation for GIO (NFS backend).|N|
|`nfs-utils`|Support programs for Network File Systems.|N|
|`dosfstools`|DOS filesystem utilities.|N|
|`findutils`|GNU utilities to locate files.|N|
|`mlocate`|Merging locate/updatedb implementation.|N|

##### <a name="5a2a"></a> ***File System Optional***

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`btrfs-progs`|Btrfs filesystem utilities.|N|
|`xfsprogs`|	XFS filesystem utilities.|N|
|`f2fs-tools`|Tools for Flash-Friendly File System (F2FS).|N|
|`jfsutils`|	JFS filesystem utilities.|N|zen
|`lvm2`|	Logical Volume Manager 2 utilities.|N|
|`dmraid`|Device mapper RAID interface.|N|
|`mdadm`|A tool for managing/monitoring Linux md device arrays, also known as Software RAID	.|N|

#### <a name="5a3"></a> **CPU**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`amd-ucode`|Microcode update image for AMD CPUs.|N|
|`intel-ucode`|Microcode update files for Intel CPUs.|N|

#### <a name="5a4"></a> **Bootloaous kernel (when you arder**

Choose either Grub or Refind.

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`grub`|	GNU GRand Unified Bootloader (2).|N|
|`refind`|An EFI boot manager	.|N|
|`os-prober`|Utility to detect other OSes on a set of drives.|N|
|`efibootmgr`|Linux user-space application to modify the EFI Boot Manager.|N|

#### <a name="5a5"></a> **CLI Text Editors**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`less`|A terminal based program for viewing text files.|N|
|`nano`|	Pico editor clone with enhancements.|N| 
|`vim`|Vi Improved, a highly configurable, improved version of the vi text editor.|N|
|`vi`|The original ex/vi text editor.|N|

*Set default with `export EDITOR=(PACKAGE)`*

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

### <a name="5b"></a> **Additional Packages**

The base package does not include all tools from the live installation, so installing other packages may be necessary for a fully functional base system. In particular, consider installing:

***[Back to Table of Contents](#TOC)***

#### <a name="5b1"></a>**System Utilities**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`openssh`|Premier connectivity tool for remote login with the SSH protocol.|Y|
|`cronie`|Daemon that runs specified programs at scheduled times and related tools.|Y|
|`xdg-user-dirs`|Manage user directories like ~/Desktop and ~/Music.|Y|  
|`haveged`|Entropy harvesting daemon using CPU timings.|Y|
|`bash-completion`|Programmable completion for the bash shell.|N|
|`man-db`|A utility for reading man pages|N|  
|`man-pages`|Linux man pages.|N|
|`texinfo`|GNU documentation system for on-line information and printed output.|N|
|`lsb-release`|LSB version query program.|N|
|`polkit`|Application development toolkit for controlling system-wide privileges.|N| 
|`unrar`|The RAR uncompression program.|N|
|`zip`|Compressor/archiver for creating and modifying zipfiles.|N|
|`unzip`|	For extracting and viewing files in .zip archives|N|
|`p7zip`|Command-line file archiver with high compression ratio.|N|
|`unace`|An extraction tool for the proprietary ace archive format.|N|  
|`xz`|Library and command line tools for XZ and LZMA compressed files.|N|
|`lzop`|File compressor using lzo lib.|N|
|`bashtop`|Linux resource monitor	|N|
|`htop`|Linux resource monitor	|N|
|`neofetch`|A CLI system information tool written in BASH that supports displaying images.|N|
|`ncdu`|Disk usage analyzer with an ncurses interface.|N|
|`mc`|Midnight Commander a CLI File Manager|N|  
|`nmon`|AIX & Linux Performance Monitoring tool|N|
|`archiso`|Tools for creating Arch Linux live and install iso images.|N|
|`perl`|A highly capable, feature-rich programming language|N|
|`python`|Next generation of the python high-level scripting language|N|
|`xf86-input-synaptics`|Synaptics driver for notebook touchpads.|N|
|`ddrescue`|GNU data recovery tool.|N|
|`dd_rescue`|A dd version that is very useful for data-recovery.|N|
|`testdisk`|Checks and undeletes partitions + PhotoRec, signature based recovery tool.|N|
|`hardinfo`|A system information and benchmark tool.|N|
|`hwinfo`|Hardware detection tool from openSUSE.|N|

***[Back to Table of Contents](#TOC)***

#### <a name="5b2"></a> **Networking**

##### <a name="5b2a"></a> **General**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`network-manager-applet`|Applet for managing network connections|N|  
|`net-snmp`|A suite of applications used to implement SNMP v1, SNMP v2c and SNMP v3 using both IPv4 and IPv6.|N|
|`samba`|SMB Fileserver and AD Domain server.|N|
|`smbnetfs`|small C program that mounts Microsoft network neighborhood in single directory.|N|
|`smbclient`|Tools to access a server's filespace and printers via SMB.|N|
|`nmap`|Utility for network discovery and security auditing.|N|
|`traceroute`|Tracks the route taken by packets over an IP network.|N|
|`rsync`|A fast and versatile file copying tool for remote and local files.|N|
|`grsync`|GTK+ GUI for rsync to synchronize folders, files and make backups.|N|
|**`firewalld`**|Firewall daemon with D-Bus interface.|Y|
|**`ufw`**|Uncomplicated and easy to use CLI tool for managing a netfilter firewall	.|Y|
|*`gufw`*|Uncomplicated way to manage your Linux firewall|N|
|*`ufw-extras`*|Extra configuration files for UFW|N|

***[Back to Table of Contents](#TOC)***

##### <a name="5b2b"></a> **Wi-Fi**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`wpa_supplicant`|A utility providing key negotiation for WPA wireless networks.|N|

***[Back to Table of Contents](#TOC)***

##### <a name="5b2c"></a> **Bluetooth**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`blueman`|A GTK+ Bluetooth Manager (BlueZ 5) - git|N|
|`bluez-utils`|Development and debugging utilities for the bluetooth protocol stack. Includes deprecated tools.|N|
|`bluez`|Libraries and tools for the Bluetooth protocol stack.|N|
|`bluez-libs`|Libraries for the bluetooth protocol stack.|N|

To enable bluetooth, run `systemctl enable bluetooth` and `systemctl start bluetooth`

***[Back to Table of Contents](#TOC)***

#### <a name="5b3"></a> **Video**

##### <a name="5b3b"></a> **Nvidia**

|Type|Driver|OpenGL|OpenGL (Multilib)|Documentation|
|:---:|:---:|:---:|:---:|:---:|
|Open source|`xf86-video-nouveau`|`mesa`|`lib32-mesa`|[Nouveau](https://wiki.archlinux.org/index.php/Nouveau)|
|Proprietary|`nvidia`|`nvidia-utils`|`lib32-nvidia-utils`|[NVIDIA](https://wiki.archlinux.org/index.php/NVIDIA)|
|Proprietary|`nvidia-390xx` *AUR*|`nvidia-390xx-utils` *AUR*|`lib32-nvidia-390xx-utils` *AUR*|[NVIDIA](https://wiki.archlinux.org/index.php/NVIDIA)|

`nvidia-settings`  

**NOTE:** *install `nvidia-dkms` and add nvidia to the modules for mkinitcpio, use `sudo nano /etc/mkinitcpio.conf` edit the file "MODULES=(nvidia)" and run `sudo mkinitcpio -P`*

***[Back to Table of Contents](#TOC)***

##### <a name="5b3c"></a> **AMD**

|Type|Driver|OpenGL|OpenGL (Multilib)|Documentation|
|:---:|:---:|:---:|:---:|:---:|
|Open source|`xf86-video-amdgpu`|`mesa`|`lib32-mesa`|[AMDGPU](https://wiki.archlinux.org/index.php/AMDGPU)|
|Open source|`xf86-video-ati`|`mesa`|`lib32-mesa`|[ATI](https://wiki.archlinux.org/index.php/ATI)|

`vulkan-radeon`  
`xf86-video-amdgpu`  
`catalyst`  
`catalyst=total-hd234k`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b3d"></a> **Intel**

|Type|Driver|OpenGL|OpenGL (Multilib)|Documentation|
|:---:|:---:|:---:|:---:|:---:|
|Open source|`xf86-video-intel`|`mesa`|`lib32-mesa`|[Intel graphics](https://wiki.archlinux.org/index.php/Intel_graphics)|

For hybrid graphics install `optimus-manager`

***[Back to Table of Contents](#TOC)***

#### <a name="5b4"></a> **Sound**

**Pulseaudio**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`pulseaudio`|A featureful, general-purpose sound server|
|`pulseeffects`|Audio Effects for Pulseaudio Applications.|N|
|`pulseaudio-bluetooth`|Bluetooth support for PulseAudio.|N|
|`pulseaudio-equalizer`|Equalizer for PulseAudio.|N|

**Alsa**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`alsa-utils`|A patched version of the alsa-utils package to support transparent terminals.|N|
|`alsa-plugins`|Additional ALSA plugins.|N|
|`lib32-alsa-plugins`|Additional ALSA plugins.|N|
|`pulseaudio-alsa`|ALSA Configuration for PulseAudio.|N|

***[Back to Table of Contents](#TOC)***

#### <a name="5b5"></a>**Printing**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`cups`|The CUPS Printing System - daemon package.|Y|
|`cups-pdf`|PDF printer for cups.|N|
|`hplip`|Drivers for HP DeskJet, OfficeJet, Photosmart, Business Inkjet and some LaserJet.|N|
|`system-config-printer`|A CUPS printer configuration tool and status applet.|N|
|`foomatic-db`|Foomatic - The collected knowledge about printers, drivers, and driver options in XML files, used by foomatic-db-engine to generate PPD files.|N|
|`foomatic-db-engine`|Foomatic - Foomatic's database engine generates PPD files from the data in Foomatic's XML database. It also contains scripts to directly generate print queues and handle jobs.|N|
|`foomatic-db-ppds`|Foomatic - PPDs from printer manufacturers.|N|
|`foomatic-db-nonfree-ppds`|Foomatic - non-free PPDs from printer manufacturers.|N|
|`foomatic-db-nonfree`|Foomatic - database extension consisting of manufacturer-supplied PPD files released under non-free licenses.|N|
|`foomatic-gutenprint-ppds`|simplified prebuilt ppd files.|N|
|`gutenprint`|Top quality printer drivers for POSIX systems.|N|
|`ghostscript`|An interpreter for the PostScript language.|N|

***[Back to Table of Contents](#TOC)***

#### <a name="5b6"></a> **XORG**

##### <a name="5b6a"></a> **XORG Apps**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`xorg`|Graphical Server Package Group, see [xorg](#7nb) for details.|N|
|`xorg-xinit`|X.Org initialisation program.|N|
|`xorg-apps`|Additional applications for xorg, see [xorg-apps](#7nc) for details.|N|
|`xorg-drivers`|Additional Drivers for xorg, see [xorg-drivers](#7nd) for details.|N|


***[Back to Table of Contents](#TOC)***

##### <a name="5b6b"></a> **Fonts**

|**Name**|**Description**|
|:---:|:---:|
|`font-bh-ttf`|X.org Luxi Truetype fonts| 
|`gsfonts`|(URW)++ Core Font Set.|
|`sdl_ttf`|A library that allows you to use TrueType fonts in your SDL applications	.|
|`ttf-bitstream-vera`|Bitstream Vera fonts.|  
|`ttf-dejavu`|Font family based on the Bitstream Vera Fonts with a wider range of characters.|
|`ttf-liberation`|Red Hats Liberation fonts.|
|`xorg-fonts-type1`|X.org Type1 fonts.|
|`ttf-ubuntu-font-family`|Ubuntu font family.|
|`noto-fonts`|Google Noto TTF fonts.|
|`ttf-opensans`|	Google Noto TTF fonts.|

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

#### <a name="5b7"></a> **Display Managers**

##### <a name="5b7a"></a> **[GDM](https://wiki.archlinux.org/index.php/GDM)**

GNOME display manager.  

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`gdm`|Display manager and login screen	||Y| 

(Also included in `gnome` package group)  

`systemctl enable gdm.service`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b7b"></a> **[LightDM](https://wiki.archlinux.org/index.php/LightDM)**

Cross-desktop display manager, can use various front-ends written in any toolkit.  

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`lightdm`|A lightweight display manager	|Y|
|`lightdm-gtk-greeter`|Default Greeter|N|

`systemctl enable lightdm.service`  

***[Back to Lightdm Login Manager Configuration](#6b)***
***[Back to Table of Contents](#TOC)***

##### <a name="5b7c"></a> **[LXDM](https://wiki.archlinux.org/index.php/LXDM)**

display manager. Can be used independent of the LXDE desktop environment.  

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`lxdm`|Lightweight X11 Display Manager.|Y|
|`lxdm-gtk3`|Lightweight X11 Display Manager (GTK+ 3 version).|Y|

`systemctl enable lxdm.service`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b7d"></a> **[SDDM](https://wiki.archlinux.org/index.php/SDDM)**

QML-based display manager and successor to KDM; recommended for Plasma and LXQt. 

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`sddm`|QML based X11 and Wayland display manager.|Y|
|`sddm-kcm`|KDE Config Module for SDDM.|N|
  
`systemctl enable sddm.service`  

***[Back to Table of Contents](#TOC)***

##### <a name="5b7e"></a> **[XDM](https://wiki.archlinux.org/index.php/XDM)**

X display manager with support for XDMCP, host chooser.  

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`xorg-xdm`|X Display Manager	|Y|

`systemctl enable xdm.service`  

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

#### <a name="5b8"></a> **Desktop Environments**

##### <a name="5b8a"></a> **[Budgie](https://wiki.archlinux.org/index.php/Budgie)** 

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`budgie-desktop`|Modern desktop environment from the Solus Project.|N|
|`gnome`|Gnome desktop environment package group, see [gnome](#7ne) for details.|N|
|`gnome-extra`|Gnome desktop environment extras, see [gnome-extra](#7nf) for details.|N|

***[Back to Table of Contents](#TOC)***

##### <a name="5b8b"></a> **[Cinnamon](https://wiki.archlinux.org/index.php/Cinnamon)**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`cinnamon`|Linux desktop which provides advanced innovative features and a traditional user experience.|N|
|`nemo`|	Cinnamon file manager (Nautilus fork)|N|
|`nemo-fileroller`|File archiver extension for Nemo|N|
|`metacity`|Window manager of GNOME Flashback	(Fallback mode)|N|
|`gnome-shell`|Next generation desktop shell (Fallback mode)|N|

***[Back to Table of Contents](#TOC)***

##### <a name="5b8c"></a> **[Deepin](https://wiki.archlinux.org/index.php/Deepin)**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`deepin`|The Deepin Desktop Environment.|N|
|`deepin-extra`|extra applications for a more complete desktop environment.|N|

*To be able to use the integrated network administration, the networkmanager package is required, and the NetworkManager.service must be started and enabled.*

***[Back to Table of Contents](#TOC)***

##### <a name="5b8d"></a> **[GNOME](https://wiki.archlinux.org/index.php/GNOME)**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`gnome`|Gnome desktop environment package group, see [gnome](#7ne) for details.|N|
|`gnome-extra`|Gnome desktop environment extras, see [gnome-extra](#7nf) for details.|N|

***[Back to Table of Contents](#TOC)***

##### <a name="5b8e"></a> **[KDE Plasma](https://wiki.archlinux.org/index.php/KDE_Plasma)**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`plasma`|KDE Plasma Desktop, See [plasma](#7ni) for details|
|`plasma-meta`|Meta package to install KDE Plasma(Full)|
|`plasma-desktop`|KDE Plasma Desktop (Minimum)|
|`kde-applications`|KDE Applications, See [kde-applications](#7nj) for details|
|`kde-applications-meta`|Meta package for KDE Applications|

To enable support for Wayland in Plasma, also install the `plasma-wayland-session` package. 

***[Back to Table of Contents](#TOC)***

##### <a name="5b8f"></a> **[MATE](https://wiki.archlinux.org/index.php/MATE)**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|rent, but the solution is the same: co
|`mate`|An intuitive and attractive desktop environment|N|
|`mate-extra`|additional utilities and applications that integrate well with the MATE desktop|N|

***[Back to Table of Contents](#TOC)***

##### <a name="5b8g"></a> **[XFCE](https://wiki.archlinux.org/index.php/Xfce)**

|**Name**|**Description**|**Enable Service**|
|:---:|:---:|:---:|
|`xfce4`|lightweight and modular desktop environment|N|
|`xfce4-goodies`|extra plugins and a number of useful utilities|N|

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

#### <a name="5b9"></a> **Applications**

##### <a name="5b9a"></a> **System**

|**Name**|**Description**|
|:---:|:---:|
|`gparted`|*Disk Partitioner*|
|`gnome-disk-utility`|*Disk Utility*|
|`baobab`|*Disk Usage*|
|`tilda`| *Terminal*|
|`terminator`| *Terminal*|
|`xdg-utils`| *Editing Config Files*|
|`gprename`|*File Renamer*|
|`grub-customizer`|*Grub Customizer*|
|`yelp`|*Help*|
|`namcap`|*PKGBUILDs checker*|
|`wavemon`|*CLI Wifi Scanner*|
|`bleachbit`| *System Cleaner*|
|`dconf-editor`|*Config Editor*|
|`parcellite`| *Clipboard Manager*|

***[Back to Table of Contents](#TOC)***

##### <a name="5b9b"></a> **Office**

|**Name**|**Description**|
|:---:|:---:|
|`libreoffice-fresh`| *Office Suite*|
|`xreader`| *Document Reader*|
|`galculator`|*Calculator*|
|`xed`| *Text Editor*|
|`gedit`|*GNOME Text Editor*|
|`pandoc`|*Markdown Export Tools*|
|`discount`|*Markdown Export Tools*|
|`calibre`|*eBook Manager*|
|`inkscape`| *Vector Image Editor*|

***[Back to Table of Contents](#TOC)***

##### <a name="5b9c"></a> **Internet**

|**Name**|**Description**|
|:---:|:---:|
|`firefox`|*Web Browser*
|`geary`|*E-Mail Client*|
|`evolution`|*E-Mail Client*|
|`qbittorrent`|*Bittorrent client*|

***[Back to Table of Contents](#TOC)***

##### <a name="5b9d"></a> **Multimedia**

|**Name**|**Description**|
|:---:|:---:|
|`cmus`|*Command Line Music Player*|
|`vlc`|*Media Player*|
|`celluloid`|*Media Player*|

***[Back to Table of Contents](#TOC)***

###### <a name="5b9da"></a> **CODECS**

**Audio**

|**Name**|**Description**|
|:---:|:---:|
|`flac`|Free Lossless Audio Codec|
|`wavpack`|Audio compression format with lossless, lossy and hybrid compression modes|
|`lame`|A high quality MPEG Audio Layer III (MP3) encoder|
|`faac`|Freeware Advanced Audio Coder|
|`faad2`|ISO AAC audio decoder|
|`celt`|Low-latency audio communication codec|
|`a52dec`|A free library for decoding ATSC A/52 streams|
|`libdca`|Free library for decoding DTS Coherent Acoustics streams|
|`libmad`|A high-quality MPEG audio decoder|
|`libmpcdec`|MusePack decoding library|
|`opencore-amr`|Open source implementation of the Adaptive Multi Rate (AMR) speech codec|
|`opus`|Totally open, royalty-free, highly versatile audio codec|
|`speex`|A free codec for free speech|
|`libvorbis`|Reference implementation of the Ogg Vorbis audio format|
|`libfdk-aac`|Fraunhofer FDK AAC codec library|
|`fdkaac`|Command line encoder frontend for libfdk-aac|

**Video**

|**Name**|**Description**|
|:---:|:---:|
|`libmpeg2`|Library for decoding MPEG-1 and MPEG-2 video streams.|
|`x264`|Open Source H264/AVC video encoder|
|`x265`|Open Source H265/HEVC video encoder|
|`libdv`|The Quasar DV codec (libdv) is a software codec for DV video|
|`xvidcore`|XviD is an open source MPEG-4 video codec|
|`ffmpeg`|Complete solution to record, convert and stream audio and video|

**Images**

|**Name**|**Description**|
|:---:|:---:|
|`jasper`|Software-based implementation of the codec specified in the emerging JPEG-2000 Part-1 standard|
|`libwebp`|WebP library and conversion tools|

##### <a name="5b9e"></a> **Photo / Image Editing**

|**Name**|**Description**|
|:---:|:---:|
|`gimp`| *Photo Editor*|
|`digikam`|*Raw Photo Tool*|
|`darktable`|*Raw Photo Tool*|
|`rawtherapee`|*Raw Photo Software*|
|`shotwell`|*Photo Manager*|
|`hugin`|*Panorma Software*|
|`gnome-screenshot`|*Screenshot*|

***[Back to Table of Contents](#TOC)***

##### <a name="5b9f"></a> **Misc**Packages

|**Name**|**Description**|
|:---:|:---:|
|`sl`|*CLI Train*|
|`lolcat`|*CLI Rainbow Effect*|
|`cmatrix`|*Matrix on CLI*|

***[Back to Installation](#3)***  
***[Back to Table of Contents](#TOC)***

### <a name="5c"></a> **Boot loader**

Choose and install a Linux-capable boot loader. If you have an Intel or AMD CPU, enable microcode updates in addition.

Recommended is the ***[Grub](https://www.archlinux.org/packages/?name=grub)*** bootloader.

***[Back to Table of Contents](#TOC)***

#### <a name="5ca"></a> **MBR**

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

#### <a name="5cb"></a> **UEFI**

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

### <a name="5d"></a> **Microcode**

Processor manufacturers release stability and security updates to the processor microcode. These updates provide bug fixes that can be critical to the stability of your system. Without them, you may experience spurious crashes or unexpected system halts that can be difficult to track down.

All users with an AMD or Intel CPU should install the microcode updates to ensure system stability.

For AMD processors, install the `amd-ucode` package.

For Intel processors, install the `intel-ucode` package.

If your Arch installation is on a removable drive that needs to have microcode for both manufacturer processors, install both packages.

***[Back to Table of Contents](#TOC)***

#### <a name="5da"></a> **GRUB**

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

#### <a name="5db"></a> **rEFInd**

Edit boot options in /boot/refind_linux.conf and add initrd=boot\cpu_manufacturer-ucode.img (or initrd=cpu_manufacturer-ucode.img if /boot is a separate partition) as the first initramfs. For example:

`"Boot using default options"     "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw add_efi_memmap initrd=boot\cpu_manufacturer-ucode.img initrd=boot\initramfs-%v.img"`

> **Tip:** Users who previously did not specify an initrd kernel parameter will need to follow the steps described in rEFInd#Configuration to enable passing of multiple initrd parameters.

Users employing manual stanzas in esp/EFI/refind/refind.conf to define the kernels should simply add initrd=boot\cpu_manufacturer-ucode.img (or initrd=cpu_manufacturer-ucode.img if /boot is a separate partition) as required to the options line, and not in the main part of the stanza. E.g.:

`options  "root=PARTUUID=XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX rw add_efi_memmap initrd=boot\cpu_manufacturer-ucode.img"`

***[Back to Table of Contents](#TOC)***

### <a name="5e"></a> **Reboot**

Before rebooting, ensure you have at least a DHCP client installed and unmount your efi and root partitions:

`umount /dev/sdaX`

*amend for whatever setup you have*

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

>nmcli device wifi connect *SSID* p(Enable service)assword *password*

Connect to a hidden network:

>nmcli device wifi connect *SSID* password *password* hidden yes

Connect to a wifi on the wlan1 wifi interface:

>nmcli device wifi connect *SSID* password *password* ifname wlan1 profile_name

Disconnect an interface:

>nmcli device disconnect ifname eth0

Reconnect an interface marked as disconnected:

>nmcli connection up uuid *UUID*

Get a list of UUIDs:n also get a potat

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

`systemctl enable NetworkManager.service`  
`systemctl enable sshd.service`  
`systemctl enable cronie.service`  
`systemctl enable havegd.service`  
`systemctl enable bluetooth.service`  
`systemctl enable org.cups.cupsd.service`  
`systemctl enable ufw.service`

*Choose Applicable*
`systemctl enable gdm.service`  
`systemctl enable lightdm.service`  
`systemctl enable lxdm.service`  
`systemctl enable sddm.service`  
`systemctl enable xdm.service`  

***[Back to Table of Contents](#TOC)***

### <a name="6b"></a> **Lightdm Login Manager Configuration**

If you need lightdm as your display manager install it and enable it, see: **[Lightdm](#5b7b)**

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

`sudo pacman -S papirus-icon-theme`
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

### <a name="6i"></a> **Additional AUR Apps**

|**Command**|**Description**|
|:---:|:---:|
|`yay pamac`| *Pacman GUI*|
|`yay xviewer`| *Image Viewer*|
|`yay pix-git`| *Image Viewer*|
|`yay lollypop`| *Music Player*|
|`yay picard`|*Music Tagger*|
|``yay xplayer`|*Media Player*|
|`yay spotify`|*Music Streaming*|
|`yay google-chrome`|*Web Browser*|
|`yay msgviewer`|*Outlook msg viewer*|
|`yay teams`|*Microsoft Teams*|
|`yay whatsapp-nativefier-dark`|*Whatsapp*|
|`yay bitwarden`|*Password Manager*|
|`yay thonny`|*Python IDE*|
|`yay timeshift`|*Recovery*|
|`yay freeoffice`| *Office Suite*|
|`yay focuswriter`|*Markdown / Text Editor*|
|`yay haroopad`|*Markdown Editor*|
|`yay remarkable`|*Markdown Editor*|
|`yay ghostwriter`|*Markdown Editor*|
|`yay multimarkdown`|*Markdown Export Tools*|
|`yay commonmark`|*Markdown Export Tools*|
|`yay kindlegen`|*eBook CLI Convertor*|
|`yay koreader`|*Epub Reader*|
|`yay sigil`|*Epub Editor*|
|`yay joplin`|*Markdown Editor / Notebook*|
|`yay cherrytree`|*Notebook*|
|`yay grub2-theme-vimix-git`|*Grub Arch Theme*|
|`yay system-log`|*System Log GUI*|
|`yay gnome-system-monitor`|*System monitor GUI*|
|`yay balena-etcher`|*USB Flasher*|
|`yay gtkhash`|*Hash Check Utility*|
|`yay ttf-ms-fonts`|*Microsoft Fonts*|
|`yay netdiscover`|*Network scanner with MAC vendors*|


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

***[Back to Table of Contents](#TOC)***

### <a name="7ma"></a> **Identify Boot Delays**

**Analyze boot times**

`systemd-analyze`

`systemd-analyze blame`

Check startup Applications for anything unnecessary.

***[Back to Table of Contents](#TOC)***

### <a name="7mb"></a> **Unable to mount from fstab at boot (Dependencies Failed)**

If this is a duelboot system, this could be an issue with the NTFS volume, try the following:

- Ensure secureboot is off on windows.  
- Run `sudo ntfsfix /dev/sda2` Ensuring the destination drive is correct) 
- Check the fstab file to ensure its correct. 

***[Back to Table of Contents](#TOC)***

### <a name="7n"></a> **Package Groups**

#### <a name="7na"></a> **base-devel**

Below is a list of the packages contained within `base-devel`

|**Name**|**Description**|
|:---:|:---:|
|`autoconf`|A GNU tool for automatically configuring source code|
|`automake`|A GNU tool for automatically creating Makefiles|
|`binutils`|A set of programs to assemble and manipulate binary and object files|
|`bison`|The GNU general-purpose parser generator|
|`fakeroot`|Tool for simulating superuser privileges|
|`file`|File type identification utility|
|`findutils`|GNU utilities to locate files|
|`flex`|A tool for generating text-scanning programs|
|`gawk`|GNU version of awk|
|`gcc`|The GNU Compiler Collection - C and C++ frontends|
|`gettext`|GNU internationalization library|
|`grep`|A string search utility|
|`groff`|GNU troff text-formatting system|
|`gzip`|GNU compression utility|
|`libtool`|A generic library support script|
|`m4`|The GNU macro processor|
|`make`|GNU make utility to maintain groups of programs|
|`pacman`|A library-based package manager with dependency support|
|`patch`|A utility to apply patch files to original sources|
|`pkgconf`|Package compiler and linker metadata toolkit|
|`sed`|GNU stream editor|
|`sudo`|Give certain users the ability to run some commands as root|
|`texinfo`|GNU documentation system for on-line information and printed output|
|`which`|A utility to show the full path of commands|

***[Back to Essentials](#5a1)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nb"></a> **xorg**

**xorg group**

|**Name**|**Description**|
|:---:|:---:|
|`xf86-video-vesa`|X.org vesa video driver|
|`xorg-bdftopcf`|Convert X font from Bitmap Distribution Format to Portable Compiled Format|
|`xorg-docs`|X.org documentations|
|`xorg-font-util`|X.Org font utilities|
|`xorg-fonts-100dpi`|X.org 100dpi fonts|
|`xorg-fonts-75dpi`|X.org 75dpi fonts|
|`xorg-fonts-encodings`|X.org font encoding files|
|`xorg-iceauth`|ICE authority file utility|
|`xorg-luit`|Filter that can be run between an arbitrary application and a UTF-8 terminal emulator|
|`xorg-mkfontscale`|Create an index of scalable font files for X|
|`xorg-server`|Xorg X server|
|`xorg-server-common`|Xorg server common files|
|`xorg-server-devel`|Development files for the X.Org X server|
|`xorg-server-xephyr`|A nested X server that runs as an X application|
|`xorg-server-xnest`|A nested X server that runs as an X application|
|`xorg-server-xvfb`|Virtual framebuffer X server|
|`xorg-server-xwayland`|run X clients under wayland|
|`xorg-sessreg`|Register X sessions in system utmp/utmpx databases|
|`xorg-setxkbmap`|Set the keyboard using the X Keyboard Extension|
|`xorg-smproxy`|Allows X applications that do not support X11R6 session management to participate in an X11R6 session|
|`xorg-x11perf`|Simple X server performance benchmarker|
|`xorg-xauth`|X.Org authorization settings program|
|`xorg-xbacklight`|RandR-based backlight control application|
|`xorg-xcmsdb`|Device Color Characterization utility for X Color Management System|
|`xorg-xcursorgen`|Create an X cursor file from PNG images|
|`xorg-xdpyinfo`|Display information utility for X|
|`xorg-xdriinfo`|Query configuration information of DRI drivers|
|`xorg-xev`|Print contents of X events|
|`xorg-xgamma`|Alter a monitor's gamma correction|
|`xorg-xhost`|Server access control program for X|
|`xorg-xinput`|Small commandline tool to configure devices|
|`xorg-xkbcomp`|X Keyboard description compiler|
|`xorg-xkbevd`|XKB event daemon|
|`xorg-xkbutils`|XKB utility demos|
|`xorg-xkill`|Kill a client by its X resource|
|`xorg-xlsatoms`|List interned atoms defined on server|
|`xorg-xlsclients`|List client applications running on a display|
|`xorg-xmodmap`|Utility for modifying keymaps and button mappings|
|`xorg-xpr`|Print an X window dump from xwd|
|`xorg-xprop`|Property displayer for X|
|`xorg-xrandr`|Primitive command line interface to RandR extension|
|`xorg-xrdb`|X server resource database utility|
|`xorg-xrefresh`|Refresh all or part of an X screen|
|`xorg-xset`|User preference utility for X|
|`xorg-xsetroot`|Classic X utility to set your root window background to a given pattern or color|
|`xorg-xvinfo`|Prints out the capabilities of any video adaptors associated with the display that are accessible through the X-Video extension|
|`xorg-xwd`|X Window System image dumping utility|
|`xorg-xwininfo`|Command-line utility to print information about windows on an X server|
|`xorg-xwud`|X Window System image undumping utility|

***[Back to XORG](#5b6)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nc"></a> **xorg-apps**

|**Name**|**Description**|
|:---:|:---:|
|`xorg-bdftopcf`|Convert X font from Bitmap Distribution Format to Portable Compiled Format|
|`xorg-iceauth`|ICE authority file utility|
|`xorg-luit`|Filter that can be run between an arbitrary application and a UTF-8 terminal emulator|
|`xorg-mkfontscale`|Create an index of scalable font files for X|
|`xorg-sessreg`|Register X sessions in system utmp/utmpx databases|
|`xorg-setxkbmap`|Set the keyboard using the X Keyboard Extension|
|`xorg-smproxy`|Allows X applications that do not support X11R6 session management to participate in an X11R6 session|
|`xorg-x11perf`|Simple X server performance benchmarker|
|`xorg-xauth`|X.Org authorization settings program|
|`xorg-xbacklight`|RandR-based backlight control application|
|`xorg-xcmsdb`|Device Color Characterization utility for X Color Management System|
|`xorg-xcursorgen`|Create an X cursor file from PNG images|
|`xorg-xdpyinfo`|Display information utility for X|
|`xorg-xdriinfo`|Query configuration information of DRI drivers|
|`xorg-xev`|Print contents of X events|
|`xorg-xgamma`|Alter a monitor's gamma correction|
|`xorg-xhost`|Server access control program for X|
|`xorg-xinput`|Small commandline tool to configure devices|
|`xorg-xkbcomp`|X Keyboard description compiler|
|`xorg-xkbevd`|XKB event daemon|
|`xorg-xkbutils`|XKB utility demos|
|`xorg-xkill`|Kill a client by its X resource|
|`xorg-xlsatoms`|List interned atoms defined on server|
|`xorg-xlsclients`|List client applications running on a display|
|`xorg-xmodmap`|Utility for modifying keymaps and button mappings|
|`xorg-xpr`|Print an X window dump from xwd|
|`xorg-xprop`|Property displayer for X|
|`xorg-xrandr`|Primitive command line interface to RandR extension|
|`xorg-xrdb`|X server resource database utility|
|`xorg-xrefresh`|Refresh all or part of an X screen|
|`xorg-xset`|User preference utility for X|
|`xorg-xsetroot`|Classic X utility to set your root window background to a given pattern or color|
|`xorg-xvinfo`|Prints out the capabilities of any video adaptors associated with the display that are accessible through the X-Video extension|
|`xorg-xwd`|X Window System image dumping utility|
|`xorg-xwininfo`|Command-line utility to print information about windows on an X server|
|`xorg-xwud`|X Window System image undumping utility|

***[Back to XORG](#5b6)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nd"></a> **xorg-drivers**

|**Name**|**Description**|
|:---:|:---:|
|`xf86-input-evdev`|X.org evdev input driver|
|`xf86-input-libinput`|Generic input driver for the X.Org server based on libinput|
|`xf86-input-synaptics`|Synaptics driver for notebook touchpads|
|`xf86-input-vmmouse`|X.org VMWare Mouse input driver|
|`xf86-input-void`|X.org void input driver|
|`xf86-video-amdgpu`|X.org amdgpu video driver|
|`xf86-video-ati`|X.org ati video driver|
|`xf86-video-dummy`|X.org dummy video driver|
|`xf86-video-fbdev`|X.org framebuffer video driver|
|`xf86-video-intel`|X.org Intel i810/i830/i915/945G/G965+ video drivers|
|`xf86-video-nouveau`|Open Source 3D acceleration driver for nVidia cards|
|`xf86-video-openchrome`|X.Org Openchrome drivers|
|`xf86-video-qxl`|Xorg X11 qxl video driver|
|`xf86-video-vesa`|X.org vesa video driver|
|`xf86-video-vmware`|X.org vmware video driver|
|`xf86-video-voodoo`|X.org 3dfx Voodoo1/Voodoo2 2D video driver|

***[Back to XORG](#5b6)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7ne"></a> **gnome**

|**Name**|**Description**|
|:---:|:---:|
|`baobab`|A graphical directory tree analyzer|
|`cheese`|Take photos and videos with your webcam, with fun graphical effects|
|`eog`|Eye of Gnome: An image viewing and cataloging program|
|`epiphany`|A GNOME web browser based on the WebKit rendering engine|
|`evince`|Document viewer (PDF, Postscript, djvu, tiff, dvi, XPS, SyncTex support with gedit, comics books (cbr,cbz,cb7 and cbt))|
|`file-roller`|Create and modify archives|
|`gdm`|Display manager and login screen|
|`gedit`|GNOME Text Editor|
|`gnome-backgrounds`|Background images and data for GNOME|
|`gnome-books`|Access and organize your e-books on GNOME|
|`gnome-boxes`|Simple GNOME application to access remote or virtual systems|
|`gnome-calculator`|GNOME Scientific calculator|
|`gnome-calendar`|Simple and beautiful calendar application designed to perfectly fit the GNOME desktop|
|`gnome-characters`|A character map application|
|`gnome-clocks`|Clocks applications for GNOME|
|`gnome-color-manager`|GNOME Color Profile Tools|
|`gnome-contacts`|Contacts Manager for GNOME|
|`gnome-control-center`|GNOME's main interface to configure various aspects of the desktop|
|`gnome-disk-utility`|Disk Management Utility for GNOME|
|`gnome-documents`|A document manager application for GNOME|
|`gnome-font-viewer`|A font viewer utility for GNOME|
|`gnome-getting-started-docs`|Help a new user get started in GNOME|
|`gnome-keyring`|Stores passwords and encryption keys|
|`gnome-logs`|A log viewer for the systemd journal|
|`gnome-maps`|A simple GNOME 3 maps application|
|`gnome-menus`|GNOME menu specifications|
|`gnome-music`|Music player and management application|
|`gnome-photos`|Access, organize, and share your photos on GNOME|
|`gnome-remote-desktop`|GNOME Remote Desktop server|
|`gnome-screenshot`|Take pictures of your screen|
|`gnome-session`|The GNOME Session Handler|
|`gnome-settings-daemon`|GNOME Settings Daemon|
|`gnome-shell`|Next generation desktop shell|
|`gnome-shell-extensions`|Extensions for GNOME shell, including classic mode|
|`gnome-software`|GNOME Software Tools|
|`gnome-system-monitor`|View current processes and monitor system state|
|`gnome-terminal`|The GNOME Terminal Emulator|
|`gnome-themes-extra`|Extra Themes for GNOME Applications|
|`gnome-user-docs`|User documentation for GNOME|
|`gnome-user-share`|Easy to use user-level file sharing for GNOME|
|`gnome-video-effects`|Collection of GStreamer effects for GNOME|
|`gnome-weather`|Access current weather conditions and forecasts|
|`grilo-plugins`|A collection of plugins for the Grilo framework|
|`gvfs`|Virtual filesystem implementation for GIO|
|`gvfs-afc`|Virtual filesystem implementation for GIO (AFC backend; Apple mobile devices)|
|`gvfs-goa`|Virtual filesystem implementation for GIO (Gnome Online Accounts backend; cloud storage)|
|`gvfs-google`|Virtual filesystem implementation for GIO (Google Drive backend)|
|`gvfs-gphoto2`|Virtual filesystem implementation for GIO (gphoto2 backend; PTP camera, MTP media player)|
|`gvfs-mtp`|Virtual filesystem implementation for GIO (MTP backend; Android, media player)|
|`gvfs-nfs`|Virtual filesystem implementation for GIO (NFS backend)|
|`gvfs-smb`|Virtual filesystem implementation for GIO (SMB/CIFS backend; Windows client)|
|`mutter`|A window manager for GNOME|
|`nautilus`|Default file manager for GNOME|
|`networkmanager`|Network connection manager and user applications|
|`orca`|Screen reader for individuals who are blind or visually impaired|
|`rygel`|UPnP AV MediaServer and MediaRenderer that allows you to easily share audio, video and pictures, and control of media player on your home network|
|`simple-scan`|Simple scanning utility|
|`sushi`|A quick previewer for Nautilus|
|`totem`|Movie player for the GNOME desktop based on GStreamer|
|`tracker`|Desktop-neutral user information store, search tool and indexer|
|`tracker-miners`|Collection of data extractors for Tracker/Nepomuk|
|`vino`|A VNC server for the GNOME desktop|
|`xdg-user-dirs-gtk`|Creates user dirs and asks to relocalize them|
|`yelp`|Get help with GNOME|

***[Back to Budgie](#5b8a)***  
***[Back to Gnome](#5b8d)***   
***[Back to Table of Contents](#TOC)***

#### <a name="7nf"></a> **gnome-extra**

|**Name**|**Description**|
|:---:|:---:|
|`accerciser`|Interactive Python accessibility explorer for the GNOME desktop|
|`dconf-editor`|dconf Editor|
|`devhelp`|API documentation browser for GNOME|
|`evolution`|Manage your email, contacts and schedule|
|`five-or-more`|Remove colored balls from the board by forming lines|
|`four-in-a-row`|Make lines of the same color to win|
|`ghex`|A simple binary editor for the Gnome desktop|
|`glade`|User Interface Builder for GTK+ applications|
|`gnome-builder`|An IDE for writing GNOME-based software|
|`gnome-chess`|Play the classic two-player boardgame of chess|
|`gnome-devel-docs`|Developer documentation for GNOME|
|`gnome-klotski`|Slide blocks to solve the puzzle|
|`gnome-mahjongg`|Disassemble a pile of tiles by removing matching pairs|
|`gnome-mines`|Clear hidden mines from a minefield|
|`gnome-nettool`|Graphical interface for various networking tools|
|`gnome-nibbles`|Guide a worm around a maze|
|`gnome-robots`|Avoid the robots and make them crash into each other|
|`gnome-sound-recorder`|A utility to make simple audio recording from your GNOME desktop|
|`gnome-sudoku`|Test your logic skills in this number grid puzzle|
|`gnome-taquin`|Move tiles so that they reach their places|
|`gnome-tetravex`|Complete the puzzle by matching numbered tiles|
|`gnome-todo`|Task manager for GNOME|
|`gnome-tweaks`|Graphical interface for advanced GNOME 3 settings (Tweak Tool)|
|`hitori`|GTK+ application to generate and let you play games of Hitori|
|`iagno`|Dominate the board in a classic version of Reversi|
|`lightsoff`|Turn off all the lights|
|`polari`|An IRC Client for GNOME|
|`quadrapassel`|Fit falling blocks together (Tetris-like game for GNOME)|
|`swell-foop`|Clear the screen by removing groups of colored and shaped tiles|
|`sysprof`|Kernel based performance profiler|
|`tali`|Beat the odds in a poker-style dice game|
|`gnome-code-assistance`|Code assistance services for GNOME|
|`gnome-multi-writer`|Write an ISO file to multiple USB devices at once|
|`gnome-recipes`|Recipe management application for GNOME|
|`gnome-usage`|GNOME application to view information about use of system resources|

***[Back to Budgie](#5b8a)***  
***[Back to Gnome](#5b8d)***   
***[Back to Table of Contents](#TOC)***

#### <a name="7ng"></a> **deepin**

|**Name**|**Description**|
|:---:|:---:|
|`deepin-account-faces`|Account faces for Linux Deepin|
|`deepin-anything`|Deepin Anything file search tool|
|`deepin-api`|Golang bindings for dde-daemon|
|`deepin-calendar`|Calendar for Deepin Desktop Environment|
|`deepin-control-center`|New control center for linux deepin|
|`deepin-daemon`|Daemon handling the DDE session settings|
|`deepin-desktop-base`|Base component for Deepin|
|`deepin-desktop-schemas`|GSettings deepin desktop-wide schemas|
|`deepin-dock`|Deepin desktop-environment - dock module|
|`deepin-file-manager`|Deepin File Manager|
|`deepin-gtk-theme`|Deepin GTK Theme|
|`deepin-icon-theme`|Deepin Icons|
|`deepin-image-viewer`|Deepin Image Viewer|
|`deepin-kwin`|KWin configures on DDE|
|`deepin-launcher`|Deepin desktop-environment - Launcher module|
|`deepin-menu`|Deepin menu service for building beautiful menus|
|`deepin-network-utils`|DDE network utils|
|`deepin-polkit-agent`|Deepin Polkit Agent|
|`deepin-polkit-agent-ext-gnomekeyring`|GNOME keyring extension for dde-polkit-agent|
|`deepin-qt5integration`|Qt platform theme integration plugins for DDE|
|`deepin-qt5platform-plugins`|Qt platform plugins for DDE|
|`deepin-screensaver`|Deepin screensaver viewer and tools|
|`deepin-session-shell`|Deepin desktop-environment - session-shell module|
|`deepin-session-ui`|Deepin desktop-environment - Session UI module|
|`deepin-shortcut-viewer`|Deepin Shortcut Viewer|
|`deepin-sound-theme`|Deepin sound theme|
|`deepin-system-monitor`|A more user-friendly system monitor|
|`deepin-turbo`|A daemon that helps to launch applications faster|
|`deepin-wallpapers`|Default wallpapers for DDE|
|`startdde`|starter of deepin desktop environment|

***[Back to Deepin](#5b8c)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nh"></a> **deepin-extra**

|**Name**|**Description**|
|:---:|:---:|
|`deepin-album`|A fashion photo manager for viewing and organizing pictures|
|`deepin-boot-maker`|Tool to create a bootable usb stick quick and easy|
|`deepin-calculator`|An easy to use calculator for ordinary users|
|`deepin-clipboard`|DDE clipboard manager component|
|`deepin-clone`|Disk and partition backup/restore tool|
|`deepin-community-wallpapers`|Community wallpapers for DDE|
|`deepin-compressor`|A fast and lightweight application for creating and extracting archives|
|`deepin-draw`|A lightweight drawing tool for Linux Deepin|
|`deepin-editor`|Simple editor for Deepin|
|`deepin-movie`|Movie player based on QtAV|
|`deepin-music`|Awesome music player with brilliant and tweakful UI Deepin-UI based.|
|`deepin-picker`|Color picker tool for deepin|
|`deepin-printer`|Printer configuration project for DDE|
|`deepin-reader`|A simple PDF reader, supporting bookmarks, highlights and annotations|
|`deepin-screen-recorder`|Deepin Screen Recorder|
|`deepin-screensaver-pp`|Optional PP screensaver resource for deepin screensaver|
|`deepin-screenshot`|Easy-to-use screenshot tool for linuxdeepin desktop environment|
|`deepin-terminal`|Default terminal emulation application for Deepin|
|`deepin-voice-note`|A lightweight memo tool to make text notes and voice recordings|

***[Back to Deepin](#5b8c)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7ni"></a> **plasma**

|**Name**|**Description**|
|:---:|:---:|
|`bluedevil`|Integrate the Bluetooth technology within KDE workspace and applications|
|`breeze`|Artwork, styles and assets for the Breeze visual style for the Plasma Desktop|
|`breeze-gtk`|Breeze widget theme for GTK 2 and 3|
|`discover`|KDE and Plasma resources management GUI|
|`drkonqi`|The KDE crash handler|
|`kactivitymanagerd`|System service to manage user's activities and track the usage patterns|
|`kde-cli-tools`|Tools based on KDE Frameworks 5 to better interact with the system|
|`kde-gtk-config`|GTK2 and GTK3 Configurator for KDE|
|`kdecoration`|Plugin based library to create window decorations|
|`kdeplasma-addons`|All kind of addons to improve your Plasma experience|
|`kgamma5`|Adjust your monitor's gamma settings|
|`khotkeys`|KHotKeys|
|`kinfocenter`|A utility that provides information about a computer system|
|`kmenuedit`|KDE menu editor|
|`knetattach`|Wizard which makes it easier to integrate network resources with the Plasma Desktop|
|`kscreen`|KDE's screen management software|
|`kscreenlocker`|Library and components for secure lock screen architecture|
|`ksshaskpass`|ssh-add helper that uses kwallet and kpassworddialog|
|`ksysguard`|Track and control the processes running in your system|
|`kwallet-pam`|KWallet PAM integration|
|`kwayland-integration`|Provides integration plugins for various KDE frameworks for the wayland windowing system|
|`kwayland-server`|Wayland server components built on KDE Frameworks|
|`kwin`|An easy to use, but flexible, composited Window Manager|
|`kwrited`|KDE daemon listening for wall and write messages|
|`libkscreen`|KDE screen management software|
|`libksysguard`|Library to retrieve information on the current status of computer hardware|
|`milou`|A dedicated search application built on top of Baloo|
|`oxygen`|KDE Oxygen style|
|`plasma-browser-integration`|Components necessary to integrate browsers into the Plasma Desktop|
|`plasma-desktop`|KDE Plasma Desktop|
|`plasma-integration`|Qt Platform Theme integration plugins for the Plasma workspaces|
|`plasma-nm`|Plasma applet written in QML for managing network connections|
|`plasma-pa`|Plasma applet for audio volume management using PulseAudio|
|`plasma-sdk`|Applications useful for Plasma development|
|`plasma-thunderbolt`|Plasma integration for controlling Thunderbolt devices|
|`plasma-vault`|Plasma applet and services for creating encrypted vaults|
|`plasma-workspace`|KDE Plasma Workspace|
|`plasma-workspace-wallpapers`|Additional wallpapers for the Plasma Workspace|
|`polkit-kde-agent`|Daemon providing a polkit authentication UI for KDE|
|`powerdevil`|Manages the power consumption settings of a Plasma Shell|
|`sddm-kcm`|KDE Config Module for SDDM|
|`systemsettings`|KDE system manager for hardware, software, and workspaces|
|`user-manager`|A simple system settings module to manage the users of your system|
|`xdg-desktop-portal-kde`|A backend implementation for xdg-desktop-portal using Qt/KF5|

***[Back to KDE Plasma](#5b8e)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nj"></a> **kde-applications**

|**Name**|**Description**|
|:---:|:---:|
|`akonadi-calendar-tools`|CLI tools to manage akonadi calendars
|`akonadi-import-wizard`|Import data from other mail clients to KMail
|`akonadiconsole`|Akonadi management and debugging console
|`akregator`|A Feed Reader by KDE
|`ark`|Archiving Tool
|`artikulate`|Improve your pronunciation by listening to native speakers
|`audiocd-kio`|Kioslave for accessing audio CDs
|`blinken`|Memory Enhancement Game
|`bomber`|A single player arcade game
|`bovo`|A Gomoku like game for two players
|`cantor`|KDE Frontend to Mathematical Software
|`cervisia`|CVS Frontend
|`dolphin`|KDE File Manager
|`dolphin-plugins`|Extra Dolphin plugins
|`dragon`|A multimedia player where the focus is on simplicity, instead of features
|`elisa`|A simple music player aiming to provide a nice experience for its users
|`ffmpegthumbs`|FFmpeg-based thumbnail creator for video files
|`filelight`|View disk usage information
|`granatier`|A clone of the classic Bomberman game
|`grantlee-editor`|Editor for Grantlee themes
|`gwenview`|A fast and easy to use image viewer
|`juk`|A jukebox, tagger and music collection manager
|`k3b`|Feature-rich and easy to handle CD burning application
|`kaddressbook`|KDE contact manager
|`kajongg`|The ancient Chinese board game for 4 players
|`kalarm`|Personal alarm scheduler
|`kalgebra`|Graph Calculator
|`kalzium`|Periodic Table of Elements
|`kamera`|KDE integration for gphoto2 cameras
|`kamoso`|A webcam recorder from KDE community
|`kanagram`|Letter Order Game
|`kapman`|A clone of the well known game Pac-Man
|`kapptemplate`|KDE Template Generator
|`kate`|Advanced Text Editor
|`katomic`|A fun and educational game built around molecular geometry
|`kbackup`|A program that lets you back up any directories or files
|`kblackbox`|A game of hide and seek played on a grid of boxes
|`kblocks`|The classic falling blocks game
|`kbounce`|A single player arcade game with the elements of puzzle
|`kbreakout`|A Breakout-like game
|`kbruch`|Exercise Fractions
|`kcachegrind`|Visualization of Performance Profiling Data
|`kcalc`|Scientific Calculator
|`kcharselect`|Character Selector
|`kcolorchooser`|Color Chooser
|`kcron`|Configure and schedule tasks
|`kde-dev-scripts`|Scripts and setting files useful during development of KDE software
|`kde-dev-utils`|Small utilities for developers using KDE/Qt libs/frameworks
|`kdebugsettings`|An application to enable/disable qCDebug
|`kdeconnect`|Adds communication between KDE and your smartphone
|`kdegraphics-mobipocket`|A collection of plugins to handle mobipocket files
|`kdegraphics-thumbnailers`|Thumbnailers for various graphics file formats
|`kdenetwork-filesharing`|Properties dialog plugin to share a directory with the local network
|`kdenlive`|A non-linear video editor for Linux using the MLT video framework
|`kdepim-addons`|Addons for KDE PIM applications
|`kdesdk-kioslaves`|KDE SDK KIO-Slaves
|`kdesdk-thumbnailers`|Plugins for the thumbnailing system
|`kdf`|View Disk Usage
|`kdialog`|A utility for displaying dialog boxes from shell scripts
|`kdiamond`|A single player puzzle game
|`keditbookmarks`|Bookmark Organizer and Editor
|`kfind`|Find Files/Folders
|`kfloppy`|Floppy Formatter
|`kfourinline`|A four-in-a-row game
|`kgeography`|Geography Trainer
|`kget`|Download Manager
|`kgoldrunner`|A game of action and puzzle solving
|`kgpg`|A GnuPG frontend
|`khangman`|Hangman Game
|`khelpcenter`|Application to show KDE Applications' documentation
|`kig`|Interactive Geometry
|`kigo`|An open-source implementation of the popular Go game
|`killbots`|A simple game of evading killer robots
|`kimagemapeditor`|HTML Image Map Editor
|`kio-extras`|Additional components to increase the functionality of KIO
|`kipi-plugins`|A collection of plugins extending the KDE graphics and image applications
|`kirigami-gallery`|Gallery application built using Kirigami
|`kiriki`|An addictive and fun dice game
|`kiten`|Japanese Reference/Study Tool
|`kjumpingcube`|A simple tactical game
|`kleopatra`|Certificate Manager and Unified Crypto GUI
|`klettres`|Learn The Alphabet
|`klickety`|An adaptation of the Clickomania game
|`klines`|A simple but highly addictive one player game
|`kmag`|Screen Magnifier
|`kmahjongg`|A tile matching game for one or two players
|`kmail`|KDE mail client
|`kmail-account-wizard`|KMail account wizard
|`kmines`|The classic Minesweeper game
|`kmix`|KDE volume control program
|`kmousetool`|Clicks the mouse for you, reducing the effects of RSI
|`kmouth`|Speech Synthesizer Frontend
|`kmplot`|Mathematical Function Plotter
|`knavalbattle`|A ship sinking game
|`knetwalk`|Connect all the terminals to the server, in as few turns as possible
|`knights`|Chess board by KDE with XBoard protocol support
|`knotes`|Popup notes
|`kolf`|A miniature golf game with 2d top-down view
|`kollision`|A simple ball dodging game
|`kolourpaint`|Paint Program
|`kompare`|Graphical file differences tool
|`konqueror`|KDE File Manager & Web Browser
|`konquest`|The KDE version of Gnu-Lactic
|`konsole`|KDE's terminal emulator
|`kontact`|KDE Personal Information Manager
|`kopete`|Instant Messenger
|`korganizer`|Calendar and scheduling Program
|`kpatience`|Offers a selection of solitaire card games
|`krdc`|Remote Desktop Client
|`kreversi`|A simple one player strategy game played against the computer
|`krfb`|Desktop Sharing
|`kross-interpreters`|Language interpreters to enable in-process scripting with Kross
|`kruler`|Screen Ruler
|`kshisen`|A solitaire-like game played using the standard set of Mahjong tiles
|`ksirk`|A computerized version of a well known strategy game
|`ksnakeduel`|A simple snake duel game
|`kspaceduel`|Each of two possible players controls a satellite spaceship orbiting the sun
|`ksquares`|A game modeled after the well known pen and paper based game of Dots and Boxes
|`ksudoku`|A logic-based symbol placement puzzle
|`ksystemlog`|System log viewer tool
|`kteatime`|A handy timer for steeping tea
|`ktimer`|Countdown Launcher
|`ktouch`|Touch Typing Tutor
|`ktuberling`|A simple constructor game suitable for children and adults alike
|`kturtle`|Educational Programming Environment
|`kubrick`|Based on the famous Rubik's Cube
|`kwalletmanager`|Wallet management tool
|`kwave`|A sound editor for KDE
|`kwordquiz`|Flash Card Trainer
|`kwrite`|Text Editor
|`lokalize`|Computer-Aided Translation System
|`lskat`|Lieutenant Skat is a fun and engaging card game for two players
|`marble`|Desktop Globe
|`mbox-importer`|Import mbox files to KMail
|`minuet`|A KDE Software for Music Education
|`okular`|Document Viewer
|`palapeli`|A single-player jigsaw puzzle game
|`parley`|Vocabulary Trainer
|`picmi`|A nonogram logic game for KDE
|`pim-data-exporter`|Import and export KDE PIM settings
|`pim-sieve-editor`|Mail sieve editor
|`poxml`|Translates DocBook XML files using gettext po files
|`print-manager`|A tool for managing print jobs and printers
|`rocs`|Graph Theory IDE
|`signon-kwallet-extension`|KWallet integration for signon framework
|`spectacle`|KDE screenshot capture utility
|`step`|Interactive Physical Simulator
|`svgpart`|A KPart for viewing SVGs
|`sweeper`|System Cleaner
|`telepathy-kde-accounts-kcm`|KCM Module for configuring Telepathy Instant Messaging Accounts
|`telepathy-kde-approver`|KDE Channel Approver for Telepathy
|`telepathy-kde-auth-handler`|Provide UI/KWallet Integration For Passwords and SSL Errors on Account Connect
|`telepathy-kde-call-ui`|Voice/Video Call UI for Telepathy
|`telepathy-kde-common-internals`|Common components for KDE-Telepathy
|`telepathy-kde-contact-list`|KDE Telepathy contact list application
|`telepathy-kde-contact-runner`|KRunner plugin for KDE Telepathy
|`telepathy-kde-desktop-applets`|The KDE-Telepathy Plasma desktop applets
|`telepathy-kde-filetransfer-handler`|KDE Telepathy file transfer handler
|`telepathy-kde-integration-module`|Sits in KDED and takes care of various bits of system integration like setting user to auto-away or handling connection errors
|`telepathy-kde-send-file`|A File manager plugin to launch a file transfer job with a specified contact
|`telepathy-kde-text-ui`|Telepathy handler for Text Chats
|`umbrello`|UML modeller
|`yakuake`|A drop-down terminal emulator based on KDE konsole technology
|`zeroconf-ioslave`|Network Monitor for DNS-SD services (Zeroconf)

***[Back to KDE Plasma](#5b8e)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nk"></a> **mate**

|**Name**|**Description**|
|:---:|:---:|
|`caja`|File manager for the MATE desktop|
|`marco`|A window manager for MATE|
|`mate-backgrounds`|Background images and data for MATE|
|`mate-control-center`|The Control Center for MATE|
|`mate-desktop`|Library with common API for various MATE modules|
|`mate-icon-theme`|MATE icon theme|
|`mate-menus`|MATE menu specifications|
|`mate-notification-daemon`|Notification daemon for MATE|
|`mate-panel`|The MATE Panel|
|`mate-polkit`|PolicyKit integration for the MATE desktop|
|`mate-session-manager`|The MATE Session Handler|
|`mate-settings-daemon`|The MATE Settings daemon|
|`mate-themes`|Default themes for the MATE desktop|
|`mate-user-guide`|MATE User Guide|

***[Back to Mate](#5b8f)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nl"></a> **mate-extra**

|**Name**|**Description**|
|:---:|:---:|
|`atril`|MATE document viewer|
|`caja-image-converter`|A Caja extension for simple image conversions|
|`caja-open-terminal`|A Caja extension for opening terminals in arbitrary local paths|
|`caja-sendto`|A Caja extension for sending files|
|`caja-share`|A Caja extension to quickly share a folder|
|`caja-wallpaper`|A Caja extension to quickly set wallpaper|
|`caja-xattr-tags`|A Caja extension to see tags stored on xattrs|
|`engrampa`|Archive manipulator for MATE|
|`eom`|An image viewing and cataloging program for MATE|
|`mate-applets`|Applets for MATE panel|
|`mate-calc`|Calculator for the MATE desktop environment|
|`mate-icon-theme-faenza`|Faenza icon theme for MATE|
|`mate-media`|MATE Media Tools|
|`mate-netbook`|A simple window management tool|
|`mate-power-manager`|Power management tool for the MATE desktop|
|`mate-screensaver`|Screensaver for MATE|
|`mate-sensors-applet`|A MATE Panel applet to display readings from hardware sensors, including CPU temperature, fan speeds and voltage readings|
|`mate-system-monitor`|A system monitor for MATE|
|`mate-terminal`|The MATE Terminal Emulator|
|`mate-user-share`|User level public file sharing via WebDAV for MATE|
|`mate-utils`|Common MATE utilities for viewing disk usage, logs and fonts, taking screenshots, managing dictionaries and searching files|
|`mozo`|MATE menu editing tool|
|`pluma`|A powerful text editor for MATE|

***[Back to Mate](#5b8f)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nm"></a> **xfce4**

|**Name**|**Description**|
|:---:|:---:|
|`exo`|Application library for Xfce|
|`garcon`|Implementation of the freedesktop.org menu specification|
|`thunar`|Modern file manager for Xfce|
|`thunar-volman`|Automatic management of removeable devices in Thunar|
|`tumbler`|D-Bus service for applications to request thumbnails|
|`xfce4-appfinder`|An application finder for Xfce|
|`xfce4-panel`|Panel for the Xfce desktop environment|
|`xfce4-power-manager`|Power manager for Xfce desktop|
|`xfce4-session`|A session manager for Xfce|
|`xfce4-settings`|Settings manager of the Xfce desktop|
|`xfce4-terminal`|A modern terminal emulator primarily for the Xfce desktop environment|
|`xfconf`|Flexible, easy-to-use configuration management system|
|`xfdesktop`|A desktop manager for Xfce|
|`xfwm4`|Xfce's window manager|
|`xfwm4-themes`|A set of additional themes for the Xfce window manager|

***[Back to XFCE4](#5b8g)***  
***[Back to Table of Contents](#TOC)***

#### <a name="7nn"></a> **xfce4-goodies**

|**Name**|**Description**|
|:---:|:---:|
|`mousepad`|Simple text editor for Xfce|
|`orage`|A simple calendar application with reminders for Xfce|
|`ristretto`|Fast and lightweight picture-viewer for Xfce4|
|`thunar-archive-plugin`|Create and extract archives in Thunar|
|`thunar-media-tags-plugin`|Adds special features for media files to the Thunar File Manager|
|`xfburn`|A simple CD/DVD burning tool based on libburnia libraries|
|`xfce4-artwork`|Backdrops for the Xfce4 desktop|
|`xfce4-battery-plugin`|A battery monitor plugin for the Xfce panel|
|`xfce4-clipman-plugin`|A clipboard plugin for the Xfce4 panel|
|`xfce4-cpufreq-plugin`|CPU frequency plugin for the Xfce4 panel|
|`xfce4-cpugraph-plugin`|CPU graph plugin for the Xfce4 panel|
|`xfce4-datetime-plugin`|A date and time display plugin for the Xfce panel|
|`xfce4-dict`|A dictionary plugin for the Xfce panel|
|`xfce4-diskperf-plugin`|Plugin for the Xfce4 panel displaying instant disk/partition performance|
|`xfce4-eyes-plugin`|A rolling eyes (following mouse pointer) plugin for the Xfce panel|
|`xfce4-fsguard-plugin`|File system usage monitor plugin for the Xfce4 panel|
|`xfce4-genmon-plugin`|plugin that monitors customizable programs stdout for the Xfce4 panel|
|`xfce4-mailwatch-plugin`|Multi-protocol, multi-mailbox mail watcher for the Xfce4 panel|
|`xfce4-mount-plugin`|Mount/umount utility for the Xfce4 panel|
|`xfce4-mpc-plugin`|Control the Music Player Daemon from the Xfce4 panel|
|`xfce4-netload-plugin`|A netload plugin for the Xfce panel|
|`xfce4-notes-plugin`|A notes plugin for the Xfce4 panel|
|`xfce4-notifyd`|Notification daemon for the Xfce desktop|
|`xfce4-pulseaudio-plugin`|Pulseaudio plugin for Xfce4 panel|
|`xfce4-screensaver`|Xfce Screensaver|
|`xfce4-screenshooter`|Plugin that makes screenshots for the Xfce panel|
|`xfce4-sensors-plugin`|A lm_sensors plugin for the Xfce panel|
|`xfce4-smartbookmark-plugin`|Plugin for the Xfce4 panel that lets you quicksearch from selected websites|
|`xfce4-systemload-plugin`|A system load plugin for the Xfce4 panel|
|`xfce4-taskmanager`|Easy to use task manager|
|`xfce4-time-out-plugin`|Take a break from your computer with this plugin for Xfce4|
|`xfce4-timer-plugin`|Plugin to track time for the Xfce4 panel|
|`xfce4-verve-plugin`|Command line plugin Xfce4 panel|
|`xfce4-wavelan-plugin`|Plugin to monitor wifi connectivity for the Xfce4 panel|
|`xfce4-weather-plugin`|A weather plugin for the Xfce4 panel|
|`xfce4-xkb-plugin`|Plugin to switch keyboard layouts for the Xfce4 panel|
|`parole`|Modern media player based on the GStreamer framework|
|`xfce4-whiskermenu-plugin`|Menu for Xfce4|

***[Back to XFCE4](#5b8g)***  
***[Back to Table of Contents](#TOC)***

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

This dumps the results into a graphical SVG file for details analysis.

`systemd-analyze plot > plot.svg`

This command prints a tree of the time-critical chain of units (for each of the specified UNIT s or for the default target otherwise). The time after the unit is active or started is printed after the "@" character.

`systemd-analyze critical-chain [ UNIT ...]`

If a boot delay is caused by `man-db` then disable the service with:

`systemctl disable man-db.service`

And ensure you either manually run `mandb` after updates or add to script.

***[Back to Table of Contents](#TOC)***

#### <a name="8ad"></a> **Crash Investigation**

1. List recent boots with `last -F | sort -r` if you see entries for crashes then proceed to find out more details.

2. To list boot records run: `journalctl --list-boots | less`

3. Match the records from step 1 and two using the date and times provided.

*From Step One:*
>adam     tty7         :0               <mark>*Fri Jul  3 17:55:39 2020*</mark> - crash                     (17:33)

*From Step Two*
><mark>**-85**</mark> ed5637fe3bab4d058e16b7baa25bfc8a <mark>*Fri 2020-07-03 17:55:39 BST—Fri 2020-07-03 22:01:01 BST*</mark>
 
4. Run the command `journalctl -b -ID -e` using the ID from step two at the beginning of the entry, for example: `journalctl -b -85 -e`

5. This will display the errors

***[Back to Table of Contents](#TOC)***

### <a name="8b"></a> **CLI Extras**

#### <a name="8ba"></a> **Password Astrisk**

Run `visudo` and add the following line:

>Defaults pwfeedback

***[Back to Table of Contents](#TOC)***

#### <a name="8bc"></a> **Export Man Pages**

**HTML**

`BROWSER=firefox man -H <command>`

 or
 
`man -Thtml (command)<(filename).html>`   
*Requires `groff` and `gropdf`*

**PDF**

`man -Tpdf (command)<(filename).pdf>`  
*Requires `groff` and `gropdf`*

***[Back to Table of Contents](#TOC)***
