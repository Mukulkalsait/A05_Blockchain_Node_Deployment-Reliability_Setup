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

