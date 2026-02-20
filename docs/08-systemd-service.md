# Phase 3 — systemd Service Setup

## Why systemd?

A production node must:

- Start automatically on reboot
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


### Restart = always 
 self healing behavour in case crash.

### LimitNOFILE = (1024*1024)65535

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
 
