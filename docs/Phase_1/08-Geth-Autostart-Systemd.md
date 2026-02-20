# Phase 3 — systemd Service Setup

## Why systemd?

A production node must:

- Auto start on reboot
- Restart on failure
- Run under a dedicated user
- Have resource limits defined

systemd provides:
- Process supervision
- Controlled restart policies
- Logging via journald
- Boot-time integration

---

## Service Design Decisions

### Dedicated User
Geth runs as a system user:
- Username: `geth`
- No shell access
- Home: `/var/lib/geth`

Reason:
Principle of least privilege.

---

### Data Directory

/var/lib/geth => standard location for persistent services.

> user creation
```bash
sudo mkdir -p /var/lib/geth

sudo useradd --system -d /var/lib/geth geth

sudo usermod geth:geth /var/lib/geth
```
 
> OP of passwd file


```bash 
mukul in  Ubuntu-24 in ~
❯ getent passwd | tail -n 2
mukul:x:1000:1000::/home/mukul:/bin/bash
geth:x:999:988::/var/lib/geth:/bin/sh

```

### Restart = always 
 self healing behavour in case crash.

### LimitNOFILE = (1024*1024)65535

[🗃️ CONFIG_FILE: /etc/systemd/system/geth.service](../../files/2_Config_New/geth.service)

Blockchanin  uses many peer connections so many files.

- service enable at boot.
-  Verified auto start after reboot 
- Conformed restart policy worked 
```bash

sudo pkill -9 geth
```

### Observed logs using 

```bash  
journalctl -u geth -f / -b / -b -1
```
 
