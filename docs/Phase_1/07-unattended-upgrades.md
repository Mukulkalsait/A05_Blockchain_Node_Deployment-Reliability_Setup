# Unattended Security Upgrades

## Objective
Ensure timely installation of critical security patches without manual intervention.

## Configuration
- Enabled automatic security updates
- Limited scope to security-related packages
- Default scheduling used

## Why This Matters
- Reduces exposure window for known vulnerabilities
- Essential for long-running, unattended servers
- Standard baseline for production systems

## Risk Considerations
- Non-security upgrades excluded
- Manual oversight retained for major changes

## Validation
- Confirmed unattended-upgrades service active
- Verified configuration file settings

```bash 

mukul in  Ubuntu-24 in ~ took 3s
❯ sudo apt list | grep upgrades

WARNING: apt does not have a stable CLI interface. Use with caution in scripts.

unattended-upgrades/noble,now 2.9.1+nmu4ubuntu1 all [installed]


mukul in  Ubuntu-24 in ~ took 3s
❯ sudo apt install unattended-upgrades -y  

# After installation 

mukul in  Ubuntu-24 in ~
❯ sudo dpkg-re
dpkg-realpath     dpkg-reconfigure

mukul in  Ubuntu-24 in ~
❯ sudo dpkg-reconfigure --priority=low unattended-upgrades
 
```
