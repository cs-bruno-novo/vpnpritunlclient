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

Configurando Client
---

Abrir o Pritunl Client:

![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/01.png)


Após importar o arquivo .tar que recebido, faça o teste de conexão para algum endereço interno:
```
ping <hostname ou ip>
```
Obs. Caso o endereço não responder pelo nome (DNS), teste pelo IP e verifique se o arquivo de configuração esta com o DNS da rede (VPN):
```shell
vi /etc/resolv.conf
```
Deve conter um novo nameserver conforme exemplo:
```shell
search hostnamelocal
nameserver 8.8.8.8 
nameserver <ip_dns_rede_vpn>
```
