Repositório pessoal de templates Zabbix 5.0.x
Alguns dos templates foi copiado, alterado, mexido, bagunçado... rsrsrs 


Contribua também, se usar e fizer alguma melhoria, criar novos, não exite em compartilhar criando um pull request com as suas modificações/arquivo! 


Instalação do Zabbix 5.0 LTS + notificações pelo Telegram nativo + Grafana 7/8 + Debian 10/11
https://blog.remontti.com.br/4348 

### MIBs
Adicione contrib e non-free ao repositório.

```
# vim /etc/apt/sources.list

deb http://ftp.br.debian.org/debian/ stretch main contrib non-free
deb-src http://ftp.br.debian.org/debian/ stretch main contrib non-free

deb http://security.debian.org/debian-security stretch/updates main contrib non-free
deb-src http://security.debian.org/debian-security stretch/updates main contrib non-free

# stretch-updates, previously known as 'volatile'
deb http://ftp.br.debian.org/debian/ stretch-updates main contrib non-free
deb-src http://ftp.br.debian.org/debian/ stretch-updates main contrib non-free

# apt update
# apt upgrade
# apt install snmp-mibs-downloader snmp

# vim /etc/snmp/snmp.conf
Comente ==> #mibs :

# systemctl restart zabbix-server
# systemctl disable snmpd
# systemctl stop snmpd
```

