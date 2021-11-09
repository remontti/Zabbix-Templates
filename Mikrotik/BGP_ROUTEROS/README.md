###Crédito Python: Gabriel Vargas Padilha @gtkpad
###Crédito Zabbix: Rudimar Remontti @remontti

https://github.com/gtkpad

# Monitoramento dos Peers no RouterOS (Script Python)


## Zabbix Server 

```
# Requisitos
apt install python3-pip
pip3 install librouteros```

# Acesse o diretório externalscripts e faça download
cd /usr/lib/zabbix/externalscripts/

# De permissão para execução e altere o dono para o usuário zabbix
chmo +x .....
chown zabbix.
```

## RouterOS:
```# Crie um usuário com permissões somente de leitura bem como 
# restringindo o acesso para somente o IP do Zabbix
/user
add group=read address=IP_ZABBIX name=SEU_USUARIO password=SUA_SENHA

# Se desejar desativar as infomação de login.
# Isso fará com que você não veja mais nenhum login feito no router.
/system logging
set 0 topics=info,!account

OBS: Não use espaço no nome dos Peer's nem caracter especial, e tenha um nomes diferentes para cada Peer
```

## Importe o Template

## Crie seu Host 
Ou importe

## Grafana Modelo
Uma idéia para modelo da sua dash:
[img]
Link Dash Modelo