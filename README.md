# vpnpritunlclient

Configurar VPN Pritunl-Client no Ubuntu Desktop 
---

Faça o logon na conta de root:
```shell
reinaldo@reinaldo-concrete:~$ sudo su -
root@reinaldo-concrete:~#
```

Adicione o repositorio (no nosso caso Ubuntu):
```shell
echo "deb http://repo.pritunl.com/stable/apt trusty main" >> /etc/apt/sources.list.d/pritunl.list
```
Adicione keyserver, atualize o novo repositorio adicionado e instale o Pritunl-Client :
```shell
apt-key adv --keyserver hkp://keyserver.ubuntu.com --recv CF8E292A && 
\ apt-get update && 
\ apt-get install pritunl-client-gtk -y
```

Configure 

Após importar o arquivo .tar que recebido, faça o teste de conexão:
```
ping <hostname ou ip>
```
