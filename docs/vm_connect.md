## Connecting to your virtual machines

There are different ways to interact with your virtual machines (VM):

1. with a **web interface** (HTTP) with web-enabled cloud appliances, for example RStudio, Jupyter Notebooks;
2. with the **SSH command line interface** (CLI) through a terminal window;
3. with a **remote graphical desktop** (X2Go).

Once the deployment of your VM is done successfully, you can get all connection parameters from the column `Access` in the  [**myVM** tab
](https://biosphere.france-bioinformatique.fr/cloud) of the biosphere portal. You will find the HTTP link (if any) to your VM, or the SSH parameters (`username` and `IP address`) to use to connect to your VM.

### 1. Connecting to the web interface of a VM

Simply click on the **HTTPS** link to be redirected to the web portal provided by your VM. In the case you are requested to provide the `username` and `password`, or the `access token`, they are provided through the parameters field `Params` in the `Access` column. These security parameters are unique for your VM and only known to you (and of course to the administrators of your group and of the cloud site for operationnal reasons).


### 2. Connecting with SSH to a VM

An SSH client is installed by default in any computer with Linux (CentOS, Ubuntu, Debian,...), MacOS ([doc](https://support.apple.com/fr-gq/guide/terminal/apd5265185d-f365-44cb-8b09-71a064a42125/mac))
and MS Windows 10 (and higher). From MS Windows 10 release, you can use both
the PowerShell ([doc](https://docs.microsoft.com/fr-fr/powershell/scripting/learn/ps101/01-getting-started?view=powershell-7.2#where-do-i-find-powershell))
or the WSL - Windows Subsystem Linux - based on Ubuntu ([doc](https://docs.microsoft.com/fr-fr/windows/wsl/install-win10)). 

#### Configuring your SSH parameters in the Biosphere portal

First, you need to **configure your SSH parameters before creating a VM with SSH access**.
Indeed your SSH PubKey will be imported in your VM at its creation, and cannot be modified afterwards.

##### 1. Get your SSH PubKey

  Open a terminal window (Linux, MacOS) or a PowerShell (MS Windows) and type the following command.

  ```
  cat $HOME/.ssh/id_rsa.pub
  ```

  If you do not have already your SSH keys pair, you can create one with the following command.

  ```
  ssh-keygen -t rsa
  ```
##### 2. Open your account parameters page
  They are available from the user menu in the top-right corner of the Biopshere portal [[go](https://biosphere.france-bioinformatique.fr/cloudweb_account/settings/)].
##### 3. Click the Edit button.

##### 4. Copy your SSH public key in the `Pubkey` field.

You can paste several public keys but be careful that each one is on one line only.

#### Opening the SSH connection to the VM

Opening the SSH connection to the VM simply requires you to click on the `ssh` link to be redirected to the terminal with an automatic SSH connection to  your VM. This will work for MacOS and most Linux. For others systems, you have to copy from the `ssh` link, paste the copied text in a terminal or a PowerShell window, and replace the '://' by ' ' in the command to run. The connection will be opened according to the SSH key you configured (see above).

### 3. Opening a remote desktop with X2Go to a VM

Opening a remote desktop requires to both have configured your SSH parameters (see above) and installed the X2Go client and dependencies.

#### Configuring the software tools 

* [All OS] Install the X2Go client: [X2Go download instructions - chapter X2Go Client](https://wiki.x2go.org/doku.php/download:start).
* [MacOS] Install the X server software [Xquartz]()
* [MS Windows 10] Install an X server sotware : [VcXsrv](https://sourceforge.net/projects/vcxsrv) or [Xming](https://sourceforge.net/projects/xming/)

*Linux distributions have usually an X server installed by default.*

#### Opening the remote desktop connection to the VM

You can get the connection parameters of the VM in the `Params` fields of the column `Access` (in the [**myVM** tab](https://biosphere.france-bioinformatique.fr/cloud)).
- `username`
- `IP/hostname` of the VM
- `session type` (usually XFCE)

Then, you will use them to configure a session in the X2Go client (see [X2Go usage instructions](https://wiki.x2go.org/doku.php/doc:usage:x2goclient)). And do not forget to check the box for `Automatic authentication (with SSH agent or default key)`


### Annex - Using the `PuTTY` software tool with MS Windows older than 10

We describe here the use of the `PuTTY` tool, which could be used to connect with SSH to your VM, or to a remote desktop with `X2Go` tool. **This solution should be used only in case your MS Windows OS is older than MS Windows 10. For MS windows 10 and higher, we recommend to use the PowerShell (see above).**

First, you need to install `PuTTY` on your machine. You can find both the download and installation instructions on the [official web site](http://www.putty.org/). Take care to use the MSI (‘Windows Installer’).

  * Creating your SSH keys and configuring your Biosphere account
  
    1. Open the software `PuTTYgen` from the MS Windows Start menu.
    2. Choose `SSH-2 RSA` in the bottom and click on `Generate`.
    3. Click on the `Save private key` button to save the **private key** in a file called `ClePriv-PUTTY` on the Desktop (*This file will be useful to open an SSH connection to your VM with PuTTY*).
    4. Exec the menu `Conversions > Export OpenSSH key` to save the private key in a SSH-format file called `ClePriv-SSH`, also on the Desktop (*You will need it to open a remote desktop with the X2Go tool, or with FileZila to tranfer data to/from the VM*).
    5. Copy the **public key** from the `Public Key for pasting into OpenSSH (...)` at the top of the window.
    6. Paste this copied SSH public key in the field `PubKey` of your Biosphere account parameters.

  * Opening an SSH connection to your VM

    1. Open the software `PuTTY` from the MS Windows `Start` menu
    2. Copy the `IP/hostname` of your deployed VM from the Biosphere dashboard (put you mouse over  `?` next to the name of the VM)
    3. Paste the `IP/hostname` in the field `Session > HostName (or IP address)`
    ([doc](https://the.earth.li/~sgtatham/putty/0.76/htmldoc/Chapter4.html#config-session))
    4. Select `SSH` for the `Connection type`
    5. Fill the `Auto-login username` in the menu `Data` ([doc](https://the.earth.li/~sgtatham/putty/0.76/htmldoc/Chapter4.html#config-data)) with the default one (`ubuntu`, `debian` or `centos`) according to the Linux system of your VM.
    6. Select the file `ClePriv-PUTTY` in the menu `Connection > SSH >Auth > Private key file for authentication`.

  * Opening a remote desktop to your VM

    1. Open the software `X2Go` from the MS Windows Start menu
    2. Create a new X2GO session (see above)
