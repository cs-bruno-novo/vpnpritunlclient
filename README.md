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
####Abrir o Pritunl Client:
![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/01.png)


####Importar o arquivo gerado para o usuario:
![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/02.png)

![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/03.png)


####Conectar através do client:
![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/04.png)


####Coloque a chave (google authenticator ou key fornecida):
![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/05.png)

Obs. Em alguns sistemas irá solictar a senha de usuário para confirmar.

####Conectando:
![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/07.png)

####VPN Conectada:
![](https://github.com/cs-reinaldo-pinto/vpnpritunlclient/blob/master/imagens/08.png)


Após importar o arquivo .tar recebido, se necessário faça o teste de conexão.
---

Teste um endereço interno:
```
ping <hostname ou ip>
```
Obs. Caso o endereço não responder pelo hostname (DNS), teste pelo IP. 
Verifique se o arquivo de configuração do DNS da sua maquina esta com o DNS da rede da VPN:
```shell
vi /etc/resolv.conf
```
Deve conter um novo nameserver conforme exemplo:
```shell
search hostnamelocal
nameserver 8.8.8.8 
nameserver <ip_dns_rede_vpn>
```
