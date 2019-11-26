## Connecting to your virtual machines

There are different way to interact with your virtual machines:
1. with a **web interface** (HTTP) for web-enabled cloud appliances, for example RStudio, Jupyter Notebooks. 
2. with the **command line interface** (CLI) through a terminal window or graphical SSH tools (PuTTY, MobaXterm...).
3. with a **remote graphical desktop** (X2Go).

Once the deployment of your VM is done successfully, you can get all connection parameters from the **myVM** tab of the biosphere portal
[[go](https://biosphere.france-bioinformatique.fr/cloud)], in the column **Access**. You will find the HTTP link (if any) to your VM, the SSH parameters with the `username` and `IP address` to use for your VM.

### 1) Connecting to the web interface of a VM

Simply click on the **http** link to be redirected to the web portal provided by your VM. In some cases you may need to know the `username:password` or a access token that will be provided through a parameters field (Params) in the Access column.


### 2) Connecting with SSH to a VM

Before creating the VM with SSH access, you need to **configure your SSH parameters** (see Annex below).

#### SSH instructions for Linux and MacOS users

SSH client is installed by default in any computer using Linux (CentOS, Ubuntu, Debian,...) or MacOS. 

You can click on the **ssh** link to be redirected to the terminal with an automatic SSH connection to  your VM. It will work for most most Linux and for MacOS. An alternative is to copy-paste the link in a terminal, with replacing the '://' by ' ' in the command.

#### SSH Instructions for Windows PC users

We describe here the use of PuTTY, which will be also useful to connect to a remote desktop with X2Go (see below). 

**N.B.:** *From Windows 10 release, you can also use the Linux Bash Shell based on Ubuntu (see [install instructions](https://docs.microsoft.com/fr-fr/windows/wsl/install-win10)). Then, you need to follow the Get your SSH PubKey for Linux below (in Annex).*

To use PuTTY, you need first to install it on your machine (see [download instructions](http://www.putty.org/)
where you will find both the download and installation instructions). Take care to use the MSI (‘Windows Installer’).

Then you have to copy the IP/hostname of your deployed VM (click on the question mark `?` next to the name of the VM), and paste it in the configuration of the PuTTY tool:
  * in the field `Session -> HostName (orIP address)`
  * and select `SSH` for the `Connection type`

### 3) Connecting with X2Go to a VM

Before creating the VM with SSH access, you need to **configure your SSH parameters** (see Annex below).

First, you need to install the requirement on your own local computer:
* [All OS] Install the X2Go client: [X2Go download instructions](https://wiki.x2go.org/doku.php/doc:installation:x2goclient).
* [MacOS] Install the X server [Xquartz]()
* [MS Windows with Ubuntu Bash] Install one X server : [VcXsrv](https://sourceforge.net/projects/vcxsrv) or [Xming](https://sourceforge.net/projects/xming/)

Second, you get the connection parameters for the VM in the `Params` fields of the column `Access` (tab **myVM**).
- the username
- the IP/hostname of the VM
- the session type (usually XFCE for Ubuntu)

Third, you configure a session in X2Go client with these parameters (see [X2Go usage instructions](https://wiki.x2go.org/doku.php/doc:usage:x2goclient)). The required ones are:
- the `username`
- the `IP/hostname`
- the `session type`
- check the `Automatic authentication (with SSH agent or default key)`


### Annex - Configure your SSH parameters

1. Open your account parameters page from the user menu in the top-right corner of the Biopshere portal
[[go](https://biosphere.france-bioinformatique.fr/cloudweb_account/settings/)].

2. Click the Edit button

3. Get your SSH PubKey:

  * **Linux, MacOS, Win10 with Linux Bash Shell**: in a terminal execute `cat $HOME/.ssh/id_rsa.pub`.
If you do not have already an SSH key, create one with `ssh-keygen -t rsa`.

  * **MS-Windows with PuTTY**: Open the tool PuTTYgen from the Start menu
    1. Choose `SSH-2 RSA` in the bottom and click on `Generate`.
    2. Click on the `Save private key` button to save the *Private key* in a file called ClePriv-PUTTY on the Desktop.
  This file will be used to SSH-connect to your VM with PuTTY. Add it to the PuTTY configuration in the field at
  `Connection->SSH->Auth-> Private key file for authentication`.
    3. Do also menu `Conversions -> Export OpenSSH key`, and save it in a file called ClePriv-SSH, also on the Desktop.
  You will need it to connect for example with the X2Go tool to access the remote dekstop of a VM, or FileZila to tranfer data to/from the VM.
    4. And finaly copy the PubKey from the `Public Key for pasting into OpenSSH (...)` at the top of the window, that you will paste in the SSH PubKey field of your Biosphere account parameters.

4. Paste your SSH PubKey (public key) in the related field of your Biosphere account parameters. You can paste several PubKey but
**be careful that each PubKey is on one line only**
