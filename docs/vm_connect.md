## Connecting to your virtual machines

There are different ways to interact with your virtual machines (VM):

1. with a **web interface** (HTTP) with web-enabled cloud appliances, for example RStudio, Jupyter Notebooks;
2. with the **SSH command line interface** (CLI) through a terminal window;
3. with a **remote graphical desktop** (X2Go or VNC).

Once the deployment of your VM is done successfully, you can get all connection parameters from the column `Access` in the  [**myVM** tab](https://biosphere.france-bioinformatique.fr/cloud) of the biosphere portal.
You will find the HTTP/S link (if any) to your VM, or the SSH parameters (`username` and `IP address`) to use to connect to your VM.

### 1. Connecting to a VM with a web interface

Simply click on the **HTTPS** link to be redirected to the web portal provided by your VM. In the case you are requested to provide the `username` and `password`, or the `access token`, they are provided through the parameters field `Params` in the `Access` column. These security parameters are unique for your VM and only known to you (and of course to the administrators of your group and of the cloud site for operationnal reasons).


### 2. Connecting to a VM with SSH 

An SSH client is installed by default in any computer with Linux (CentOS, Ubuntu, Debian,...), MacOS ([doc](https://support.apple.com/fr-gq/guide/terminal/apd5265185d-f365-44cb-8b09-71a064a42125/mac))
and MS Windows 10 (and higher).

From MS Windows 10 release, you can use both
the PowerShell ([doc](https://docs.microsoft.com/fr-fr/powershell/scripting/learn/ps101/01-getting-started?view=powershell-7.2#where-do-i-find-powershell))
or the WSL - Windows Subsystem Linux - based on Ubuntu ([doc](https://docs.microsoft.com/fr-fr/windows/wsl/install-win10)). 

#### Configuring your SSH parameters in your Biosphere profile

First, you need to **configure your SSH parameters before creating a VM with SSH access**.
Indeed your SSH PubKey will be imported in your VM at its creation, and cannot be modified afterwards.

##### 1. Get your SSH PubKey

  Open a terminal window (Linux, MacOS) or a PowerShell (MS Windows) and type the following command.

  ```
  cat $HOME/.ssh/id_rsa.pub
  ```

  If you got an empty answer, you do not have already a SSH keys pair, and you can create one with the following command.

!!! Warning
    If you have already a SSH key pair, you risk overwriting it with this new command..

  ```
  ssh-keygen -t rsa
  ```

##### 2. Open your account parameters page
  They are available from the user menu in the top-right corner of the Biopshere portal [[go](https://biosphere.france-bioinformatique.fr/cloudweb_account/settings/)].

##### 3. Click the Edit button.

##### 4. Copy your SSH public key in the `Pubkey` field.

You can paste several public keys but be careful that each one is on one line only.

#### Opening the SSH connection to the VM

To connect to a VM with SSH, you will need to

- open the VM description page by clicking on its `ID` link in the Biosphere dashboard [**myVM**](https://biosphere.france-bioinformatique.fr/cloud),
- in the VM page, copy the `ssh` command from the table `Access`,
- paste the copied text in a terminal (Linux, MacOS) or a PowerShell window (MS Windows),
- and hit return.

The connection will be established according to the SSH public key you configured in your profile (see above).

You can also click on the `ssh` link in the Biosphere dashboard to open
a new terminal with an automatic SSH connection to  your VM.
_(But this will work only with MacOS and most Linux.)_


### 3. Connecting to a VM with a virtual remote desktop

You can connect to a desktop VM in two different ways, with X2Go or with VNC.

Opening a remote desktop requires to have both

- configured your SSH parameters (see above),
- and installed the X2Go or a VNC client and dependencies (see below).

!!! Warning 
    With recent version of Ubuntu, there is a known bug with the X2Go desktop related to the compatibility of the X2Go server with the GLX library.
    So if you encounter some troubles with X2Go, you should perfer a connection with VNC 


#### Connecting to a desktop VM with X2Go

##### 1. Install the X2Go client

[X2Go download instructions - chapter X2Go Client](https://wiki.x2go.org/doku.php/download:start).

##### 2. Install the X server software

* [MacOS] : Xquartz (https://www.xquartz.org/)
* [MS Windows 10] : VcXsrv (https://sourceforge.net/projects/vcxsrv) or Xming (https://sourceforge.net/projects/xming/)

*Linux distributions have usually an X server installed by default.*

##### 3. Open the remote desktop connection to the VM

You can get the connection parameters of the VM in the `Params` fields of the column `Access` (in the [**myVM** tab](https://biosphere.france-bioinformatique.fr/cloud)):

- `username`
- `IP/hostname` of the VM
- `session type` (usually XFCE)

Then, you will use them to configure a session in the X2Go client (see [X2Go usage instructions](https://wiki.x2go.org/doku.php/doc:usage:x2goclient)). And do not forget to check the box for `Automatic authentication (with SSH agent or default key)`

#### Connecting to a desktop VM with VNC

You can use any VNC client, for example the TigerVNC one (https://tigervnc.org)
([download the latest release](https://sourceforge.net/projects/tigervnc/files/stable/)).

##### 1. Connect to your VM with SSH

`ssh -L 5901:localhost:5901 ubuntu@<vm-ip>`

_(Valid for Ubuntu VM, replace `ubuntu` by `debian` or `rocky` according to the VM you are running)_

##### 2. Once connected to your VM, launch the VNC server

`vncserver -localhost yes -autokill no -SecurityTypes None`

##### 3. Verify that the service is running

`vncserver -list`

##### 4. Connect to the desktop

On your local computer, open the TigerVNC client, and fill in the window the parameter `VNC server` with the value `localhost:5901`.
