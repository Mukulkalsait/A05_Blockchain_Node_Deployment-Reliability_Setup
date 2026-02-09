# SSHD Hardening

## Objective
Reduce attack surface on the primary remote access mechanism.

## Configuration Decisions
- Disabled root login
- Disabled password-based authentication
- Enforced SSH key-only access
- Retained default SSH port to avoid security-through-obscurity

## Why These Changes
- Root login is a high-value target
- Password auth is vulnerable to brute-force attacks
- SSH keys provide stronger cryptographic guarantees

## Risk Mitigation
- Verified alternate user access before restarting SSH
- Changes applied incrementally to avoid lockout

## Validation
- Confirmed successful login post-change
- Confirmed root and password logins were rejected

