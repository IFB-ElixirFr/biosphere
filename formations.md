L'IFB soutient les formations (cursus universitaires, ecoles scientifiques, formations permanentes, workshops, hackathons...) par la fourniture de l’infractructure bio-informatique et informatique avec des machines virtuelles dédiées, et par une assistance pour la préparation de l’environnement logiciel.

## Création d'un groupe formation dédié à la formation 

Il vous suffit de remplir une demande pour cette formation dans le portail Biosphère :

https://biosphere.france-bioinformatique.fr/cloudweb_account/groups/create?type_of_group=2
 
Un groupe correspondant à cette formation sera créé dans Biosphère, et des ressources seront allouées (vCPU, RAM, stockage) en fonction de vos besoins et des ressources disponibles sur l'infrastructure.

Les formateurs et élèves pourront sélectionner ce groupe lors du déploiement des VMs relatives à cette formation (dans *Déploiement avancé*), ou le définir par défaut dans leur profil.

## Fonctionnalités pour les formateurs

Les formateurs, que vous aurez indiqués, seront administrateurs de ce groupe et pourront valider les élèves et gérer leurs VMs.

Les formateurs recevront pour chaque demande d'adhésion au groupe formation une notification par email et pourront valider les nouveaux comptes dans le portail Biosphère. Ces comptes élèves seront désactivés automatiquement à la fin de la formation.

Les formateurs pourront voir et gérer les VMs des élèves dans le tableau de bord du portail Biosphère (page « myVM »), par exemple pour les arrêter à la fin de la formation si l’élève ne l’a pas fait.

## Fonctionnalités pour les élèves

Les élèves pourront demander un compte cloud avec leurs identifiants académiques (par exemple de leur université ou de leur organisme de recherche), et leur adhésion au groupe de la formation.

Chaque élève pourra avec son compte déployer ses propres VMs suivant ses besoins et les recommandations des enseignants, en choisissant la taille de ses VMs en fonction de ses besoins. Cela peut être 1 CPU et 4 Go de RAM pour un premier exercice, puis 16 vCPUs et 64 Go RAM lors d’exercices plus gourmands. 

## Des environnements dédiés

Les VMs des élèves seront construites automatiquement avec les modèles existants dans notre catalogue RAINBio (https://biosphere.france-bioinformatique.fr/catalogue), ou avec un nouveau modèle défini pour la formation.

Les environnements disponibles vont d'un serveur linux de base (ubuntu, debian, centos) à des environnements plus complets avec des gestionnaires de workflows (Nextflow, Snakemake, CWLtool), un bureau graphique à distance ou des interfaces web (Jupyter, Rstudio/Shiny …).

Pour la création d'une nouvelle appliance cloud dans le catalogue RAINBio, vous pouvez nous contacter sur notre adresse support (biosphere-support@genouest.org), nous pouvons vous aider.

## Une infrastructure distribuée et redondante

L’infrastructure cloud comprend plusieurs sites qui permettent de pallier une défaillance d’un des sites le jour de la formation.

La liste des sites et leurs ressources sont visibles sur le portail Biopshère : https://biosphere.france-bioinformatique.fr/cloud/system_status


