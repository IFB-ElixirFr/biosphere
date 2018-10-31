## Welcome to Biosphere - IFB Clouds Federation for Life Science

Biosphere provides multi-cloud deployment that help for example to combine larger CPU resources, to use different data sources, and to guarantee the availability of cloud resources. Biosphere is used for scientific production in the life sciences, developments, and also to support events like cloud and scientific training sessions, hackathons or workshops.

The Biosphere portal provides different high-level cloud interfaces to analyze your data:

* The [RAINBio](https://biosphere.france-bioinformatique.fr/catalogue) catalogue to select the bioinformatics cloud appliances, useful for your analysis,
* An operating center (tab [myVM](https://biosphere.france-bioinformatique.fr/cloud)) to manage your cloud deployments with single virtual machines (VM) or complex applications with multiple VM
* A [data center](https://biosphere.france-bioinformatique.fr/catalogue/data) where you will find common public data available in the clouds.

To use the clouds of IFB-Biosphere, you need to ask for an account, and get membership of an active group. Then, you will need to set up your personnal parameters. And finally, you are ready to launch your virtual machines (VM) from the RAINBio catalogue.

*N.B.: To use the IFB clouds, you will need at least a recent Web browser to access the Biosphere portal, and your VM providing a web interface*

### Sign in

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

### Deploy your virtual machines (VM)

Pre-defined bioinformatics environment ('appliances') are available from the [RAINBio](https://biosphere.france-bioinformatique.fr/catalogue) catalogue. You can from there deploy your virtual environment with a single VM or several. To identify the relevant appliances, you can filter the available ones with keywords, name of tools, topics,...

Each appliance is shortly described in a box with the list of tools and topics associated to it. There are also several actions directly usable through the following icons:
- 'star': to record it in your favorites,
- 'lightning': to start it quickly with default parameters (default cloud, default size),
- 'wrench': to configure your deployment, for example to change the used cloud and the size of the VM,
- '+': to display an detailled view of the appliance (you can also click on the name of the appliance).

### Connect to your virtual machines

Once the deployment of your VM is done successfully, you can get all info from the **myVM** tab of the biosphere portal
[[go](https://biosphere.france-bioinformatique.fr/cloud)]. Especially, the column Access will show you howto connect to your VM

* **http**: click on the link to go on the web portal provided by your VM.

* **ssh**: click on the link to connect by SSH to to your VM, or copy-paste the link in a terminal. Be sure to have set up your SSH PubKey before creating the VM, as explained in the chapter about setting your SSH parameters.

These SSH instruction is valid only for Linux and MacOS computers. For Windows PC, you will need to to copy the IP/hostname of your VM (click on the question mark to get it), and paste it in the configuration of the PuTTY tool:
  * in the field "Session -> HostName (orIP address)"
  * and select "SSH" for the "Connection type"


*Software requirements*

To connect to your VM with the Linux command line interface (CLI), you will do it with a secure shell (SSH), and require an SSH client.
Such software tool is installed by default in any computer using Linux (CentOS, Ubuntu, Debian,...) or MacOS.
But for Microsoft Windows computer, you will need to install the tool PuTTY available from its web site [PuTTY web site](http://www.putty.org/),
where you will find also the download and installation instructions. Take care to use the MSI (‘Windows Installer’). 


#### Setting your SSH parameters

To configure your SSH parameters:

1. Open your account parameters page from the user menu in the top-right corner of the Biopshere portal
[[go](https://biosphere.france-bioinformatique.fr/cloudweb_account/settings/)].

2. Click the Edit button

3. Paste your SSH PubKey (public key) in the related field. You can paste several PubKey but
**be careful that each PubKey is on one line only**

You can find your SSH PubKey from

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



### Current infrastructure

Biosphere already gathers five academic clouds deployed in regional IFB platforms:
* [IFB-core](https://www.france-bioinformatique.fr/fr/core)
* [GenOuest](https://www.france-bioinformatique.fr/fr/plateformes/genouest)
* [PRABI-LBBE](https://www.france-bioinformatique.fr/fr/plateformes/prabi-doua)
* [BiRD](https://www.france-bioinformatique.fr/fr/plateformes/bird)
* [BIstrO](https://www.france-bioinformatique.fr/fr/plateformes/bistro)

You can follow the current status of the infrastructure on the [Support page](https://biosphere.france-bioinformatique.fr/cloud/system_status) of the Biosphere portal.

Other clouds are under deployment and will be added to the federation once operationnal: [GenoToul-Bioinfo](https://www.france-bioinformatique.fr/fr/plateformes/genotoul), [RPBS](https://www.france-bioinformatique.fr/fr/plateformes/rpbs), [PSMN ENSL-Lyon](http://www.ens-lyon.fr/PSMN/doku.php).
