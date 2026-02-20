# Fail2Ban Service

## Objective
Provide automated protection against repeated authentication failures.

## Protection Scope
- SSH authentication attempts
- Default jail configuration used

## Why Fail2Ban
- Lightweight and effective
- Complements firewall rules
- Reduces noise from automated attacks

## Operational Notes
- Service enabled at boot
- No aggressive tuning applied to avoid false positives

## Validation
- Service status confirmed running
- Logs verified for active monitoring

> Config File [Fail2Ban=/etc/fail2ban/sshd.jail](../../files/2_Config_New/sshd.jail)

> Orignal OP
```bash 
mukul in  Ubuntu-24 in ~
❯ sudo fail2ban-client status
Status
|- Number of jail:      1
`- Jail list:   sshd

mukul in  Ubuntu-24 in ~
❯ sudo fail2ban-client status sshd
Status for the jail: sshd
|- Filter
|  |- Currently failed: 4
|  |- Total failed:     5689
|  `- Journal matches:  _SYSTEMD_UNIT=sshd.service + _COMM=sshd
`- Actions
   |- Currently banned: 4
   |- Total banned:     555
   `- Banned IP list:   92.118.39.76 192.241.184.7 170.64.154.41 159.89.13.139

mukul in  Ubuntu-24 in ~
❯

```
