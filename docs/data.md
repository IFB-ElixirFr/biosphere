## Transferring data with your VM

Cloud appliances providing a **web interface** usually include upload and download features through web forms,
for example RStudio and Jupyter Notebooks.

With appliances providing **SSH-based access** or a **remote graphical desktop**, you can transfer you data
with the usual SSH commands `scp` and `sftp` (see related user manuals and man pages for usage),
or with some graphical tools listed below 
(see each tool User Guide for usage and configuration). They all rely on the SSH protocol and will use the PubKey
you configured in your Biosphere user profile
(*Do not forget to set it up in the configuration parameters of the following graphical tools*).

#### **Linux**
  - FileZilla (https://filezilla-project.org)

#### **MacOS**
  - CyberDuck (https://cyberduck.io)
  - Transmit (https://panic.com/transmit/
  - FileZilla (https://filezilla-project.org)

#### **MS-Windows**:
  - FileZilla (https://filezilla-project.org)
  - MobaXterm (https://mobaxterm.mobatek.net)
  - the embedded Ubuntu available from Windows 10 [[details](https://docs.microsoft.com/en-us/windows/wsl/install-win10)]
