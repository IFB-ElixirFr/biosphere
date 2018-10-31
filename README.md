## Welcome to Biosphere - IFB Clouds Federation for Life Science

Biosphere provides multi-cloud deployment that help for example to combine larger CPU resources, to use different data sources, and to guarantee the availability of cloud resources. Biosphere is used for scientific production in the life sciences, developments, and also to support events like cloud and scientific training sessions, hackathons or workshops.

The Biosphere portal provides different high-level cloud interfaces to analyze your data:

![Biosphere portal top banner](https://raw.githubusercontent.com/IFB-ElixirFr/biosphere/master/assets/img/biosphere-portal-top.png)

* [1] The [RAINBio](https://biosphere.france-bioinformatique.fr/catalogue) catalogue to select the bioinformatics cloud appliances, useful for your analysis,
* [2] An operating center (tab [myVM](https://biosphere.france-bioinformatique.fr/cloud)) to manage your cloud deployments with single virtual machines (VM) or complex applications with multiple VM
* [3] A [data center](https://biosphere.france-bioinformatique.fr/catalogue/data) where you will find common public data available in the clouds.

To use the clouds of IFB-Biosphere, you need to ask for an account, and get membership of an active group. Then, you will need to set up your personnal parameters [5]. And finally, you are ready to launch your virtual machines (VM) from the RAINBio catalogue.

You can get the **current status and usage** of the infrastructure from the Support menu [4]. Biosphere already gathers five academic clouds deployed in regional IFB platforms:
[IFB-core](https://www.france-bioinformatique.fr/fr/core),
[GenOuest](https://www.france-bioinformatique.fr/fr/plateformes/genouest),
[PRABI-LBBE](https://www.france-bioinformatique.fr/fr/plateformes/prabi-doua),
[BiRD](https://www.france-bioinformatique.fr/fr/plateformes/bird),
[BIstrO](https://www.france-bioinformatique.fr/fr/plateformes/bistro).
Other clouds under deployment will be added to the federation once operationnal: [GenoToul-Bioinfo](https://www.france-bioinformatique.fr/fr/plateformes/genotoul), [RPBS](https://www.france-bioinformatique.fr/fr/plateformes/rpbs), [PSMN ENSL-Lyon](http://www.ens-lyon.fr/PSMN/doku.php).

## Sign in

Go to the menu Sign-in in the top-right corner of the main page of the Biopshere portal [[go](https://biosphere.france-bioinformatique.fr/cloudweb/login/?next=/)], and follow the guidelines.
We advise to use your federated identity in eduGAIN where most of European universities and academic organisms are registered ([more details about eduGAIN there](https://edugain.org)).
It will fill automatically your email address and other personnal information that you authorised to transmit. 

In case your institution is not registered in eduGAIN, you can ask for a local Biosphere account. But then you will have to fill the required information by hand.
Take care of the email address you enter because it will be use to contact you for any inquiry or announcement related to IFB-Biosphere.
For example, at the second step of the account request, an email message will be sent to this email address to validate it.  
In case you have not anymore access to this email address, we will not be able to join you or help you to keep access to your IFB-Biosphere cloud account.

Once your email have been validated, you will be asked to apply to join an affiliation [[go](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups/add)]. If your affiliation is not already registered, you may ask to create it.

Both your request for an account and for the membership to an affiliation will be evaluate by the IFB committee before validation.
Take care when you fill these two steps because it will help to keep the validation process going. In case of a clarification need, you will be contacted on the email address you enter. 

## Deploy your virtual machines (VM)

Pre-defined bioinformatics environment ('appliances') are available from the [RAINBio](https://biosphere.france-bioinformatique.fr/catalogue) catalogue. You can from there deploy your virtual environment with a single VM or several. To identify the relevant appliances, you can filter the available ones with keywords, name of tools, topics,...

Each appliance is shortly described in a box, like in the following example. The list of integrated tools and associated topics are summarized in the box [4]. There are also several actions directly usable through the following icons:

![Biosphere portal RAINBio box example](https://github.com/IFB-ElixirFr/biosphere/raw/master/assets/img/rainbio-box.png)

- [1] 'star': to record it in your favorites,
- [2] 'lightning': to start it quickly with default parameters (default cloud, default size),
- [3] 'wrench': to configure your deployment, for example to change the used cloud and the size of the VM,
- [5] '+': to display an detailled view of the appliance (you can also click on the name of the appliance).

## Connect to your virtual machines

There are different way to connect to virtual machines: command line interface (CLI) with SSH tool, web interface (HTTP) or remote graphical desktop (X2Go). Once the deployment of your VM is done successfully, you can get all access infromations from the **myVM** tab of the biosphere portal
[[go](https://biosphere.france-bioinformatique.fr/cloud)], where the column **Access** provides you with details.

### Connect to the web interface of VMs

Simply click on the **http** link to be redirected to the web portal provided by your VM.

### Connect with SSH of VMs

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

3. Getting your SSH PubKey:

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
