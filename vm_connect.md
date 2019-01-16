## Connect to your virtual machines

There are different way to connect to virtual machines: command line interface (CLI) with SSH tool, web interface (HTTP) or remote graphical desktop (X2Go). Once the deployment of your VM is done successfully, you can get all access infromations from the **myVM** tab of the biosphere portal
[[go](https://biosphere.france-bioinformatique.fr/cloud)], where the column **Access** provides you with details.

### Connect to the web interface of VMs

Simply click on the **http** link to be redirected to the web portal provided by your VM.

### Connect with SSH to VMs

#### Instructions for Linux and MacOS users

SSH client is installed by default in any computer using Linux (CentOS, Ubuntu, Debian,...) or MacOS. 

You can click on the **ssh** link to be redirected to the terminal with an automatic SSH connection to  your VM. It will work for most most Linux and for MacOS. An alternative is to copy-paste the link in a terminal, with replacing the '://' by ' ' in the command.

#### Instructions for Windows PC users

You need to install the tool PuTTY available from its web site [PuTTY web site](http://www.putty.org/),
where you will find also the download and installation instructions. Take care to use the MSI (‘Windows Installer’).

You will need to to copy the IP/hostname of your VM (click on the question mark to get it), and paste it in the configuration of the PuTTY tool:
  * in the field "Session -> HostName (orIP address)"
  * and select "SSH" for the "Connection type"

#### Setting your SSH parameters

Before creating the VM with SSH access, you need to configure your SSH parameters.

1. Open your account parameters page from the user menu in the top-right corner of the Biopshere portal
[[go](https://biosphere.france-bioinformatique.fr/cloudweb_account/settings/)].

2. Click the Edit button

3. Get your SSH PubKey:

  * **Linux and MacOS**: in a terminal execute `cat $HOME/.ssh/id_rsa.pub`.
If you do not have already an SSH key, create one with `ssh-keygen -t rsa`.

  * **MS-Windows**: Open the tool PuTTYgen from the Start menu
    1. Choose "SSH-2 RSA" in the bottom and click on `Generate`.
    2. Click on the "Save private key" button to save the *Private key* in a file called ClePriv-PUTTY on the Desktop.
  This file will be used to SSH-connect to your VM with PuTTY. Add it to the PuTTY configuration in the field at
  "Connection->SSH->Auth-> Private key file for authetincation".
    3. Do also menu "Conversions -> Export OpenSSH key", and save it in a file called ClePriv-SSH, also on the Desktop.
  You will need it to connect with the X2Go tool to access a remote dekstop of a VM.
    4. And finaly copy the PubKey from the "Public Key for pasting into OpenSSH (...)" at the top of the window.
  You can then copy it in the SSH PubKey field of your Biosphere account parameters.

4. Paste your SSH PubKey (public key) in the related field. You can paste several PubKey but
**be careful that each PubKey is on one line only**
