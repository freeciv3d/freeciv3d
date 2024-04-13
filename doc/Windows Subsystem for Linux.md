Run Fciv.net on Windows Subsystem for Linux (WSL)

=================================================

  

Allows running Freeciv3D on an Ubuntu Linux in Windows.

  
## 1. Running Fciv-net on WSL:

### 1.1. Install WSL on Windows 11:

https://learn.microsoft.com/en-us/windows/wsl/install

Open a Powershell window, run as Administator, this command:

> wsl --install

  

### 1.2. Git clone Fciv.net:

> git clone https://github.com/fciv-net/fciv-net.git --depth=10

  

### 1.3. Build Fciv.net:

> cd fciv-net

> ./scripts/install/install.sh --mode=TEST

  

### 1.4. Start Fciv.net:

> ./scripts/start-freeciv-web.sh

  

### Open Fciv.net at http://localhost/

<br />

## 2. Known problems

### 2.1. SQL problems
#### 2.1.1. error: 'Access denied for user 'root'@'localhost'

> error: 'Access denied for user 'root'@'localhost' (using password: YES)'

  

![sql bug](https://raw.githubusercontent.com/fciv-net/fciv-net/main/doc/img/sql_bug.png  "")

This error can happen when Fciv-net is stopped, both during compilation and run-time. It can be solved by stopping mySQL:

> sudo systemctl stop mysql

  

Try to re-run Fciv-net. If the same error happens again, the only known solution is to completely uninstall mySQL.

> sudo systemctl stop mysql

> sudo apt-get purge mysql-server mysql-client mysql-common mysql-server-core-* mysql-client-core-*

> sudo rm -rf /etc/mysql /var/lib/mysql

> sudo apt autoremove && sudo apt autoclean

or a single long command:

> sudo systemctl stop mysql && sudo apt-get purge mysql-server mysql-client mysql-common mysql-server-core-* mysql-client-core-* && sudo rm -rf /etc/mysql /var/lib/mysql && sudo apt autoremove && sudo apt autoclean

Now try to install Fciv-net again. mySQL will be automatically reinstalled.

### 2.2. tomcat problems

#### 2.2.1. mv: cannot move 'apache-tomcat-10.1.18'

> mv: cannot move 'apache-tomcat-10.1.18' to 'tomcat10/apache-tomcat-10.1.18': Directory not empty


![tomcat bug](https://raw.githubusercontent.com/fciv-net/fciv-net/main/doc/img/tomcat_bug.png  "")

This issue can appear during compilation. It can be solved by removing the /var/lib/tomcat10 folder.
> sudo rm -r /var/lib/tomcat10
=======
Now install Fciv-net again. mySQL will be automatically reinstalled.
