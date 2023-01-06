---
layout: post
title:  "Rocky Linux"
permalink:
categories: OS 
---



## Rocky Linux

As one of the pupular Linux distributions, CentOS is widely used; not to mention that it served as a commmunity vereion of the Red Hat enterprise Linux. On December 8, 2020, Red Hat announced that they would discontinue development of CentOS. Gregory Kurtzer, one of the original founders of CentOS, announced that he would start a new project to achieve the original goals of CentOS. Its name was chosen as a tribute to early CentOS co-founder Rocky McGaugh.By December 12, the code repository of Rocky Linux had become the top-trending repository on GitHub. 
The first Rocky Linux was officially released on April 30, 2021 The second release is version 8.4. Its version number is based on RHEL. On June 21, 2021, the stable release of Rocky Linux 8.4 was released. 

## Test
### Commandss

```
lsblk
lshw
lsblk
lscpu
uname
fdisk
yum
rpm
dnf

```

### Sysinfo
![screenshot is here](/images/screenshot.png)
```

[root@rocky-linux ~]# uname -a
Linux rocky-linux 4.18.0-372.32.1.el8_6.x86_64 #1 SMP Thu Oct 27 15:18:36 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux

[root@rocky ~]# cat /etc/os-release
NAME="Rocky Linux"
VERSION="8.6 (Green Obsidian)"
ID="rocky"
ID_LIKE="rhel centos fedora"
VERSION_ID="8.6"
PLATFORM_ID="platform:el8"
PRETTY_NAME="Rocky Linux 8.6 (Green Obsidian)"
ANSI_COLOR="0;32"
CPE_NAME="cpe:/o:rocky:rocky:8:GA"
HOME_URL="https://rockylinux.org/"
BUG_REPORT_URL="https://bugs.rockylinux.org/"
ROCKY_SUPPORT_PRODUCT="Rocky Linux"
ROCKY_SUPPORT_PRODUCT_VERSION="8"
REDHAT_SUPPORT_PRODUCT="Rocky Linux"
REDHAT_SUPPORT_PRODUCT_VERSION="8"
[root@rocky ~]#

[root@rocky-linux ~]# lsblk
NAME                MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
vda                 252:0    0  100G  0 disk
├─vda1              252:1    0    1G  0 part /boot
├─vda2              252:2    0  100M  0 part /boot/efi
└─vda3              252:3    0 98.9G  0 part
  ├─vg_virt-lv_root 253:0    0 97.9G  0 lvm  /
  └─vg_virt-lv_swap 253:1    0    1G  0 lvm
vdb                 252:16   0  366K  0 disk
vdc                 252:32   0   44K  0 disk


[root@rocky-linux ~]# fdisk -l
Disk /dev/vda: 100 GiB, 107374182400 bytes, 209715200 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0xea53f700

Device     Boot   Start       End   Sectors  Size Id Type
/dev/vda1  *       2048   2099199   2097152    1G 83 Linux
/dev/vda2       2099200   2303999    204800  100M ef EFI (FAT-12/16/32)
/dev/vda3       2304000 209715199 207411200 98.9G 8e Linux LVM


Disk /dev/vdb: 366 KiB, 374784 bytes, 732 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/vdc: 44 KiB, 45056 bytes, 88 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/mapper/vg_virt-lv_root: 97.9 GiB, 105117646848 bytes, 205307904 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes


Disk /dev/mapper/vg_virt-lv_swap: 1 GiB, 1073741824 bytes, 2097152 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes



```





### rpm( Red Hat Package Manager)
![screenshot is here](/images/Screenshot2.png)

```
[root@rocky-linux ~]# rpm -qi NetworkManager
Name        : NetworkManager
Epoch       : 1
Version     : 1.36.0
Release     : 9.el8_6
Architecture: x86_64
Install Date: Mon 07 Nov 2022 12:24:28 PM UTC
Group       : System Environment/Base
Size        : 6331945
License     : GPLv2+ and LGPLv2+
Signature   : RSA/SHA256, Tue 25 Oct 2022 07:52:04 AM UTC, Key ID 15af5dac6d745a60
Source RPM  : NetworkManager-1.36.0-9.el8_6.src.rpm
Build Date  : Tue 25 Oct 2022 07:36:24 AM UTC
Build Host  : ord1-prod-x86build004.svc.aws.rockylinux.org
Relocations : (not relocatable)
Packager    : infrastructure@rockylinux.org
Vendor      : Rocky
URL         : https://networkmanager.dev/
Summary     : Network connection manager and user applications
Description :
NetworkManager is a system service that manages network interfaces and
connections based on user or automatic configuration. It supports
Ethernet, Bridge, Bond, VLAN, Team, InfiniBand, Wi-Fi, mobile broadband
(WWAN), PPPoE and other devices, and supports a variety of different VPN
services.
```
![screenshot3 is here](/images/Screenshot3.png)


```
[root@rocky-linux ~]# rpm -q curl
curl-7.61.1-22.el8_6.4.x86_64
[root@rocky-linux ~]#
[root@rocky-linux ~]# rpm -ql curl
/usr/bin/curl
/usr/lib/.build-id
/usr/lib/.build-id/74
/usr/lib/.build-id/74/12d9a83b2a437be12d5c92b9182ea7c50d2745
/usr/share/doc/curl
/usr/share/doc/curl/BUGS
/usr/share/doc/curl/CHANGES
/usr/share/doc/curl/FAQ
/usr/share/doc/curl/FEATURES
/usr/share/doc/curl/MANUAL
/usr/share/doc/curl/README
/usr/share/doc/curl/RESOURCES
/usr/share/doc/curl/TODO
/usr/share/doc/curl/TheArtOfHttpScripting
/usr/share/man/man1/curl.1.gz
/usr/share/zsh/site-functions
/usr/share/zsh/site-functions/_curl
[root@rocky-linux ~]#
```

### YUM (Yellowdog Updater Modified)
![screenshot3 is here](/images/Screenshot4.png)

```
[root@rocky-linux ~]# yum list openssh
Last metadata expiration check: 1:53:17 ago on Fri 06 Jan 2023 01:55:03 AM UTC.
Installed Packages
openssh.x86_64                         8.0p1-13.el8                          @anaconda
Available Packages
openssh.x86_64                         8.0p1-16.el8                          baseos
[root@rocky-linux ~]# yum search wget
Last metadata expiration check: 1:53:47 ago on Fri 06 Jan 2023 01:55:03 AM UTC.
============================= Name Exactly Matched: wget =============================
wget.x86_64 : A utility for retrieving files using the HTTP or FTP protocols
[root@rocky-linux ~]# yum info wget
Last metadata expiration check: 1:54:07 ago on Fri 06 Jan 2023 01:55:03 AM UTC.
Available Packages
Name         : wget
Version      : 1.19.5
Release      : 10.el8
Architecture : x86_64
Size         : 733 k
Source       : wget-1.19.5-10.el8.src.rpm
Repository   : appstream
Summary      : A utility for retrieving files using the HTTP or FTP protocols
URL          : http://www.gnu.org/software/wget/
License      : GPLv3+
Description  : GNU Wget is a file retrieval utility which can use either the HTTP or
             : FTP protocols. Wget features include the ability to work in the
             : background while you are logged out, recursive retrieval of
             : directories, file name wildcard matching, remote file timestamp
             : storage and comparison, use of Rest with FTP servers and Range with
             : HTTP servers to retrieve files over slow or unstable connections,
             : support for Proxy servers, and configurability.
```

