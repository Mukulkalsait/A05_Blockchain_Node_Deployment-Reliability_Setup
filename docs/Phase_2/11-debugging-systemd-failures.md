
# Debugging systemd Failures

## Issue Encountered

Service repeatedly failed with:
 * wrong location added => 203 error systemd used /usr/local/bin/geth
 * wrong name in geth.service of Install.WantedBy=multi-user.target (did multy-user)
 * wrong mapping of StartLimit{IntervalSec,Burst}=> must used in U-Unit put it in S-Service. note I-Install
 * Misspelled StartLimitBrust ❌ instead of "BU-RST" ✅
 
### after every change 
 > systemctl daemon-reload 
 > restart geth 
 > init 6 (restart) 
 > systemctl status geth 
 > journalctl -u geth -b -> if logs are present ✅
 > journalctl -u geth -f -> follow mode.



