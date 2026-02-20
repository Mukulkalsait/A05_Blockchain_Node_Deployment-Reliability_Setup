# Runtime Observations (Execution Client)

## First Startup Behaviour

Observed:

- Peer discovery
- Chain data initialization
- Database lock creation
- Ancient data directory creation
- Blobpool directory creation

---

## Data Growth

Validated using:
```bash 

du -sh /var/lib/geth

```

## Confirms:
- Disk writes occurring
- State persistence working


## Consensus Warning

Warning observed:
 * Beacon client online, but no consensus updates received

## Reason:
No consensus (beacon) client connected which is expected when running only execution client.

---

## Conclusion

Execution client:

- Stable
- Network-connected
- Persisting state
- Managed by systemd

> Real Logs: 
```logs

systemd[1]: Started geth.service - Geth Etherium Node (sepolia).
geth[5231]: INFO [02-11|20:03:59.067] Starting Geth on Sepolia testnet...
geth[5231]: INFO [02-11|20:03:59.071] Maximum peer count                       ETH=50 total=50
geth[5231]: INFO [02-11|20:03:59.074] Smartcard socket not found, disabling    err="stat /run/pcscd/pcscd.comm: no such file or directory"
geth[5231]: WARN [02-11|20:03:59.077] Sanitizing cache to Go's GC limits       provided=1024 updated=320
geth[5231]: INFO [02-11|20:03:59.079] Set global gas cap                       cap=50,000,000
geth[5231]: INFO [02-11|20:03:59.083] Enabling metrics collection
geth[5231]: INFO [02-11|20:03:59.083] Enabling stand-alone metrics HTTP endpoint address=127.0.0.1:6060
geth[5231]: INFO [02-11|20:03:59.083] Starting metrics server                  addr=http://127.0.0.1:6060/debug/metrics
geth[5231]: INFO [02-11|20:03:59.083] Allocated trie memory caches             clean=48.00MiB dirty=80.00MiB
geth[5231]: INFO [02-11|20:03:59.083] Using pebble as the backing database
geth[5231]: INFO [02-11|20:03:59.083] Allocated cache and file handles         database=/var/lib/geth/geth/chaindata cache=160.00MiB handles=32768
geth[5231]: INFO [02-11|20:03:59.087] Initializing the KZG library             backend=gokzg
geth[5231]: INFO [02-11|20:03:59.169] Opened ancient database                  database=/var/lib/geth/geth/chaindata/ancient/chain readonly=false
geth[5231]: INFO [02-11|20:03:59.169] Opened Era store                         datadir=/var/lib/geth/geth/chaindata/ancient/chain/era
geth[5231]: INFO [02-11|20:03:59.170] State scheme set to already existing     scheme=path
geth[5231]: INFO [02-11|20:03:59.170] Initialising Ethereum protocol           network=11,155,111 dbversion=9
geth[5231]: INFO [02-11|20:03:59.171] Load database journal from file          path=/var/lib/geth/geth/triedb/merkle.journal
geth[5231]: INFO [02-11|20:03:59.176] Opened ancient database                  database=/var/lib/geth/geth/chaindata/ancient/state readonly=false
geth[5231]: INFO [02-11|20:03:59.177] Initialized path database                triecache=48.00MiB statecache=32.00MiB buffer=80.00MiB state-history="last 90000 blocks" journal-dir=/var/lib/geth/geth/triedb
geth[5231]: INFO [02-11|20:03:59.187]
geth[5231]: INFO [02-11|20:03:59.187] ---------------------------------------------------------------------------------------------------------------------------------------------------------
geth[5231]: INFO [02-11|20:03:59.188] Chain ID:  11155111 (sepolia)
geth[5231]: INFO [02-11|20:03:59.188] Consensus: Beacon (proof-of-stake), merged from Ethash (proof-of-work)
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Pre-Merge hard forks (block based):
geth[5231]: INFO [02-11|20:03:59.188]  - Homestead:                   #0
geth[5231]: INFO [02-11|20:03:59.188]  - Tangerine Whistle (EIP 150): #0
geth[5231]: INFO [02-11|20:03:59.188]  - Spurious Dragon/1 (EIP 155): #0
geth[5231]: INFO [02-11|20:03:59.188]  - Spurious Dragon/2 (EIP 158): #0
geth[5231]: INFO [02-11|20:03:59.188]  - Byzantium:                   #0
geth[5231]: INFO [02-11|20:03:59.188]  - Constantinople:              #0
geth[5231]: INFO [02-11|20:03:59.188]  - Petersburg:                  #0
geth[5231]: INFO [02-11|20:03:59.188]  - Istanbul:                    #0
geth[5231]: INFO [02-11|20:03:59.188]  - Muir Glacier:                #0
geth[5231]: INFO [02-11|20:03:59.188]  - Berlin:                      #0
geth[5231]: INFO [02-11|20:03:59.188]  - London:                      #0
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Merge configured:
geth[5231]: INFO [02-11|20:03:59.188]  - Total terminal difficulty:  17000000000000000
geth[5231]: INFO [02-11|20:03:59.188]  - Merge netsplit block:       #1735371
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Post-Merge hard forks (timestamp based):
geth[5231]: INFO [02-11|20:03:59.188]  - Shanghai:                    @1677557088
geth[5231]: INFO [02-11|20:03:59.188]  - Cancun:                      @1706655072 blob: (target: 3, max: 6, fraction: 3338477)
geth[5231]: INFO [02-11|20:03:59.188]  - Prague:                      @1741159776 blob: (target: 6, max: 9, fraction: 5007716)
geth[5231]: INFO [02-11|20:03:59.188]  - Osaka:                       @1760427360 blob: (target: 6, max: 9, fraction: 5007716)
geth[5231]: INFO [02-11|20:03:59.188]  - BPO1:                        @1761017184 blob: (target: 10, max: 15, fraction: 8346193)
geth[5231]: INFO [02-11|20:03:59.188]  - BPO2:                        @1761607008 blob: (target: 14, max: 21, fraction: 11684671)
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] All fork specifications can be found at https://ethereum.github.io/execution-specs/src/ethereum/forks/
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] ---------------------------------------------------------------------------------------------------------------------------------------------------------
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Loaded most recent local block           number=0 hash=25a5cc..3e6dd9 age=4y5mo2d
geth[5231]: INFO [02-11|20:03:59.189] Initialized transaction indexer          range="last 2350000 blocks"
geth[5231]: INFO [02-11|20:03:59.622] Enabled snap sync                        head=0 hash=25a5cc..3e6dd9
geth[5231]: INFO [02-11|20:03:59.623] Gasprice oracle is ignoring threshold set threshold=2
geth[5231]: INFO [02-11|20:03:59.623] Registered sync override service
geth[5231]: INFO [02-11|20:03:59.623] Starting peer-to-peer node               instance=Geth/v1.16.8-stable-abeb78c6/linux-amd64/go1.25.1
geth[5231]: INFO [02-11|20:03:59.804] New local node record                    seq=1,770,652,562,959 id=07c98792b56a8f32 ip=127.0.0.1 udp=30303 tcp=30303
geth[4770]: INFO [02-11|20:03:56.699] HTTP server stopped                      endpoint=127.0.0.1:8545
geth[4770]: INFO [02-11|20:03:56.699] HTTP server stopped                      endpoint=127.0.0.1:8551
geth[4770]: INFO [02-11|20:03:56.699] IPC endpoint closed                      url=/var/lib/geth/geth.ipc
geth[4770]: INFO [02-11|20:03:58.942] Ethereum protocol stopped
geth[4770]: INFO [02-11|20:03:58.943] Transaction pool stopped
geth[4770]: INFO [02-11|20:03:58.947] Persisting dirty state                   root=5eb6e3..a3f494 layers=0
geth[4770]: INFO [02-11|20:03:58.958] Persisted dirty state to file            path=/var/lib/geth/geth/triedb/merkle.journal size=74.00B elapsed=11.370ms
geth[4770]: INFO [02-11|20:03:58.965] Blockchain stopped
systemd[1]: geth.service: Deactivated successfully.
systemd[1]: Stopped geth.service - Geth Etherium Node (sepolia).
systemd[1]: geth.service: Consumed 25.320s CPU time, 68.5M memory peak, 0B memory swap peak.
systemd[1]: Started geth.service - Geth Etherium Node (sepolia).
geth[5231]: INFO [02-11|20:03:59.067] Starting Geth on Sepolia testnet...
geth[5231]: INFO [02-11|20:03:59.071] Maximum peer count                       ETH=50 total=50
geth[5231]: INFO [02-11|20:03:59.074] Smartcard socket not found, disabling    err="stat /run/pcscd/pcscd.comm: no such file or directory"
geth[5231]: WARN [02-11|20:03:59.077] Sanitizing cache to Go's GC limits       provided=1024 updated=320
geth[5231]: INFO [02-11|20:03:59.079] Set global gas cap                       cap=50,000,000
geth[5231]: INFO [02-11|20:03:59.083] Enabling metrics collection
geth[5231]: INFO [02-11|20:03:59.083] Enabling stand-alone metrics HTTP endpoint address=127.0.0.1:6060
geth[5231]: INFO [02-11|20:03:59.083] Starting metrics server                  addr=http://127.0.0.1:6060/debug/metrics
geth[5231]: INFO [02-11|20:03:59.083] Allocated trie memory caches             clean=48.00MiB dirty=80.00MiB
geth[5231]: INFO [02-11|20:03:59.083] Using pebble as the backing database
geth[5231]: INFO [02-11|20:03:59.083] Allocated cache and file handles         database=/var/lib/geth/geth/chaindata cache=160.00MiB handles=32768
geth[5231]: INFO [02-11|20:03:59.087] Initializing the KZG library             backend=gokzg
geth[5231]: INFO [02-11|20:03:59.169] Opened ancient database                  database=/var/lib/geth/geth/chaindata/ancient/chain readonly=false
geth[5231]: INFO [02-11|20:03:59.169] Opened Era store                         datadir=/var/lib/geth/geth/chaindata/ancient/chain/era
geth[5231]: INFO [02-11|20:03:59.170] State scheme set to already existing     scheme=path
geth[5231]: INFO [02-11|20:03:59.170] Initialising Ethereum protocol           network=11,155,111 dbversion=9
geth[5231]: INFO [02-11|20:03:59.171] Load database journal from file          path=/var/lib/geth/geth/triedb/merkle.journal
geth[5231]: INFO [02-11|20:03:59.176] Opened ancient database                  database=/var/lib/geth/geth/chaindata/ancient/state readonly=false
geth[5231]: INFO [02-11|20:03:59.177] Initialized path database                triecache=48.00MiB statecache=32.00MiB buffer=80.00MiB state-history="last 90000 blocks" journal-dir=/var/lib/geth/geth/triedb
geth[5231]: INFO [02-11|20:03:59.187]
geth[5231]: INFO [02-11|20:03:59.187] ---------------------------------------------------------------------------------------------------------------------------------------------------------
geth[5231]: INFO [02-11|20:03:59.188] Chain ID:  11155111 (sepolia)
geth[5231]: INFO [02-11|20:03:59.188] Consensus: Beacon (proof-of-stake), merged from Ethash (proof-of-work)
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Pre-Merge hard forks (block based):
geth[5231]: INFO [02-11|20:03:59.188]  - Homestead:                   #0
geth[5231]: INFO [02-11|20:03:59.188]  - Tangerine Whistle (EIP 150): #0
geth[5231]: INFO [02-11|20:03:59.188]  - Spurious Dragon/1 (EIP 155): #0
geth[5231]: INFO [02-11|20:03:59.188]  - Spurious Dragon/2 (EIP 158): #0
geth[5231]: INFO [02-11|20:03:59.188]  - Byzantium:                   #0
geth[5231]: INFO [02-11|20:03:59.188]  - Constantinople:              #0
geth[5231]: INFO [02-11|20:03:59.188]  - Petersburg:                  #0
geth[5231]: INFO [02-11|20:03:59.188]  - Istanbul:                    #0
geth[5231]: INFO [02-11|20:03:59.188]  - Muir Glacier:                #0
geth[5231]: INFO [02-11|20:03:59.188]  - Berlin:                      #0
geth[5231]: INFO [02-11|20:03:59.188]  - London:                      #0
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Merge configured:
geth[5231]: INFO [02-11|20:03:59.188]  - Total terminal difficulty:  17000000000000000
geth[5231]: INFO [02-11|20:03:59.188]  - Merge netsplit block:       #1735371
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Post-Merge hard forks (timestamp based):
geth[5231]: INFO [02-11|20:03:59.188]  - Shanghai:                    @1677557088
geth[5231]: INFO [02-11|20:03:59.188]  - Cancun:                      @1706655072 blob: (target: 3, max: 6, fraction: 3338477)
geth[5231]: INFO [02-11|20:03:59.188]  - Prague:                      @1741159776 blob: (target: 6, max: 9, fraction: 5007716)
geth[5231]: INFO [02-11|20:03:59.188]  - Osaka:                       @1760427360 blob: (target: 6, max: 9, fraction: 5007716)
geth[5231]: INFO [02-11|20:03:59.188]  - BPO1:                        @1761017184 blob: (target: 10, max: 15, fraction: 8346193)
geth[5231]: INFO [02-11|20:03:59.188]  - BPO2:                        @1761607008 blob: (target: 14, max: 21, fraction: 11684671)
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] All fork specifications can be found at https://ethereum.github.io/execution-specs/src/ethereum/forks/
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] ---------------------------------------------------------------------------------------------------------------------------------------------------------
geth[5231]: INFO [02-11|20:03:59.188]
geth[5231]: INFO [02-11|20:03:59.188] Loaded most recent local block           number=0 hash=25a5cc..3e6dd9 age=4y5mo2d
geth[5231]: INFO [02-11|20:03:59.189] Initialized transaction indexer          range="last 2350000 blocks"
geth[5231]: INFO [02-11|20:03:59.622] Enabled snap sync                        head=0 hash=25a5cc..3e6dd9
geth[5231]: INFO [02-11|20:03:59.623] Gasprice oracle is ignoring threshold set threshold=2
geth[5231]: INFO [02-11|20:03:59.623] Registered sync override service
geth[5231]: INFO [02-11|20:03:59.623] Starting peer-to-peer node               instance=Geth/v1.16.8-stable-abeb78c6/linux-amd64/go1.25.1
geth[5231]: INFO [02-11|20:03:59.804] New local node record                    seq=1,770,652,562,959 id=07c98792b56a8f32 ip=127.0.0.1 udp=30303 tcp=30303
geth[5231]: INFO [02-11|20:03:59.984] IPC endpoint opened                      url=/var/lib/geth/geth.ipc
geth[5231]: INFO [02-11|20:03:59.985] Loaded JWT secret file                   path=/var/lib/geth/geth/jwtsecret             crc32=0x8d08bc24
geth[5231]: INFO [02-11|20:03:59.986] HTTP server started                      endpoint=127.0.0.1:8545 auth=false prefix= cors= vhosts=localhost
geth[5231]: INFO [02-11|20:03:59.986] WebSocket enabled                        url=ws://127.0.0.1:8551
geth[5231]: INFO [02-11|20:03:59.986] HTTP server started                      endpoint=127.0.0.1:8551 auth=true  prefix= cors=localhost vhosts=localhost
geth[5231]: INFO [02-11|20:04:00.002] Started P2P networking                   self=enode://5d3f75903242da62c6e4afe4ef71ad65cd74ef11f2b1d89349011b4c2502537773e791168bf8453b38765d9b8410551e32869af41a78a6b986661b1b13852da5@127.0.0.1:30303
geth[5231]: INFO [02-11|20:04:00.003] Loaded local transaction journal         transactions=0 dropped=0
geth[5231]: INFO [02-11|20:04:00.022] Started log indexer
geth[5231]: INFO [02-11|20:04:05.470] New local node record                    seq=1,770,652,562,960 id=07c98792b56a8f32 ip=64.227.160.199 udp=30303 tcp=30303
geth[5231]: WARN [02-11|20:04:34.648] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:09:34.683] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:14:34.716] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:19:34.749] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:24:34.781] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:29:34.815] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:34:34.849] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:39:34.886] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:44:34.918] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:49:34.953] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:54:34.989] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|20:59:35.052] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|21:04:35.086] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|21:09:35.119] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|21:14:35.157] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
geth[5231]: WARN [02-11|21:19:35.193] Beacon client online, but no consensus updates received in a while. Please fix your beacon client to follow the chain!
```
