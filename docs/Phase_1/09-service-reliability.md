# Service Reliability Observations

## Restart Behaviour

Tested:
- Manual stop/start
- Reboot
- Invalid ExecStart path (failure simulation)

Observed:
- systemd restart counter increments
- Service recovery after fix
- Logs captured in journal

---

## Boot Validation

After reboot:

- `systemctl status geth` → active (running)
- `ps -C geth` → process exists
- Ports listening confirmed
- Data directory intact

This validates:
- Service enablement
- Dependency ordering
- Network availability at startup

> **Service Running From 6 Days**

```bash 
mukul in  Ubuntu-24 in ~ took 2s
❯ sudo systemctl status geth
● geth.service - Geth Etherium Node (sepolia)
     Loaded: loaded (/etc/systemd/system/geth.service; enabled; preset: enabled)
     Active: active (running) since Fri 2026-02-13 20:50:54 IST; 6 days ago
   Main PID: 26983 (geth)
      Tasks: 8 (limit: 1107)
     Memory: 69.6M (peak: 98.5M)
        CPU: 2h 33min 49.330s
     CGroup: /system.slice/geth.service
             └─26983 /usr/bin/geth --sepolia --datadir /var/lib/geth --syncmode snap --http --http.api eth,net,web3 --http.addr 127.0.0.1 --http.port 8545 --authrpc.addr 127.0.0.1 --authrpc.port 8551 --metrics --metrics.addr 127.0.0.1 --metrics.port 6060

```
