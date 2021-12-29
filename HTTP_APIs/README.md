
# Instalação - RR Traceroute MTR
```
# apt install mtr-tiny
# cd /usr/lib/zabbix/externalscripts
```
### RR Traceroute MTR DNS.xml
```
# echo '#!/bin/bash' > zbx_mtr
# echo 'IP=$1' >> zbx_mtr
# echo 'mtr -r -c5 -w -b -p -j $IP | sed -e "s/???/* * */g"' >> zbx_mtr
# chown zabbix. zbx_mtr  
# chmod +x zbx_mtr
```
### RR Traceroute MTR NO-DNS.xml
```
# echo '#!/bin/bash' > zbx_mtr_nodns
# echo 'IP=$1' >> zbx_mtr_nodns
# echo 'mtr -r -c3 -w -b -p -j -n $IP | sed -e "s/???/* * */g"' >> zbx_mtr_nodns
# chown zabbix. zbx_mtr_nodns
# chmod +x zbx_mtr_nodns
```
