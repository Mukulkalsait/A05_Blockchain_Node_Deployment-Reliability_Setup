# Droplet Creation & SSH Access

## Objective
Provision a secure cloud VM suitable for running long-lived infrastructure services, with fast and reliable SSH access.

## Resource Selection
- Cloud Provider: DigitalOcean
- OS: Ubuntu 22.04 LTS
- Droplet Size: Selected based on anticipated blockchain node resource usage
- Networking: Public IPv4 enabled

## SSH Key Strategy
- Generated a **dedicated SSH key** for this project
- Avoided key reuse to reduce blast radius
- Key naming aligned with project for clarity

## SSH Alias Configuration
An SSH alias was configured locally to:
- Simplify repeated access
- Enable faster `rsync` and automation later
- Reduce human error when managing multiple servers

## Security Rationale
- Key-based authentication only (no passwords)
- Separation of access credentials per project
- Early foundation for automation and scripting

## Validation
- Verified SSH access using alias
- Confirmed password login was never enabled

