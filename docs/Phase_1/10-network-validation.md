# Network & Port Validation

## Ports Used

| Port | Purpose |
|------|----------|
| 30303 * 2 | Ethereum P2P |
| 8545  | HTTP JSON-RPC (local only) |
| 8551  | Engine API (Execution ↔ Consensus) |

---

## Observations

Using:

```bash
sudo ss -tulpn | grep geth


ps -C geth -U/ -O user,pid,comm,mem

lsof -p pid


```

### Confirmed:

  - P2P port exposed publicly
  - RPC bound to 127.0.0.1 (secure)
  - Peer connections established
  - Node record published

---

 ## Security Decision

RPC endpoints are restricted to localhost by seting localhost ip.
Reason: Avoid exposing JSON-RPC publicly without authentication.


> Orignal OP

```bash 
❯ sudo ss -tulpn
[sudo] password for mukul:
Netid                 State                  Recv-Q                 Send-Q                                   Local Address:Port                                    Peer Address:Port                 Process
udp                   UNCONN                 0                      0                                        127.0.0.53%lo:53                                           0.0.0.0:*                     users:(("systemd-resolve",pid=463,fd=14))
udp                   UNCONN                 0                      0                                                    *:30303                                              *:*                     users:(("geth",pid=26983,fd=111))
tcp                   LISTEN                 0                      4096                                         127.0.0.1:8545                                         0.0.0.0:*                     users:(("geth",pid=26983,fd=123))
tcp                   LISTEN                 0                      4096                                         127.0.0.1:8551                                         0.0.0.0:*                     users:(("geth",pid=26983,fd=124))
tcp                   LISTEN                 0                      4096                                           0.0.0.0:22                                           0.0.0.0:*                     users:(("sshd",pid=982,fd=3),("systemd",pid=1,fd=135))
tcp                   LISTEN                 0                      4096                                                 *:30303                                              *:*                     users:(("geth",pid=26983,fd=110))
tcp                   LISTEN                 0                      4096                                              [::]:22                                              [::]:*                     users:(("sshd",pid=982,fd=4),("systemd",pid=1,fd=136))


# SOME REMOVED FOR SECURITY PURPOSE 
# But the server and everything will be deleted when you see it.
```
