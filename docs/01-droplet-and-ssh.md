# Droplet Creation & SSH Access

## Objective
Provision a secure cloud VM suitable for running long-lived infrastructure services, with fast and reliable SSH access.

## Resource Selection
- Cloud Provider: DigitalOcean
- OS: Ubuntu 24.04 LTS
- Droplet Size: Selected based on anticipated blockchain node resource usage
- Networking: Public IPv4 enabled
> I have used 1gb/1cpu plan for setup and Configuration and then **UpSize** the droplet for running the whole geth.

## SSH Key Strategy
- Generated a **dedicated SSH key** for this project
- Avoided key reuse to reduce blast radius
- Key naming aligned with project for clarity

```bash 
ssh-keygen -t  ed25519 -f eth -C "mukuldk"
```

## SSH Alias Configuration
An SSH alias was configured locally to:
- Simplify repeated access
- Enable faster `rsync` and automation later
- Reduce human error when managing multiple servers

```bash
  # mukuldk user on droplet
  Host eth 
    HostName 64.***.**.***
    User mukul
    IdentityFile /home/mukuldk/.ssh/eth
```

## Security Rationale
- Key-based authentication only (no passwords)
- Separation of access credentials per project
- Early foundation for automation and scripting

## Validation
- Verified SSH access using alias
- Confirmed password login was never enabled

