IFB supports training initiatives (university programs, scientific schools, continuing education, workshops, hackathons, etc.) by providing bioinformatics and computing infrastructure, including dedicated virtual machines and offering assistance in setting up the software environment.

!!! Warning "Important Note"

    Various environmental (resource conservation) and economic (electricity costs) considerations lead us to rethink our use of digital resources. That’s why we ask you to prioritize our dedicated training VM templates. These templates (‘ifb.tr.xxxx’, where ‘tr’ stands for "training") are designed with a lower memory footprint, following a ratio of 1 core per 1 GB of RAM. This allows more VMs to run on a single physical server thereby reducing electricity consumption.

```
ifb.tr.small (1c 1Go)
ifb.tr.medium (2c 2Go)
ifb.tr.large (4c 4Go)
ifb.tr.xlarge (8c 8Go)
ifb.tr.2xlarge (16c16Go)
```

Indeed, we cannot allocate more RAM to VMs than what is physically available on the server whereas for virtual CPUs it is possible to allocate 3 to 4 times the number of physical CPUs. However, in the IFB-Biosphere clouds, the VM templates have been designed for high-performance usage. This is why the typical ratio is set to 1 computing core (1c) per 4 GB of RAM.

Training VMs are not necessarily used continuously (e.g., during preparation or between courses). As a result, when a server hosts a large number of training VMs, the total RAM may be saturated, but the CPUs are not fully engaged. **Nevertheless, even if a server is not actively processing, it still consumes about half of its maximum electrical power.**

## Creation of a dedicated training group

The first step is to submit a support request for this training through the Biosphère portal using this
[form](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups/create?type_of_group=2). The person requesting support must also have a valid account in the IFB cloud and have joined the group corresponding to their primary affiliation.

A group corresponding to this training will be created in Biosphère, and resources (vCPU, RAM, storage) will be allocated based on your needs and the available resources on the infrastructure.

Instructors and students will be able to select this group for deploying the virtual machines (VMs) related to this training (**in Advanced Deployment** or set it as the default in their profile).

## Features for instructors

The instructors you specify will be administrators of this group and will be able to validate students and manage their VMs.

Instructors will receive an email notification for each group training membership request and will be able to approve new accounts in the Biosphère portal. These student accounts will be automatically deactivated at the end of the training.

Instructors will be able to view and manage students' VMs through the Biosphère portal dashboard (page [myVM - View All](https://biosphere.france-bioinformatique.fr/monitor)), for example, to delete them at the end of the training if the student has not done so.

## Features for Students

Students will be able to request a cloud account using their academic credentials (e.g., from their university or research organization) and join the training group.

Each student, with their account, can deploy their own VMs based on their needs and the instructors' recommendations, choosing the size of their VMs according to the available resources on the infrastructure sites. For example, they might start with 1 CPU and 4 GB of RAM for an initial exercise, and then scale up to 16 vCPUs and 64 GB of RAM for more resource-intensive exercises.

## Dedicated environments

The students' VMs will be automatically built using existing templates from our [RAINBio catalog](https://biosphere.france-bioinformatique.fr/catalogue), or with a new model specifically designed for the training.

The available environments range from a basic Linux server (Ubuntu, Debian, CentOS) to more comprehensive setups, including workflow managers (Nextflow, Snakemake, CWLtool), remote graphical desktops, or web interfaces (Jupyter, RStudio/Shiny, etc.).

If you need to create a new cloud appliance in the RAINBio catalog, feel free to contact us at our [support address](mailto:biosphere-support@genouest.org), we are happy to assist you.

## A distributed and redundant infrastructure

The cloud infrastructure includes several sites with different hardware resources, allowing you to:
1. switch to another site in case of failure of one of the sites on the day of the training,
2. find specific resources, such as VMs with more memory or faster processors.

The list of sites and their resources can be viewed on the Biosphere portal under the system status [page](https://biosphere.france-bioinformatique.fr/cloud/system_status).