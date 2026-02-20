
Perfect — this is the **exact checkpoint** where a lot of people rush… and you didn’t. Good SRE instincts 👌
Now we flip the switch from *“it runs”* → *“it stays running”*.

---

# 🚀 PHASE 3 — systemd + Reliability (CORE SRE SIGNAL)

This is the most important phase for this JD.

InfStones doesn’t care if you can start a node.
They care if:

* it **comes back after crashes**
* it **behaves predictably**
* it’s **operable at 3 AM**

That’s systemd.

---

## 3.1 Why systemd (interview framing)

Before commands, internalize this:

> systemd is the **first reliability layer** in infra
> before containers, before orchestration

What we get:

* automatic restarts
* controlled startup order
* centralized logs (journald)
* resource limits
* predictable behavior

This alone upgrades your project from *“blockchain node”* → *“SRE-grade service”*.

---

## 3.2 Create systemd service file

Create the unit file:

```bash
sudo nvim /etc/systemd/system/geth.service
```

Paste this (read it, don’t blindly paste):

```ini
[Unit]
Description=Ethereum Geth Node (Sepolia)
After=network.target
Wants=network-online.target

[Service]
User=geth
Group=geth
Type=simple

ExecStart=/usr/bin/geth \
  --sepolia \
  --datadir /var/lib/geth \
  --syncmode snap \
  --http \
  --http.addr 127.0.0.1 \
  --http.port 8545 \
  --http.api eth,net,web3

Restart=always
RestartSec=10

# Increase file descriptor limit for P2P networking
LimitNOFILE=65536

# Hardening (basic, safe)
NoNewPrivileges=true
PrivateTmp=true

[Install]
WantedBy=multi-user.target
```

### Why these options matter (remember this):

* `Restart=always` → crash recovery
* `RestartSec=10` → avoids tight crash loops
* `LimitNOFILE` → P2P connections need it
* `NoNewPrivileges` → basic security hardening
* `PrivateTmp` → isolates temp files

This is **not overkill**, this is baseline.

---

## 3.3 Load and start the service

```bash
sudo systemctl daemon-reexec
sudo systemctl daemon-reload
sudo systemctl enable geth
sudo systemctl start geth
```

Check status:

```bash
systemctl status geth
```

Follow logs:

```bash
journalctl -u geth -f
```

You should again see:

* peer discovery
* sync activity
* no permission errors

---

## 3.4 🔥 Mandatory Failure Tests (DO NOT SKIP)

These are **interview gold**.

### Test 1 — Kill the process

In another terminal:

```bash
sudo pkill geth
```

Then immediately:

```bash
systemctl status geth
```

Expected:

* service goes `inactive` briefly
* comes back to `active (running)`

Check logs:

```bash
journalctl -u geth --since "2 minutes ago"
```

You should see:

* exit
* restart
* clean startup

---

### Test 2 — Reboot survival

```bash
sudo reboot
```

After reconnecting:

```bash
systemctl status geth
```

Expected:

* service already running
* no manual intervention

If this works → **you’ve proven reliability**.

---

## 3.5 What to document for Phase 3

Later create:
`docs/09-systemd-and-reliability.md`

Include **only this level of detail**:

### Sections to include:

* Why systemd over manual runs
* Restart behavior and backoff
* Log handling via journald
* Failure scenarios tested
* Observed behavior during restart

Example phrasing (you can reuse):

> The Geth node is managed via systemd to ensure automatic recovery from crashes and predictable lifecycle management. Restart behavior was validated by forcefully terminating the process and confirming successful auto-restart without manual intervention.

That sentence alone is strong.

---

## ✅ Current State Check

At this point, you can **truthfully say**:

* I deployed an Ethereum node
* It runs as a managed service
* It survives crashes and reboots
* Logs are centrally observable
* Data ownership and permissions are controlled

That already matches **half the JD**.

---

## Next Phase (tell me when ready)

### PHASE 4 — Monitoring & Observability

* node_exporter
* Prometheus
* service-level visibility
* “node down” detection

Reply with:

* ✅ systemd restart test worked
  and we move straight into monitoring.

You’re doing this **exactly right**.
