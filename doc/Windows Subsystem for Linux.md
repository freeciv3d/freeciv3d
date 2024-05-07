Run Fciv.net on Windows Subsystem for Linux (WSL)

=================================================

  

Allows running Freeciv3D on an Ubuntu Linux in Windows.

  
## 1. Running Fciv-net on WSL:

### 1.1. Install WSL on Windows 11:

https://learn.microsoft.com/en-us/windows/wsl/install

Open a Powershell window, run as Administator, this command:

> wsl --install

  

### 1.2. Git clone Fciv.net:

> git clone https://github.com/freeciv3d/freeciv3d.git --depth=10

  

### 1.3. Build Fciv.net:

> cd fciv-net

> ./scripts/install/install.sh --mode=TEST

  

### 1.4. Start Fciv.net:

> ./scripts/start-freeciv-web.sh

  

### Open Fciv.net at http://localhost/

<br />

