# Repositório pessoal de templates Zabbix 5.x > 6.x 
Alguns dos templates foram copiado, alterado, mexido, bagunçado... rsrsrs

Contribua também, se usar e fizer alguma melhoria, criar novos, não hesite em compartilhar criando um pull request com as suas modificações/arquivo! 

### Instalação do Zabbix 
#### 6.0 LTS Debian 11
https://blog.remontti.com.br/6350

#### 5.0 LTS + Grafana - Debian 10/11
Acesse: https://blog.remontti.com.br/4348 

#### Grafana - Debian 11
Acesse: https://blog.remontti.com.br/6370

### Instalação MIBs :: (Requisito para alguns Templates)
Instale o pacotes snmp-mibs-downloader e snmp, para isso sera necessário adicionar <b>contrib e non-free</b> ao repositório.
```
# vim /etc/apt/sources.list
```
<b>VERSÃO:</b> buster / bullseye
<pre>
deb http://ftp.br.debian.org/debian/ {VERSAO} main <b>contrib non-free</b>
deb-src http://ftp.br.debian.org/debian/ {VERSAO} main <b>contrib non-free</b>

deb http://security.debian.org/debian-security {VERSAO}/updates main <b>contrib non-free</b>
deb-src http://security.debian.org/debian-security {VERSAO}/updates main <b>contrib non-free</b>

# stretch-updates, previously known as 'volatile'
deb http://ftp.br.debian.org/debian/ {VERSAO}-updates main <b>contrib non-free</b>
deb-src http://ftp.br.debian.org/debian/ {VERSAO}-updates main <b>contrib non-free</b>
</pre>

```
# apt update
# apt upgrade
# apt install snmp-mibs-downloader snmp
```
```
# vim /etc/snmp/snmp.conf
```
Comente ==> #mibs :
```
# systemctl restart zabbix-server
# systemctl disable snmpd
# systemctl stop snmpd
```

## Comandos úteis
snmpwalk / snmptranslate<br />
<b>Exemplos:</b>
```
# snmpwalk -v2c -c public 10.10.20.30 .1.3.6.1.2.1.2.2.1.2
# snmptranslate -m ALL 1.3.6.1.2.1.2.2.1.2
# snmptranslate -On IF-MIB::ifName
```
