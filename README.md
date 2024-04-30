# Installazione su WSL:
In questo tutorial installeremo: 
1) MySQL (il dbms che useremo)
2) L'interprete del linguaggio PHP (il linguaggio che useremo)
3) Il web server apache (non necessario, ma utile)
4) Il tool MySQL Workbench (con due metodi diversi)


>## N.b il tutto è previsto ed aggiornato su Ubuntu(wsl) 22.04.4 LTS
>E' prevista quindi come **pre-requisito** l'installazione di ubuntu.

## Apache2
```
sudo apt install apache2
```
## MySQL
```
sudo apt install mysql-server
```

## Php
```
sudo apt install php-perl php-fpm php-dev php-zip php-curl php-xmlrpc php-gd php-mysql phpmbstring php-xml libapache2-mod-php
```

## Restart Server 
per aggiornare la config:
```
sudo service apache2 restart
```
## Check Apache

Aprendo il web browser e accedendo al seguente url: http://localhost/. 
Dovreste visualizzare un messaggio in cui dice che funziona.

## Check Php

Eseguendo il seguente comando viene svolto il controllo di funzionamento :
```
php -r 'echo "\n\n Your PHP installation is working fine. \n\n";'
```
## MySQL Workbench
>Vi sono due metodi principali :
> - Usare MySQL Workbench **da Microsoft Windows**
> - Provare installazione diretta **da Ubuntu (sconsigliata/più instabile)**

### Scelta 1:
Installare MySQL workbench  al seguente link https://dev.mysql.com/downloads/workbench/ creare poi una nuova connesione in local host.

### Scelta 2:
lanciare i seguenti pre command: 
-   ```sudo apt-get update```
-   ```sudo apt-get upgrade```
-   ```sudo apt-get install libpython2.7-minimal```
-   ```sudo apt-get install libpython2.7-stdlib```
-   ```sudo apt-get install libpython2.7```
-   ```sudo apt-get install libmysqlclient-dev```
-   ```sudo apt-get install libpcrecpp0v5```
-   ```sudo apt-get install libproj-dev```
	
e seguite questa guida per installare MySQL Workbench:
[https://tutorialforlinux.com/2020/02/19/step-by-step-mysql-workbench-ubuntu-20-04-installation-guide/](https://tutorialforlinux.com/2020/02/19/step-by-step-mysql-workbench-ubuntu-20-04-installation-guide/)

Se invece è presente la versione **Ubuntu 20.10 o 21.04** o altre versioni e avete dei problemi allora cercate su internet come installare MySQL Workbench sulla vostra versione di Ubuntu.

Cercando su Google è possibile trovare la **guida per Ubuntu 21.04**:

[https://tutorialforlinux.com/2021/03/30/step-by-step-mysql-workbench-ubuntu-21-04-installation-guide/](https://tutorialforlinux.com/2021/03/30/step-by-step-mysql-workbench-ubuntu-21-04-installation-guide/)
