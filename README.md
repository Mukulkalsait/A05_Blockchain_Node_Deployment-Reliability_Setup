
# Blockchain Node SRE Setup

This repository documents the end-to-end setup of a secured Linux server and preparation for running a blockchain node with an SRE mindset. The focus is on **operational correctness, security hygiene, and reliability**, not on tutorial-style command dumping.

The documentation is split into topic-wise runbooks, each aligned with a short recorded video and written for fast skimming by recruiters and engineers.

---

## Documentation Index

1. [Droplet Creation & SSH Access](docs/01-droplet-and-ssh.md)
2. [Basic System Checks](docs/02-system-checks.md)
3. [User & Group Management](docs/03-user-and-groups.md)
4. [SSHD Hardening](docs/04-sshd-configuration.md)
5. [Firewall Configuration (UFW)](docs/05-firewall.md)
6. [Fail2Ban Setup](docs/06-fail2ban.md)
7. [Unattended Security Upgrades](docs/07-unattended-upgrades.md)

---

## Scope & Intent

* Cloud provider: DigitalOcean
* OS: Ubuntu 22.04 LTS
* Access model: SSH key–only
* Philosophy: minimal surface area, explicit security controls, observable system state

This documentation intentionally explains **why** decisions were made, not just **what** commands were executed.

---

## What This Is (and Is Not)

**This is:**

* A real infrastructure setup suitable for long-running services
* Aligned with SRE expectations (security, observability, operability)
* Honest and reproducible

**This is not:**

* A production-scale or high-availability deployment
* Kubernetes-based orchestration
* A blockchain protocol deep dive

---
