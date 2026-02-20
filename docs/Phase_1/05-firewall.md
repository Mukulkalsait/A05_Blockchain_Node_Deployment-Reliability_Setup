# Firewall Configuration (UFW)

## Objective
Restrict network access to only what is explicitly required.

## Firewall Policy
- Default deny for incoming traffic
- Explicit allow for SSH
- All other ports blocked by default

## Why UFW
- Simple, readable rule management
- Suitable for single-node environments
- Reduces chance of misconfiguration

## Security Impact
- Minimizes exposure of unused services
- Protects against opportunistic scanning

## Validation
- Confirmed SSH access post-enablement
- Verified firewall status and active rules


> Orignal OP 
```bash 


mukul in  Ubuntu-24 in ~
❯ sudo ufw status verbose

Status: active
Logging: on (low)
Default: deny (incoming), allow (outgoing), disabled (routed)
New profiles: skip

To                         Action      From
--                         ------      ----
22/tcp (OpenSSH)           ALLOW IN    Anywhere
80,443/tcp (Nginx Full)    ALLOW IN    Anywhere

22/tcp (OpenSSH (v6))      ALLOW IN    Anywhere (v6)
80,443/tcp (Nginx Full (v6)) ALLOW IN    Anywhere (v6)


```
