  647  su user2
  648  ll /home/
  649  sudo userdel -m user2
  650  sudo userdel -r user2 
  651  su  user2
  652  ll /home/
  653  clear
  654  groupadd -g 1005 textbook
  655  sudo groupadd -g 1005 textbook
  656  sudo cat /etc/group
  657  groupmod -n Textbook textbook
  658  sudo groupmod -n TextBook textbook 
  659  sudo cat /etc/group
  660  sudo gropumod -g 1010
  661  sudo groupmod 0g 1020
  662  sudo groupmod -g 1020
  663  sudo groupmod -g 1020 TextBook 
  664  id
  665  cat /etc/group
  666  sudo cat /etc/shadow
  667  localectl
  668  exit
  669  cat /etc/passwd
  670  cat /etc/group
  671  sudo cat /etc/sudoers
  672  cat /etc/login.defs 
  673  visudo
  674  sudo visudo
  675  clear
  676  sudo vim visudo
  677  clear
  678  visudo --help
  679  sudo authconfig --passalgo md5
  680  clear
  681  chage
  682  sudo cat /etc/shadow
  683  chage -l user1
  684  sudo chage -l user1
  685  sudo chage -m 15 user1
  686  sudo chage -l user1
  687  su user1
  688  sudo chage -M 30 user1
  689  sudo chage -m 0 user1
  690  sudo chage -l user1
  691  date
  692  sudo chage -M 1 user1
  693  sudo chage -l user1
  694  su user1
  695  sudo chage -M 0 user1
  696  sudo chage -l user1
  697  su user1
  698  passwd
  699  passwd user1
  700  passwd
  701  exit
  702  sudo chage -l user1
  703  sudo chage -m 15 -M 30 user1
  704  sudo chage -l user1
  705  chage -h
  706  sudo chage -w 3 user1
  707  sudo chage -W 3 user1
  708  sudo chage -l user1
  709  sudo chage -I 7 user1
  710  sudo chage -l user1
  711  sudo chage -i 7 user1
  712  sudo chage -d 0 user1
  713  su user1
  714  sudo chage -l user1
  715  exit
  716  ll
  717  clear
  718  ls
  719  ll
  720  ps 
  721  ps -e
  722  ps -r -C bash
  723  ps -r -c bash
  724  ps -rc bash
  725  ps -r
  726  ps -e 
  727  ps -ec bash
  728  ps -e -c bash
  729  ps -c bash
  730  ps --help a
  731  ps -eC bash
  732  ps -eCt bash
  733  ps -eC bash -t
  734  ps -eC bash -T
  735  ps -P
  736  ps -S
  737  ps -V
  738  ps -U
  739  ps -U mukul
  740  ps -U user1
  741  ps -ly
  742  ps -elyf
  743  clear
  744  ps -Z
  745  ps -z
  746  clea
  747  sudo cat /etc/hosts
  748  sudo cat /etc/passwq 
  749  clear
  750  exit
  751  htop
  752  sudo chage -l mukul
  753  reboot
  754  sudo reboot
  755  exit
  756  clear
  757  groupadd -g 40000 testgroup
  758  sudo groupadd -g 40000 test-group-40k
  759  cat /etc/group
  760  getent group test-group-40k 
  761  ls
  762  mkdir --help
  763  mkdir 
  764  mkdir -m +x scripts/
  765  ls
  766  cd scripts/
  767  ls
  768  ll
  769  touch test.sh
  770  ls
  771  ll
  772  cd ..
  773  ls
  774  ll
  775  suod chmod 
  776  lsl
  777  clear
  778  ll
  779  cd scripts/
  780  ls
  781  vim users_create.sh
  782  ls
  783  ll
  784  cat users_create.sh 
  785  vim users_create.sh 
  786  exit
  787  ls
  788  sudo chmod -x scripts/
  789  lsl
  790  ll
  791  cd 
  792  cd scripts
  793  ls
  794  rm -rrf
  795  asdf
  796  rm -rf scripts/
  797  sudo rm -rf  scripts/
  798  lsl
  799  mkdir scripts
  800  ls
  801  cd scripts/
  802  ls
  803  htop
  804  ls
  805  cd scripts/
  806  ls
  807  ll
  808  rm -rf user_create.sh 
  809  sudo chmod +x user_create2.sh 
  810  ls
  811  ./user_create2.sh 
  812  getent passwd 
  813  ./user_create2.sh 
  814  lsl
  815  cd scripts/
  816  ls
  817  ll
  818  ./user_create2.sh 
  819  getent group
  820  getent group test001
  821  getent group
  822  sudo usermod -aG test-group-40k test001-1
  823  sudo usermod -aG test-group-40k test001-2
  824  sudo usermod -aG test-group-40k test001-3
  825  sudo usermod -aG test-group-40k test001-0
  826  getent group test-group-40k 
  827  getent group test-group-40k  | awk -F: 
  828  getent group test-group-40k  | awk -F: "{print $4}"
  829  getent group test-group-40k | awk -F: '
  830  getent group test-group-40k | awk -F: '{print $4}'
  831  getent group test-group-40k | awk -F: '{print $4}' | tr ',' ' ' 
  832  for a in $(getent group test-group-40k | awk -F: '{print $4}' | tr ',' ' '); do  echo $a; ; done
  833  for a in $(getent group test-group-40k | awk -F: '{print $4}' | tr ',' ' '); do  echo $a;; done
  834  for a in $(getent group test-group-40k | awk -F: '{print $4}' | tr ',' ' '); do  echo $a;done
  835  for a in $(getent group test-group-40k | awk -F: '{print $4}' | tr ',' ' '); do
  836  sudo chage -l test001-0 
  837  echo "------------------------"
  838  for a in $(getent group test-group-40k | awk -F: '{print $4}' | tr ',' ' '); do sudo chage $a -l ; echo "-------------"; done
  839  for a in $(getent group test-group-40k | awk -F : '{print $4 }' | tr ',' ' '); do  sudo chage -m 7 -W 3 -M 30 -I 7 $a; sudo chage $a -l ; echo "===================="; done 
  840  ls
  841  cat ./scripts/user_create2.sh 
  842  cd scripts/
  843  ls
  844  ./user_create2.sh 
  845  ./user_create
  846  ls
  847  rm -rf user_create.sh 
  848  cat user_create2.sh 
  849  ./user_create2.sh 
  850  cat user_create2.sh 
  851  ./user_create2.sh 
  852  getent group 
  853  lsl
  854  clear
  855  ls
  856  clear
  857  lsl
  858  ls
  859  ./user_create2.sh 
  860  ls
  861  whoami
  862  htop
  863  clear
  864  apt list software-properties-common 
  865  clear
  866  exit
  867  cat /etc/os-release 
  868  suod apt-add-repository 
  869  useradd --help
  870  sudoi
  871  clear
  872  sudo --help
  873  geth
  874  man geth
  875  clear
  876  exit
  877  sudo -u geth ls /var/lib/geth 
  878  exit
  879  cat /etc/os-release 
  880  sudo apt update -y
  881  sudo apt install software-properties-common 
  882  sudo add-apt-repository ppa:ethereum/ethereum
  883  sudo do
  884  sudo apt update -y
  885  sudo apt upgrade
  886  sudo apt  install geth
  887  geth 
  888  clear
  889  ll
  890  geth --help
  891  geth -v
  892  geth --help
  893  geth  --help | grep --sepolia
  894  geth  --help | grep --se
  895  geth --help | grep sepo
  896  geth --help | grep data
  897  geth --help | grep sync
  898  geth --help | grep http
  899  clear
  900  geth -v
  901  sudo  useradd --system -d /var/lib/geth/ -G geth 
  902  sudo  useradd --system -d /var/lib/geth/ -g geth
  903  sudo  useradd --system -d /var/lib/geth/ geth
  904  getent group 
  905  userdel -r geth
  906  sudo userdel -r geth
  907  sudo groupdel geth
  908  getent 
  909  getent passwd 
  910  getent group 
  911  ls /var/lib/
  912  ls /var/lib/geth
  913  ]clear
  914  clear
  915  geth -v
  916  sudo useradd --system -d /var/lib/geth geth 
  917  getent passwd 
  918  getent passwd geth 
  919  getent group geth
  920  ls -altir /var/lib/geth
  921  sudo userdel -r geth
  922  sudo groupdel geth
  923  clear
  924  useradd --help
  925  sudo useradd --system --home /var/lib/geth geth 
  926  ls /var/lib/geth
  927  ll /var/lib/
  928  clear
  929  geth -v
  930  mkdir -p /var/lib/geth 
  931  sudo mkdir -p /var/lib/geth 
  932  ls /var/lib/geth
  933  ls /var/lib/
  934  sudo useradd --system -d /var/lib/geth geth 
  935  userdel -r geth
  936  suod userdel -r geth
  937  sudo userdel -r geth
  938  cleawr
  939  clear
  940  ls -altir /var/lib/
  941  getent passwd
  942  getent group 
  943  clear
  944  suod useradd --system -d /var/lib/geth geth 
  945  sudo useradd --system -d /var/lib/geth geth
  946  getent passwd geth
  947  getent group geth 
  948  ls -alt /var/lib/geth
  949  ls -alt /var/lib/
  950  ls -airlt /var/lib/
  951  sudo usermod geth:geth /var/lib/geth
  952  sudo clear
  953  ls
  954  sudo userdel -r geth
  955  ls -altir /var/lib/geth/
  956  ls -altir /var/lib/
  957  clear
  958  getent passwd 
  959  getent group 
  960  clear
  961  sudo useradd --system -d /var/lib/geth geth 
  962  getent passwd geth
  963  getent group geth
  964  ls -altir /var/lib
  965  sudo chown geth:geth /var/lib/geth/
  966  ls -altir /var/lib
  967  sudo chmod 750 /var/lib/geth/
  968  ls -altir /var/lib
  969  geth --help 
  970  geth --help | sepo
  971  geth --help | grep sepo
  972  geth --help | grep data
  973  geth --help | grep sync
  974  geth --help | grep http
  975  sudo -u geth geth --sepolia --datadir /var/lib/geth --syncmode snap --http --http.api web3,eth,net --http.port 8545 
  976  clear
  977  ls
  978  ps i
  979  ps e
  980  ps -e
  981  ps e
  982  ps -e | grep geth
  983  ps -e | awk -F '/geth/ {print} '
  984  ps -e | awk -F  '/geth/ {print} '
  985  ps -e | awk -F ' '  '/geth/ {print} '
  986  ps -e | awk -F ' '  ' {print $3} '
  987  ps -e | awk -F ' '  ' {print $4} '
  988  exit
  989  ls
  990  htop
  991  whoami
  992  clear
  993  ps -eC bash
  994  ps -C bash
  995  ps -e  -C bash
  996  ps -C bash
  997  ps -p 49891
  998  ps -p 49891 -O comm,pid,
  999  sudo pkill geth
 1000  nvim
 1001  sudo apt install neovim
 1002  nvim
 1003  sudo nvim  /etc/systemd/system/geth.service
 1004  ls
 1005  whoami
 1006  sudo su
 1007  cd .config
 1008  ls
 1009  ll
 1010  nvim
 1011  ls
 1012  cd nvim
 1013  sudo chown mukul:mukul nvim 
 1014  ls
 1015  ll
 1016  sudo chown mukul:mukul ./nvim 
 1017  ls
 1018  ll
 1019  sudo chown -r mukul:mukul /home/mukul/.config/nvim 
 1020  sudo chown -R mukul:mukul /home/mukul/.config/nvim 
 1021  ls
 1022  ll
 1023  nvim
 1024  cd nvim
 1025  ll
 1026  sudo rm -rf nvim 
 1027  ls
 1028  sudo su
 1029  ls
 1030  git clone https://github.com/LazyVim/starter ~/.config/nvim
 1031  ls
 1032  nvim
 1033  ls
 1034  cd nvim/
 1035  ls
 1036  nvim
 1037  sudo nvim /etc/systemd/system/geth.service 
 1038  nvim
 1039  sudo nvim
 1040  clear
 1041  exit
 1042  sudo init 6
 1043  lsl
 1044  fail2ban-client status
 1045  sudo fail2ban-client status
 1046  sudo fail2ban-client status sshd
 1047  sudo fail2ban-client sshd unban 92.118.39.92
 1048  sudo fail2ban-client unban sshd 92.118.39.92
 1049  sudo fail2ban-client staus sshd 
 1050  sudo fail2ban-client status ssh d
 1051  sudo fail2ban-client status sshd 
 1052  clear
 1053  sudo nvim /etc/systemd/system/geth.service 
 1054  sudo systemctl daemon-reload 
 1055  sudo systemctl start geth
 1056  sudo systemctl status geth
 1057  journalctl -u geth -f
 1058  sudo journalctl -u geth -f
 1059  which geth
 1060  command -v geth
 1061  whereis geth
 1062  ls -l /usr/bin/geth
 1063  sudo nvim /etc/systemd/system/geth.service 
 1064  sudo systemctl daemon-reload 
 1065  sudo systemctl status geth
 1066  journalctl -u geth -f 
 1067  sudo journalctl -u geth -f
 1068  ps -e | aux 
 1069  ps -e | aux '/geth/ {print}
 1070  '
 1071  ps -e | aux '/geth/ {print}'
 1072  ps -e | awk '/geth/ {print}'
 1073  ps -ef
 1074  ps -el | awk '/geth/ {print }'
 1075  ps -eL | grep geth 
 1076  ps -el | grep geth 
 1077  ps -el -C geth -O usr,comm,pid
 1078  ps -C geth -O usr,comm,pid
 1079  ps -C geth
 1080  ps -C geth -O user
 1081  ps -C geth -O user,comm,pid
 1082  sudo du -sh  /var/lib/geth
 1083  sudo init 6
 1084  sudo systemctl status geth 
 1085  sudo systemctl enable geth
 1086  sudo systemctl status geth 
 1087  exit
 1088  sudo init 6
 1089  init --help
 1090  clear
 1091  sudo systemctl status geth
 1092  ps -C geth
 1093  journalctl -u geth
 1094  sudo journalctl -u geth
 1095  sudo journalctl -u geth -f
 1096  sudo journalctl -u geth
 1097  sudo init 6
 1098  sudo systemctl status geth
 1099  sudo systemctl is-enabled geth
 1100  sudo systemctl start geth.service 
 1101  sudo journalctl -u geth -f
 1102  sudo journalctl -u geth -b
 1103  sudo journalctl -u geth -b -1
 1104  sudo journalctl -u geth -b -2
 1105  sudo journalctl -u geth -b -3
 1106  sudo nvim /etc/systemd/system/geth.service 
 1107  sudo cat /etc/systemd/system/geth.service 
 1108  sudo nvim /etc/systemd/system/geth.service 
 1109  sudo systemctl daemon-reload 
 1110  sudo systemctl status get
 1111  sudo systemctl status geth.service 
 1112  sudo init 6
 1113  ps -C geth 
 1114  sudo systemctl status geth.service 
 1115  sudo systemctl disable geth.service 
 1116  sudo systemctl enable geth.service 
 1117  sudo init 6
 1118  sudo journalctl -u geth -f
 1119  sudo journalctl --unit geth 
 1120  clear
 1121  exit
 1122  ps -C geth
 1123  sudo systemctl status geth.service 
 1124  journalctl -u geth -f
 1125  sudo journalctl -u geth -f
 1126  sudo journalctl -u geth -b
 1127  clear
 1128  sudo nvim /etc/systemd/system/geth.service 
 1129  sudo systemctl daemon-reload 
 1130  sudo systemctl restart geth.service 
 1131  sudo journalctl -u geth -f
 1132  sudo pkill -9 geth
 1133  sudo journalctl -u geth -f
 1134  sudo journalctl -u geth -b
 1135  htop
 1136  ps -C geth 
 1137  lsof -p 1485 
 1138  sudo lsof -p 1485
 1139  ss -tulpn | grep geth
 1140  ss -tulpn 
 1141  ss -tulp
 1142  sudo nvim /etc/systemd/system/geth.service 
 1143  clear
 1144  sudo systemctl daemon-reload 
 1145  sudo systemctl restart geth.service 
 1146  sudo journalctl -u geth -b 
 1147  ps -C geth
 1148  sudo pkill -9 geth
 1149  ps -C geth
 1150  sudo journalctl -u geth -b 
 1151  time
 1152  datetime
 1153  timedatectl
 1154  sudo systemctl status geth.service 
 1155  sudo journalctl -u geth -b 
 1156  sudo ss -tulpn | grep geth
 1157  ss -tulpn | grep geth
 1158  ss -tulpn
 1159  sudo ss -tulpn 
 1160  ls 
 1161  ll /var/lib/
 1162  ll /var/lib/geth
 1163  ll /var/lib | grep geth
 1164  sudo -u geth ll /var/lib/geth
 1165  sudo -u geth ls /var/lib/geth
 1166  sudo -u geth ls -altir  /var/lib/geth
 1167  sudo su 
 1168  ps -C geth -O cmd
 1169  sudo ss -tulpn | grep geth
 1170  cat  /etc/systemd/system/geth.service 
 1171  clear
 1172  sudo nvim /etc/systemd/system/geth.service 
 1173  geth --help | grep -A 4  metrics.port 
 1174  clear
 1175  sudo systemctl daemon-reload 
 1176  sudo systemctl restart geth
 1177  sudo systemctl restart geth.service 
 1178  curl http://127.0.0.1:6060/debug/metrics/promethus 
 1179  curl http://127.0.0.1:6060
 1180  sudo systemctl status geth
 1181  curl http://127.0.0.1:6060
 1182  curl http://127.0.0.1:6060/debug/metrics/promethus 
 1183  curl http://127.0.0.1:6060/debug/metrics/promethus
 1184  sudo ss -tulpn | grep geth
 1185  sudo journalctl -u geth 
 1186  sudo journalctl -u geth | grep metrics
 1187  sudo journalctl -u geth | grep authrpc
 1188  sudo journalctl -u geth | grep http
 1189  sudo systemctl daemon-reload 
 1190  sudo systemctl stop geth
 1191  sudo systemctl start geth
 1192  sudo systemctl stop geth
 1193  sudo systemctl disable geth
 1194  sudo systemctl enable geth
 1195  sudo systemctl start geth
 1196  journalctl -u geth -b
 1197  sudo journalctl -u geth -b 
 1198  sudo nvim /etc/systemd/system/geth.service 
 1199  geth --help | grep metrics
 1200  sudo nvim /etc/systemd/system/geth.service 
 1201  sudo systemctl daemon-reload 
 1202  sudo nvim /etc/systemd/system/geth.service 
 1203  sudo systemctl daemon-rel
 1204  sudo systemctl daemon-reload 
 1205  sudo systemctl reload geth
 1206  sudo systemctl status geth.service
 1207  sudo systemctl reload geth.service
 1208  sudo systemctl restart geth.service 
 1209  sudo journalctl -u geth -b
 1210  datetimectl
 1211  timedatectl
 1212  sudo journalctl -u geth -b | grep authrpc
 1213  sudo journalctl -u geth -b | grep metrics
 1214  curl http://localhost:6060
 1215  sudo ss -tulpn 
 1216  curl http://127.0.0.1:6060/debug/metrics/promethus
 1217  curl http://127.0.0.1:6060/debug/metrics/prometheus
 1218  curl http://127.0.0.1:6060/debug/metrics/
 1219  curl http://127.0.0.1:6060
 1220  curl http://127.0.0.1:6060/debug/metrics/prometheus
 1221  sudo journalctl -u geth -b | grep -A 4 metrics 
 1222  curl http://127.1.1.0:6060
 1223  curl http://127.1.1.0:6060/debug/metrics
 1224  sudo nvim /etc/systemd/system/geth.service 
 1225  sudo systemctl daemon-reload 
 1226  sudo systemctl restart geth.service 
 1227  ss -tulpn | grep geth
 1228  sudo ss -tulpn  | grep geth 
 1229  curl http://127.0.0.1:6060/debug/metrics/prometheus
 1230  clear
 1231  sudo apt install podman -yu
 1232  podman -v
 1233  podman ps 
 1234  ll
 1235  sudo mkdir -p /opt/monitoring/{prometheus,grafana}
 1236  ll /
 1237  sudo chown -R $User:$User /opt/monitoring/
 1238  ll /opt/
 1239  ll /
 1240  ll /opt/
 1241  ll /opt/monitoring/
 1242  sudo chown -R $USER:$USER /opt/monitoring/
 1243  ll /opt/monitoring/
 1244  nvim /opt/monitoring/prometheus/prometheus.yaml
 1245  clear
 1246  podman run -d  --name pro -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yaml:/etc/prometheus/prometheus.yaml:Z prom/prometheus
 1247  podman run -d  --name pro -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yaml:/etc/prometheus/prometheus.yaml:Z docker.io/prom/prometheus:latest
 1248  podman ps -a
 1249  ufw allow 3000/tcp
 1250  sudo ufw allow 3000/tcp
 1251  sudo ufw reload 
 1252  curl localhost:3000
 1253  curl localhost:9090
 1254  sudo ss -tulpn
 1255  sudo ufw allow 9090/tcp
 1256  htop
 1257  clear
 1258  exit
 1259  loginctl show-user mukul
 1260  sudo loginctl enable-linger mukul
 1261  exit
 1262  ls
 1263  getent passwd 
 1264  exit
 1265  ls
 1266  whoami
 1267  ps -e
 1268  pe -el | grep podman
 1269  podman ps 
 1270  podman ps -a
 1271  podman rm pro 
 1272  podman run -d --name pro -p 9090:9090 -v ./opt/monitoring/prometheus/prometheus.yaml:/etc/prometheus/prometheus.yaml:Z docker.io/prom/prometheus:latest
 1273  ls
 1274  cd /
 1275  ls
 1276  cd opt/
 1277  ls
 1278  cd monitoring/prometheus/
 1279  ls
 1280  pwd
 1281  ls
 1282  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yaml:/etc/prometheus/prometheus.yaml:Z docker.io/prom/prometheus:latest
 1283  podman ps 
 1284  podman exec prometheus 
 1285  podman exec --it prometheus.yaml bash
 1286  podman exec --it prometheus.yaml -- bash
 1287  podman exec -it prometheus bash
 1288  podman exec -it prometheus 
 1289  podman exec -it prometheus /bin/bash
 1290  sudo ss -tulpn
 1291  dig +short myip.opendns.com @resolver1.opendns.com
 1292  ls
 1293  ps -e geth
 1294  ps -el | grep geth
 1295  ps -rl |  grep geth
 1296  journalctl -u geth 
 1297  sudo journalctl -u geth 
 1298  pkill geth
 1299  sudo pkill geth
 1300  ps -el | grep geth
 1301  poweroff
 1302  clear
 1303  exit
 1304  ss -tulpn
 1305  ls
 1306  ll
 1307  cat Music/
 1308  ll Music/
 1309  ll TestDir/
 1310  ll config_default/
 1311  ll config_new/
 1312  ll scripts/
 1313  cat /etc/passwd
 1314  podman ps -a
 1315  podman inspect prometheus
 1316  ls /
 1317  ll /
 1318  cd /etc/
 1319  ls
 1320  ll
 1321  ll pro*
 1322  cd 
 1323  ls
 1324  ll /
 1325  ll srv
 1326  ll /srv
 1327  ll /opt
 1328  cd /opt/monitoring/
 1329  ls
 1330  for [[ls]]; do ll; done
 1331  for [[ ls ]] ; do
 1332  for [[ ls ]] ; do ll done
 1333  ll grafana/
 1334  ll prometheus/
 1335  cd prometheus/
 1336  cat prometheus.yaml 
 1337  podman ps 
 1338  podman exec -it prometheus bash
 1339  podman exec -it prometheus 
 1340  podman exec -it prometheus -- bash
 1341  podman exec -it prometheus  sh
 1342  cd 
 1343  ls
 1344  cd TestDir/
 1345  ls
 1346  cd ..
 1347  ls
 1348  cd config_new/
 1349  ls
 1350  nvim prometheus.yaml
 1351  ls
 1352  mv prometheus.yaml prometheus.yml
 1353  podmsn ps -a
 1354  podman ps -a
 1355  podman kill prometheus 
 1356  podman ps -a
 1357  podman ps
 1358  podman ps -a
 1359  podman rm prometheus 
 1360  ls
 1361  cp prometheus.yml /opt/monitoring/prometheus/
 1362  ls /opt/monitoring/prometheus/
 1363  ls
 1364  mkdir -p /opt/monitoring/prometheus/data
 1365  ls  /opt/monitoring/prometheus/
 1366  ls
 1367  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.y*:/etc/prometheus/ -v /opt/monitoring/prometheus/data/:/prometheus:Z docker.io/prom/prometheus:latest
 1368  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/ -v /opt/monitoring/prometheus/data/:/prometheus:Z docker.io/prom/prometheus:latest
 1369  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data/:/prometheus:Z docker.io/prom/prometheus:latest
 1370  podman rm prometheus 
 1371  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data/:/prometheus:Z docker.io/prom/prometheus:latest
 1372  podman ps 
 1373  podman  ps  -a
 1374  podman logs prometheus 
 1375  ls
 1376  nvim prometheus.yml 
 1377  cp prometheus.yml /opt/monitoring/prometheus/prometheus.yml
 1378  cat /opt/monitoring/prometheus/prometheus.yml 
 1379  clear
 1380  podman rm prometheus 
 1381  podamn run --name prometheus -d -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus:Z docker.io/prom/prometheus:latest
 1382  podman run  --name prometheus -d -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus:Z docker.io/prom/prometheus:latest
 1383  podman ps 
 1384  podman ps -a
 1385  podman logs prometheus 
 1386  journalctl -u prometheus 
 1387  journalctl -p 
 1388  journalctl -p 3
 1389  journalctl --help
 1390  journalctl | grep prometheus
 1391  timedatectl
 1392  timedatectl -p 6 | grep prometheus
 1393  timedatectl -p 7 | grep prometheus
 1394  timedatectl -p 8
 1395  journalctl -p 7
 1396  journalctl -p 9
 1397  journalctl -p 8
 1398  journalctl -p 6 | grep prometheus
 1399  journalctl -p 7 | grep prometheus
 1400  journalctl -p 5 | grep prometheus
 1401  journalctl -p 4 | grep prometheus
 1402  journalctl -p 3 | grep prometheus
 1403  journalctl -p 2 | grep prometheus
 1404  sudo journalctl -p 2 | grep prometheus
 1405  sudo journalctl -p 2 
 1406  sudo journalctl -p 1 
 1407  podman logs prometheus 
 1408  ls
 1409  cat prometheus.yml 
 1410  podman logs prometheus 
 1411  ll /opt/monitoring/prometheus/
 1412  ls
 1413  nvim prometheus.yml 
 1414  mv prometheus.yml prometheus_IDEAL.yml
 1415  cp prometheus_IDEAL.yml prometheus.yml
 1416  ls
 1417  nvim  prometheus.yml 
 1418  clear
 1419  ls
 1420  ls /opt/monitoring/prometheus/
 1421  ls
 1422  cd /opt/monitoring/prometheus/
 1423  ls
 1424  rm -rf prometheus.*
 1425  ls
 1426  ll data/
 1427  cd -
 1428  ls
 1429  cp prometheus.yml /opt/monitoring/prometheus/prometheus.yml
 1430  ls
 1431  podman ps -a
 1432  podman rm prometheus 
 1433  podman run --name prometheus -d -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus:Z docker.io/prom/prometheus:latest
 1434  podman ps 
 1435  podman ps -a
 1436  podman logs prometheus 
 1437  ls
 1438  nvim prometheus
 1439  nvim prometheus.yml 
 1440  cp prometheus.yml /opt/monitoring/prometheus/prometheus.yml 
 1441  ll /opt/monitoring/prometheus/
 1442  podman rm prometheus 
 1443  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus:Z docker.io/prom/prometheus:latest
 1444  podman ps
 1445  podman logs prometheus 
 1446  podman inspect prommethus
 1447  podman inspect prometheus
 1448  podman logs --details prometheus 
 1449  ls
 1450  cat prometheus.yml 
 1451  nvim prometheus.yml 
 1452  cp prometheus.yml /opt/monitoring/prometheus/prometheus.yml 
 1453  cat /opt/monitoring/prometheus/prometheus.yml 
 1454  podman rm prometheus 
 1455  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus:Z docker.io/prom/prometheus:latest
 1456  podman ps 
 1457  podman ps -a
 1458  podman logs prometheus 
 1459  nvim configSet.sh
 1460  sudo chmod 766 configSet.sh 
 1461  ls
 1462  sudo chmod +x configSet.sh 
 1463  ./configSet.sh 
 1464  nvim configSet.sh 
 1465  ./configSet.sh 
 1466  ls
 1467  nvim prometheus.yml 
 1468  ls
 1469  ./configSet.sh 
 1470  podman rm prometheus 
 1471  podman run --name prometheus -d -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus:Z docker.io/prom/prometheus:latest
 1472  podman ps -a
 1473  podman logs prometheus 
 1474  podmai
 1475  podman  
 1476  ls
 1477  clear
 1478  ls
 1479  ll
 1480  cd config_new/
 1481  ls
 1482  podman run --rm docker.io/prom/prometheus:latest id 
 1483  podman run --rm docker.io/prom/prometheus:latest 
 1484  podman run --rm -d docker.io/prom/prometheus:latest 
 1485  podman ps
 1486  podman exec -it stoic_benz id
 1487  podman kill  stoic_benz stoic_benz 
 1488  podman rm prometheus 
 1489  podman ps -a
 1490  ls
 1491  nvim configSet.sh 
 1492  cd /opt/monitoring/prometheus/data/
 1493  ls
 1494  cd ..
 1495  ls
 1496  cd ..
 1497  ls
 1498  ll
 1499  sudo chwom -R 65534:65534 ./prometheus/data/
 1500  ls 
 1501  ll
 1502  cd prometheus/
 1503  ll
 1504  sudo chown -R 65534:65534 ./data/
 1505  ll
 1506  ls
 1507  podman ps  -a
 1508  podman run --name prometheus -d -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus:Z docker.io/prom/prometheus:latest
 1509  podman ps 
 1510  podman ps  -a
 1511  podman logs prometheus 
 1512  ls -Z /opt/monitoring/prometheus/
 1513  podman volume create prometheus-data
 1514  podman volume 
 1515  podman volume ls
 1516  podman volume inspect 2e83872d68ff419f6fc25c029c8ac33989fec30e599341b3f4eb14cbfe5f4a7d 
 1517  podman volume inspect 9c778903c409588eb89a0665504d9bfaa5edb2cf42e353bd320300e50bfefa7f 
 1518  cd 
 1519  cd .local/share/containers/storage/volumes/
 1520  ls
 1521  ll
 1522  cd 2e83872d68ff419f6fc25c029c8ac33989fec30e599341b3f4eb14cbfe5f4a7d/
 1523  ls
 1524  cd _data/
 1525  ls
 1526  cd chunks_head/
 1527  ls
 1528  ll
 1529  sudo ls
 1530  sudo ll
 1531  sudo ls 
 1532  sudo ls -altir
 1533  cd ..
 1534  ls
 1535  cd wal/
 1536  ls
 1537  ll
 1538  cd ..
 1539  ls
 1540  cd ..
 1541  ls
 1542  cd ..
 1543  ls
 1544  cd 9c778903c409588eb89a0665504d9bfaa5edb2cf42e353bd320300e50bfefa7f/
 1545  ls
 1546  cd _data/
 1547  ls
 1548  sudo cp * ../../prometheus-data/_data/
 1549  sudo cp -r *  ../../prometheus-data/_data/
 1550  cd ../../prometheus-data/_data/
 1551  ls
 1552  cd 
 1553  ls
 1554  podman volume inspect prometheus-data 
 1555  clear
 1556  df -h
 1557  df -h .local/share/containers/storage/volumes/
 1558  podman ps -a
 1559  podman rm prometheus 
 1560  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v prometheus-data:/prometheus:Z docker.io/prom/prometheus:latest
 1561  podman ps 
 1562  podman ps 0a
 1563  podman ps -a
 1564  podman logs prometheus 
 1565  podman rm prometheus 
 1566  podman ps -a
 1567  podman run --name prometheus -d -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v /opt/monitoring/prometheus/data:/prometheus docker.io/prom/prometheus:latest
 1568  podman ps -a
 1569  podman logs prometheus 
 1570  podman rm prometheus 
 1571  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v prometheus-data:/prometheus docker.io/prom/prometheus:latest
 1572  podman ps -a
 1573  podman logs prometheus 
 1574  ll .local/share/containers/storage/volumes/prometheus-data/
 1575  ll .local/share/containers/storage/volumes/prometheus-data/_data/
 1576  ll   .local/share/containers/storage/volumes/9c778903c409588eb89a0665504d9bfaa5edb2cf42e353bd320300e50bfefa7f/_data/
 1577  sudo chown -R 165533:165533 .local/share/containers/storage/volumes/prometheus-data/_data/*
 1578  ll .local/share/containers/storage/volumes/prometheus-data/_data/
 1579  podman rm prometheus 
 1580  podman run -d --name prometheus -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v prometheus-data:/prometheus:Z docker.io/prom/prometheus:latest
 1581  podman ps  -a
 1582  ps -ef | grep geth
 1583  ps -r 
 1584  ss -tulip
 1585  sudo ss -tulpn
 1586  curl localhost:6060/metrics
 1587  curl localhost:6060
 1588  curl localhost:6060/metrics
 1589  journalctl -u geth 
 1590  sudo journalctl -u geth
 1591  curl localhost:6060/debug/metrics
 1592  curl localhost:6060/debug/metrics/prometheus
 1593  ls
 1594  cd config_new/
 1595  ls
 1596  nvim prometheus.yml 
 1597  ./configSet.sh 
 1598  podman kill prometheus 
 1599  podman rm prometheus 
 1600  podman run --name prometheus -d -p 9090:9090 -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v prometheus-data:/prometheus:Z docker.io/prom/prometheus:latest
 1601  podman ps
 1602  ls
 1603  cat prometheus.yml 
 1604  http://loalhost:9090
 1605  curl http://localhost:9090
 1606  curl http://localhost:9090/targates
 1607  curl http://localhost:9090/targets
 1608  podman exec -it prometheus curl http://host.containers.internal:6060/debug/metrics/prometheus
 1609  sudo ufw status
 1610  sudo ufw allow 6060/tcp
 1611  sudo ufw reload
 1612  curl localhost:6060/debug/metrics/prometheus
 1613  sudo ufw status
 1614  j
 1615  podman ps 
 1616  podman kill prometheus 
 1617  podman rm prometheus 
 1618  podman run --name prometheus -d -p 9090:9090 --network=host -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v prometheus-data:/prometheus:Z docker.io/prom/pormetheus:latest
 1619  podman run --name prometheus -d -p 9090:9090 --network=host -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v prometheus-data:/prometheus:Z docker.io/prom/prometheus:latest 
 1620  podman ps
 1621  curl localhost:6060/debug/monitor/
 1622  curl localhost:6060/debug/monitoring/
 1623  curl localhost:6060/debug/metrics/prometheus/
 1624  curl localhost:6060/debug/metrics/
 1625  curl localhost:6060/debug/metrics/prometheus
 1626  podman info prometheus
 1627  podman inspect prometheus 
 1628  podman inspect prometheus | grep network
 1629  podman logs prometheus 
 1630  ls
 1631  nvim prometheus.yml 
 1632  ./configSet.sh 
 1633  podman kill prometheus 
 1634  podman rm prometheus 
 1635  podman run --name prometheus -d -p 9090:9090 --network=host -v /opt/monitoring/prometheus/prometheus.yml:/etc/prometheus/prometheus.yml:Z -v prometheus-data:/prometheus:Z docker.io/prom/prometheus:latest 
 1636  exit
 1637  lsl
 1638  ls
 1639  ll
 1640  podman ps 
 1641  mkdir 1_Containerisation
 1642  ls
 1643  cd 1_Containerisation/
 1644  ls
 1645  history
 1646  history >> ./history.md
