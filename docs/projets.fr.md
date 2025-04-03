L'IFB soutient les projets de recherche (régionaux, ANR, Europe...) par la fourniture de l’infrastructure bio-informatique et informatique avec des machines virtuelles dédiées, et par une assistance pour la mise en oeuvre des environnements logiciels.

## Création d'un groupe projet 

La **première étape consiste à remplir une demande d'appui** pour ce projet dans le portail Biosphère avec ce 
[formulaire](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups/create?type_of_group=3).

!!! Warning "Attention"
    **Cette demande doit être faite par la/le responsable administratif du projet (porteur du projet ANR, chef d'équipe,
    responsable du stage...). La personne responsable du projet devra également avoir un compte valide dans le cloud IFB, et avoir rejoint le groupe de son affiliation principale.**

La demande de projet sera étudiée par l'IFB. En fonction de la décision du comité d'évaluation, les ressources attribuées et les modalités de prise en charge vous seront communiquées. La prise en charge des ressources pourra être de plusieurs types :
- par une des plateformes participant à l'infrastructure sur son enveloppe de ressources,
- dans le cadre d'une collaboration scientifique,
- sur facturation.

Un groupe correspondant à cette formation sera créé dans Biosphère, auquel des **ressources seront allouées (vCPU, RAM, stockage)** en fonction de vos besoins exprimés et de la décision du comité d'évaluation.

## Fonctionnalités pour les responsables du projet

Les responsables de projet, tels qu'indiqués dans la demande, seront administrateurs de ce groupe. Ils pourront valider les demandes d'adhésion des membres et monitorer toutes les machines virtuelles (VMs) du projet.

Les responsables de projet recevront pour chaque demande d'adhésion au groupe projet une notification par email et pourront valider les nouveaux comptes dans le portail Biosphère. Les comptes liés au projet seront désactivés automatiquement à la fin du projet.

Les responsables de projet peuvent monitorer et gérer les environnements et VMs du projet dans le tableau de bord du portail Biosphère (page [myVM - Tout voir](https://biosphere.france-bioinformatique.fr/monitor)), par exemple pour les supprimer lorsque c'est nécessaire.

La consommation des ressources par les membres et leurs VMs seront imputées au projet. Un relevé de la consommation courante est mis à jour quotidiennement, et disponible dans la page du projet sur le portail Biosphère.

## Fonctionnalités pour les membres du projet

Les membres du projet peuvent demander à rejoindre le groupe projet depuis la [page correspondante](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups) sur le portail Biosphère. Ils doivent au préalable avoir demandé un compte cloud Biosphère avec leurs identifiants académiques (par exemple de leur université ou de leur organisme de recherche).

Chaque membre pourra avec son compte déployer ses propres environnements d'analyse et VMs suivant ses besoins, les recommandations du projet et les ressources disponibles sur les sites de l'infrastructure.

## Des environnements dédiés

Les environnements et VMs des membres du projet sont construits automatiquement d'après les modèles existants dans le [catalogue RAINBio](https://biosphere.france-bioinformatique.fr/catalogue), ou avec un nouveau modèle défini pour le projet.

Les environnements disponibles vont d'un serveur linux de base (ubuntu, debian, centos) à des environnements plus complexes avec des gestionnaires de workflows (Nextflow, Snakemake, CWLtool), un bureau graphique à distance ou des interfaces web (Jupyter, Rstudio/Shiny …).

Pour la création d'une nouvelle appliance cloud dédiée au projet, contactez-nous sur notre [adresse support](mailto:biosphere-support@genouest.org), nous pouvons vous aider.

## Une infrastructure distribuée et redondante

L’infrastructure cloud IFB-Biosphère comprend plusieurs sites avec des ressources matérielles différentes qui vous permettent : 
1. de trouver des ressources de taille adaptée à vos besoins,
2. ou des ressources spécifiques comme, par exemple, des VMs avec beaucoup de mémoire (`BigMem`) ou des processeurs plus rapides (`HighFreq`),
3. de basculer sur un site disponible en cas de défaillance d’un des sites.

!!! Note

    La liste des sites et leurs ressources disponibles sont visibles sur le portail Biosphère dans la page d'[état du système](https://biosphere.france-bioinformatique.fr/cloud/system_status).
