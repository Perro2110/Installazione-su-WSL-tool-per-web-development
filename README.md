# <a href="https://learn.microsoft.com/it-it/windows/wsl/" target="_blank" rel="noreferrer"><img src="https://store-images.s-microsoft.com/image/apps.61786.14131597032361940.38d2a067-3798-455f-934a-f69935156b3d.eb49d3ac-e311-4e6f-b89b-f1fe8db9d73b" alt="WSL" width="35" height="35"/></a> Installazione su WSL:
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
sudo apt install php-pear php-fpm php-dev php-zip php-curl php-xmlrpc php-gd php-mysql php-mbstring php-xml libapache2-mod-php
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
> - Scelta 1:   Usare MySQL Workbench **da Microsoft Windows**
> - Scelta 2:   Provare installazione diretta **da Ubuntu (sconsigliata/più instabile)**

 ### Scelta 1:

Installare MySQL workbench  al seguente link https://dev.mysql.com/downloads/workbench/ creare poi una nuova connesione in local host.

Se nell'atto della connessione/creazione di connessione dopo l'inserimento negli appositi campi: 

 > ***Connection name*** ⇒ Con nome deciso dall'utente <br>
  ***Connection method*** ⇒ da tenere di default <br>
  ***Hostname*** ⇒ 127.0.0.1  (default) <br>
  ***Port***  ⇒ 3306 (default) <br>
  ***Username*** ⇒ root (default) <br>
  ***Password*** ⇒  root (default) <br>
   *(In pratica si tenga quasi tutto di default tranne il ***Connection name***.)*

risultasse un qualunque errore di connessione o di permission denied (cosa molto frequente) si prosegua come segue: 

## Creazione di un nuovo utente per generare e gestire la connesione (Risoluzione a problemi vari):
All'interno di WSL mandare in esecuzione i seguenti comandi:
```
sudo mysql -u root -p
```
rispondere alla richiesta di sudo con propria password di sistema e rispondere alla seconda richiesta di password per accesso a root di mysql attraverso ```root``` come risposta.
Digitare poi le due query come segue: 
mysql> ```CREATE USER 'local_user'@'localhost' IDENTIFIED BY 'password';```
mysql>  ```GRANT ALL ON *.* TO 'local_user'@'localhost' WITH GRANT OPTION```
A seguire ricreare/instaurare una nuova connesione su MySQL workbench con i parametri richiesti in input come segue: 
> ***Connection name*** ⇒  Con nome deciso dall'utente <br>
> ***Connection method*** ⇒  da tenere di default <br>
> ***Hostname*** ⇒  127.0.0.1  (default) <br>
 ***Port*** ⇒  3306 (default) <br>
 ***Username*** ⇒  local_user (settato dalla query) <br>
 ***Password*** ⇒   password  (settato dalla query) <br>
---
Da ora quando si vuole usare MySQL workbench è possibile farlo alla connesione appena creata mentre se si vogliono mandare query o scrivere codice da CLI di WSL questo è possibile digitando su WSL il comando:
```
sudo mysql -u local_user -p
```
è autenticandosi come richiesto.


---
### <div align="center">Siete giunti alla conclusione ora il vostro ambiente è completo e funzionante !! </div>
---

 ### Scelta 2:
 
 *<div align="center">(Si ricorda essere una "strada" sconsigliata)</div>*
lanciare i seguenti pre-command: 
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

---
### <div align="center">Siete giunti alla conclusione ora il vostro ambiente è completo e funzionante !! </div>
---
