## Welcome to Biosphere - IFB Cloud Federation for Life Science

Biosphere provides multi-cloud deployment that help for example to combine larger CPU resources, to use different data sources, and to guarantee the availability of cloud resources. Biosphere is used for scientific production in the life sciences, developments, and also to support events like cloud and scientific training sessions, hackathons or workshops.

The Biosphere portal provides different high-level cloud interfaces to analyze your data:

* The [RAINBio](https://biosphere.france-bioinformatique.fr/catalogue) catalogue to select the bioinformatics cloud appliances, useful for your analysis,
* An operating center (tab [myVM](https://biosphere.france-bioinformatique.fr/cloud)) to manage your cloud deployments with single virtual machines (VM) or complex applications with multiple VM
* A [data center](https://biosphere.france-bioinformatique.fr/catalogue/data) where you will find common public data available in the clouds.

### Using the cloud

First, you have to ask an account. 

#### Sign in

Go to the menu Sign-in in the top-right corner of the main page of the Biopshere portal [[go](https://biosphere.france-bioinformatique.fr/cloudweb/login/?next=/)], and follow the guidelines.
We advise to use your federated identity in eduGAIN where most of European universities and academic organisms are registered ([more details about eduGAIN there](https://edugain.org)).
It will fill automatically your email address and other personnal information that you authorised to transmit. 

In case your institution is not registered in eduGAIN, you can ask for a local Biosphere account. But then you will have to fill the required information by hand.
Take care of the email address you enter because it will be use to contact you for any inquiry or announcement related to IFB-Biosphere.
For example, at the second step of the account request, an email message will be sent to this email address to validate it.  
In case you have not anymore access to this email address, we will not be able to join you or help you to keep access to your IFB-Biosphere cloud account.

Once your email have been validated, you will be asked to apply to join an affiliation [[go](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups/add)]. If your affiliation is not already registered, you may ask to create it.

Both your request for an account and for the membership to an affiliation will be evalute by the IFB committee before validation.
Take care when you fill these two steps because it will help to keep the validation process going. In case of a clarification need, you will be contacted on the email address you enter. 

#### Software requirements:

To use the IFB cloud, you will need at least a recent Web browser to access the Biosphere portal, and your VM with a web interface

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

* **Linux and MacOS**: in a terminal execute `cat $HOME/.ssh/id_rsa.pub` 

* **MS-Windows**: Open the tool PuTTYgen from the Start menu
  1. Choose "SSH-2 RSA" in the bottom and click on `Generate`.
  2. Click on the "Save private key" button to save the *Private key* in a file called ClePriv-PUTTY on the Desktop.
  3. Do also menu "Conversions -> Export OpenSSH key", and save it in a file called ClePriv-SSH, also on the Desktop.
  You will need to connect with the X2Go tool to acces a remote dekstop of a VM.
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
