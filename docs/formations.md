L'IFB soutient les formations (cursus universitaires, écoles scientifiques, formations permanentes, workshops, hackathons...) par la fourniture de l’infrastructure bio-informatique et informatique avec des machines virtuelles dédiées, et par une assistance pour la préparation de l’environnement logiciel.

**Note importante :**
Différentes constatations environnementales (préservation des ressources) ou économiques (coût de l’électricité) nous amènent à réfléchir sur notre usage du numérique. C'est pourquoi nous vous demandons de privilégier nos gabarits dédiés aux VMs de formation. Ces gabarits (‘ifb.tr.xxxx’, ’tr’ pour « training ») sont moins chargés en mémoire avec un ratio de 1 coeur pour 1 Go de RAM. Cela permet de mettre plus de VMs par serveur physique et donc de moins consommer d’électricité. 
```
ifb.tr.small (1c 1Go)
ifb.tr.medium (2c 2Go)
ifb.tr.large (4c 4Go)
ifb.tr.xlarge (8c 8Go)
ifb.tr.2xlarge (16c16Go)
```

En effet, on ne peut pas proposer plus de RAM dans les VMs que celle disponible sur le serveur physique, alors que pour les CPUs virtuels il est possible d’allouer 3 ou 4 fois plus que la taille des CPUs physiques. Or, dans les clouds IFB-Biosphère, les gabarits proposés pour les VMs ont été calibrés pour un usage intensif. C’est pourquoi le ratio est généralement équivalent à 1 coeur de calcul (1c) pour 4 Go de RAM.

Les VMs déployées lors d’une formation ne sont pas forcément utilisées en permanence (étape de préparation, inter-cours…). Ainsi, lorsqu’un serveur est occupé par un grand nombre de VMs de formation, la taille totale en RAM est saturée mais pas les CPUs. **Or un serveur qui ne calcule pas consomme malgré tout la moitié de sa consommation électrique maximale**.

## Création d'un groupe dédié à la formation 

La **première étape consiste à remplir une demande d'appui** pour cette formation dans le portail Biosphère avec ce 
[formulaire](https://biosphere.france-bioinformatique.fr/cloudweb_account/groups/create?type_of_group=2). La personne demandant le soutien devra également avoir un compte valide dans le cloud IFB, et avoir rejoint le groupe de son affiliation principale.
 
Un groupe correspondant à cette formation sera créé dans Biosphère, et des ressources seront allouées (vCPU, RAM, stockage) en fonction de vos besoins et des ressources disponibles sur l'infrastructure.

Les formateurs et élèves pourront sélectionner ce groupe pour le déploiement des machines virtuelles (VMs) relatives à cette formation (dans *Déploiement avancé*, ou le définir par défaut dans leur profil).

## Fonctionnalités pour les formateurs

Les formateurs, que vous aurez indiqués, seront administrateurs de ce groupe et pourront valider les élèves et gérer leurs VMs.

Les formateurs recevront pour chaque demande d'adhésion au groupe formation une notification par email et pourront valider les nouveaux comptes dans le portail Biosphère. Ces comptes élèves seront désactivés automatiquement à la fin de la formation.

Les formateurs pourront voir et gérer les VMs des élèves dans le tableau de bord du portail Biosphère (page [myVM - Tout voir](https://biosphere.france-bioinformatique.fr/monitor)), par exemple pour les supprimer à la fin de la formation si l’élève ne l’a pas fait.

## Fonctionnalités pour les élèves

Les élèves pourront demander un compte cloud avec leurs identifiants académiques (par exemple de leur université ou de leur organisme de recherche), et leur adhésion au groupe de la formation.

Chaque élève pourra avec son compte déployer ses propres VMs suivant ses besoins et les recommandations des enseignants, en choisissant la taille de ses VMs suivant les ressources disponibles sur les sites de l'infrastructure. Cela peut être 1 CPU et 4 Go de RAM pour un premier exercice, puis 16 vCPUs et 64 Go RAM lors d’exercices plus gourmands. 

## Des environnements dédiés

Les VMs des élèves seront construites automatiquement avec les modèles existants dans notre [catalogue RAINBio](https://biosphere.france-bioinformatique.fr/catalogue), ou avec un nouveau modèle défini pour la formation.

Les environnements disponibles vont d'un serveur linux de base (ubuntu, debian, centos) à des environnements plus complets avec des gestionnaires de workflows (Nextflow, Snakemake, CWLtool), un bureau graphique à distance ou des interfaces web (Jupyter, Rstudio/Shiny …).

Pour la création d'une nouvelle appliance cloud dans le catalogue RAINBio, contactez-nous sur notre [adresse support](mailto:biosphere-support@genouest.org), nous pouvons vous aider.

## Une infrastructure distribuée et redondante

L’infrastructure cloud comprend plusieurs sites avec des ressources matérielles différentes qui vous permettent : 
1. de basculer sur un autre site en cas de défaillance d’un des sites le jour de la formation,
2. de trouver des ressources spécifiques comme par exemple des VMs avec beaucoup de mémoire ou des processeurs plus rapides.

La liste des sites et leurs ressources sont visibles sur le portail Biosphère dans la page d'[état du système](https://biosphere.france-bioinformatique.fr/cloud/system_status).


