The IFB supports research projects (regional, ANR, European, etc.) by providing bioinformatics and IT infrastructure with dedicated virtual machines, as well as assistance in implementing software environments.

!!! Warning "IMPORTANT!"
    The IFB cloud is currently available only for analysis purposes and not for permanent data storage. In this sense, it is neither backed up nor guaranteed against misuse or system crashes.

    The IFB cloud is not authorized to host health data (HDS), industrial or more broadly sensitive and confidential data of high importance.

## Setting up a project group

The **first step is to fill out a support request** for this project on the Biosphere portal using this 
[form](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups/create?type_of_group=3).

!!! Warning
    **This request must be submitted by the project’s administrative lead (ANR project holder, team leader, supervisor, etc.). The project lead must also have a valid account in the IFB cloud and have joined the group corresponding to their main affiliation.**

The project request will be reviewed by the IFB. Based on the decision of the evaluation committee, the allocated resources and the terms of support will be communicated to you. Resource support may take several forms:
- provided by one of the platforms participating in the infrastructure under their resource envelope,
- as part of a scientific collaboration,
- billed on an invoicing basis.

A group corresponding to this training will be created in Biosphere, and **resources (vCPU, RAM, storage) will be allocated** according to your stated needs and the committee’s decision.

## Features for project leads

Project leads, as specified in the request, will be administrators of the project group. They will have the ability to approve membership requests and monitor all virtual machines (VMs) associated with the project.

Project leads will receive an email notification for each membership request and will be able to approve new accounts within the Biosphere portal. Accounts linked to the project will be automatically deactivated at the end of the project.

Project leads can monitor and manage the project’s environments and VMs through the Biosphere portal dashboard (page [on the myVM - View All page](https://biosphere.france-bioinformatique.fr/monitor)), including the option to delete VMs when necessary.

Resource consumption by project members and their VMs will be attributed to the project. A daily updated record of current consumption is available on the project page in the Biosphere portal.

## Features for project members

Project members can request to join the project group from the [corresponding page](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups) on the  Biosphere portal. They must first request a Biosphere cloud account using their academic credentials (e.g., from their university or research organization).

Each member, with their account, will be able to deploy their own analysis environments and VMs according to their needs, the project recommendations, and the resources available on the infrastructure sites.

## Dedicated Environments

Project members' environments and VMs are automatically built based on existing models in the [RAINBio catalog](https://biosphere.france-bioinformatique.fr/catalogue), or a new model specifically defined for the project.

Available environments range from a basic Linux server (Ubuntu, Debian, CentOS) to more advanced setups featuring workflow managers (Nextflow, Snakemake, CWLtool), remote graphical desktops, or web-based interfaces (Jupyter, RStudio/Shiny, etc.).

For the creation of a new cloud appliance dedicated to your project, feel free to contact us on our [helpdesk](https://biosphere-support.genouest.org), we will be happy to assist you.

## A distributed and redundant infrastructure

The IFB-Biosphere cloud infrastructure includes multiple sites with different hardware resources, allowing you to: 

 1. find resources scaled to your needs,
 2. access specialized resources, such as high-memory VMs (`BigMem`) or high-frequency processors (`HighFreq`),
 3. switch to an available site in case of a failure at one of the locations.

!!! Note

    The list of sites and their available resources can be viewed on the Biosphere portal under the system [status page](https://biosphere.france-bioinformatique.fr/cloud/system_status).
