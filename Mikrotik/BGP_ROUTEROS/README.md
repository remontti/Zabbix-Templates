# Não use, ainda não terminei! 

# Monitoramento dos Peers no RouterOS (API + Script Python)
### Créditos 
<b>Python:</b> <a href="https://github.com/gtkpad">Gabriel Vargas Padilha</a> | <b><a href="https://github.com/gtkpad/mikrotikBgpZabbixScript">mikrotikBgpZabbixScript</b></a><br />
<b>Zabbix:</b> <a href="https://github.com/remontti">Rudimar Remontti</a> | <b><a href="https://github.com/remontti/Zabbix-Templates/edit/main/Mikrotik/BGP_ROUTEROS/">Zabbix BGP RouterOS</b></a>

<i>Espero que um dia a mikrotik inclua em seu snmp!</i> 🙌

<img src="https://raw.githubusercontent.com/remontti/Zabbix-Templates/main/Mikrotik/BGP_ROUTEROS/imgs/dados.png">
<img src="https://github.com/remontti/Zabbix-Templates/blob/main/Mikrotik/BGP_ROUTEROS/imgs/graficos_bgp.png">

# Configuração

## Zabbix Server 5.x
<i>Debian distro</i>

Requisitos
```
# apt install python3-pip
# pip3 install librouteros
```
Acesse o diretório externalscripts e faça download.
```
# cd /usr/lib/zabbix/externalscripts/
```
Faça download dos scripts 
```
# apt install wget 
# wget https://raw.githubusercontent.com/gtkpad/mikrotikBgpZabbixScript/main/main.py -O mikrotikBgp.py
# wget https://raw.githubusercontent.com/gtkpad/mikrotikBgpZabbixScript/main/Mikrotik.py
```
De permissão para os arquivos para execução e altere o dono para o usuário zabbix.
```
# chmod +x mikrotikBgp.py Mikrotik.py
# chown zabbix. mikrotikBgp.py Mikrotik.py
# systemctl  restart zabbix-server
```

## RouterOS / Mikrotik
OBS: Não use espaço e caracter especial nos nomes dos Peer's e tenha nomes diferentes para cada Peer.

Crie um usuário com permissões somente de leitura bem como restringindo o acesso para somente o IP do Zabbix
```
/user add group=read address=IP_ZABBIX name=SEU_USUARIO password=SUA_SENHA
```
Se desejar desativar as infomação de login. Isso fará com que você não veja mais nenhum login feito no router.
```
/system logging set 0 topics=info,!account
```

## Importe o Template
Faça download do template <a href="https://raw.githubusercontent.com/remontti/Zabbix-Templates/main/Mikrotik/BGP_ROUTEROS/RR%20Mikrotik%20-%20BGP%20-%20Script%20Python.xml">RR Mikrotik - BGP - Script Python.xml</a> e importe para seu Zabbix.

## Crie seu Host
<b>De um nome para seu host</b>
<img src="https://github.com/remontti/Zabbix-Templates/blob/main/Mikrotik/BGP_ROUTEROS/imgs/host_1.png">
  
<b>Selecione o Template</b>
<img src="https://github.com/remontti/Zabbix-Templates/blob/main/Mikrotik/BGP_ROUTEROS/imgs/host_2.png">

<b>Herde os macros do template, e modifique para os seus dados e clique em salvar</b>
<img src="https://github.com/remontti/Zabbix-Templates/blob/main/Mikrotik/BGP_ROUTEROS/imgs/host_3.png">

OBS: A descoberta esta ajustada para 6h, se desejar que seja mais rápido execute manualmente.

## Grafana Modelo
Uma idéia para modelo da sua dash:
<img src="https://github.com/remontti/Zabbix-Templates/blob/main/Mikrotik/BGP_ROUTEROS/imgs/grafana.png">
Importe a <a href="https://raw.githubusercontent.com/remontti/Zabbix-Templates/main/Mikrotik/BGP_ROUTEROS/Grafana_Modelo.json">Dash Modelo</a>

## Tutorial de instalção do Zabbix
<a href="https://blog.remontti.com.br/5517">Instalação do Zabbix 5 LTS + Grafana + NGINX + PostgreSQL + Telegram</a>

## LICENÇA
Se usar ou melhorar não seja cuzão de não compartilha!
