# Basic System Checks

## Objective
Validate OS, kernel, CPU, memory, disk, and network state before deploying services.

```bash 
uname -a # for kernal configuration
lsb_release # for ubuntu version and all information
cat /etc/os-release # for version of any dextro

lscpu # CPU information

free -h # ram information

lsblk -f # for storages and mounts

# Network information 
ip a
ip link

# Netwokr test
ping -c 3 8.8.8.8
```

## Checks Performed
- OS version and distribution
- Kernel version
- CPU architecture and cores
- Block devices and mount points
- Disk usage
- Network interfaces and IP configuration

## Why This Matters
- Confirms compatibility with blockchain clients
- Establishes a baseline for future troubleshooting
- Helps identify resource constraints early

## Observations
- OS matched expected LTS release
- Disk layout suitable for stateful workloads
- Network configuration stable with public access

## Outcome
System verified as ready for user creation and service hardening.

> Orignal OP

```bash 
mukul in  Ubuntu-24 in ~
❯ uname -a
Linux Ubuntu-24 6.8.0-100-generic #100-Ubuntu SMP PREEMPT_DYNAMIC  x86_64 x86_64 x86_64 GNU/Linux

mukul in  Ubuntu-24 in ~
❯ lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.4 LTS
Release:        24.04
Codename:       noble

mukul in  Ubuntu-24 in ~
❯ cat /etc/os-release
PRETTY_NAME="Ubuntu 24.04.4 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04.4 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo

mukul in  Ubuntu-24 in ~
❯ lscpu | head
Architecture:                            x86_64
CPU op-mode(s):                          32-bit, 64-bit
Address sizes:                           40 bits physical, 48 bits virtual
Byte Order:                              Little Endian
CPU(s):                                  1
On-line CPU(s) list:                     0
Vendor ID:                               GenuineIntel
Model name:                              DO-Regular
CPU family:                              6
Model:                                   79

mukul in  Ubuntu-24 in ~
❯ free -h
               total        used        free      shared  buff/cache   available
Mem:           961Mi       462Mi       189Mi       4.3Mi       473Mi       498Mi
Swap:             0B          0B          0B

mukul in  Ubuntu-24 in ~
❯ lsblk -f
NAME    FSTYPE  FSVER LABEL           UUID                                 FSAVAIL FSUSE% MOUNTPOINTS
vda
├─vda1  ext4    1.0   cloudimg-rootfs d36f7414-beb7-45e0-900e-9ab79cdbcb2d   19.6G    15% /
├─vda14
├─vda15 vfat    FAT32 UEFI            0683-2D32                              98.2M     6% /boot/efi
└─vda16 ext4    1.0   BOOT            cc2d5907-a56d-4ba5-b398-19d5f860a9e1  702.3M    13% /boot
vdb     iso9660       config-2        2026-02-04-08-50-54-00

mukul in  Ubuntu-24 in ~
❯ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 12:42:cc:ea:42:4e brd ff:ff:ff:ff:ff:ff
    altname enp0s3
    altname ens3
    inet 64.227.160.199/20 brd 64.227.175.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet 10.47.0.5/16 brd 10.47.255.255 scope global eth0
       valid_lft forever preferred_lft forever
    inet6 fe80::1042:ccff:feea:424e/64 scope link
       valid_lft forever preferred_lft forever
3: eth1: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether aa:63:13:ea:06:53 brd ff:ff:ff:ff:ff:ff
    altname enp0s4
    altname ens4
    inet 10.122.0.2/20 brd 10.122.15.255 scope global eth1
       valid_lft forever preferred_lft forever
    inet6 fe80::a863:13ff:feea:653/64 scope link
       valid_lft forever preferred_lft forever

mukul in  Ubuntu-24 in ~
❯ ping -c 3 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=117 time=14.4 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=117 time=13.3 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=117 time=13.3 ms

--- 8.8.8.8 ping statistics ---
3 packets transmitted, 3 received, 0% packet loss, time 2003ms
rtt min/avg/max/mdev = 13.304/13.663/14.361/0.493 ms
```
