## Connexion à vos machines virtuelles

Il existe différentes manières d'interagir avec vos machines virtuelles (VM) :

1. avec une **interface web** (HTTP) avec des apps cloud compatibles, par exemple RStudio, Jupyter Notebooks ;
2. avec l'**interface de ligne de commande SSH** (CLI) via une fenêtre de terminal ;
3. avec un **bureau graphique distant** (X2Go ou VNC).

Une fois que le déploiement de votre VM est terminé avec succès, vous pouvez obtenir tous les paramètres de connexion dans la colonne « Accès » de l'onglet [**myVM**](https://biosphere.france-bioinformatique.fr/cloud) du portail Biosphere.

Vous trouverez le lien HTTP/S (si disponible) vers votre VM, ou les paramètres SSH (`nom d'utilisateur` et `adresse IP`) à utiliser pour vous connecter à votre VM.

### 1. Connexion à une VM avec une interface web

Cliquez simplement sur le lien **HTTPS** pour être redirigé vers le portail web fourni par votre VM. Si vous êtes invité à fournir le `nom d'utilisateur` et le `mot de passe`, ou le `jeton d'accès`, ils sont fournis via le champ « Paramètres » de la colonne « Accès ». Ces paramètres de sécurité sont uniques pour votre VM et ne sont connus que de vous (et, bien sûr, des administrateurs de votre groupe et du site cloud pour des raisons opérationnelles).

### 2. Connexion à une VM avec SSH

Un client SSH est installé par défaut sur tout ordinateur équipé de Linux (CentOS, Ubuntu, Debian, ...), MacOS ([doc](https://support.apple.com/fr-gq/guide/terminal/apd5265185d-f365-44cb-8b09-71a064a42125/mac)) et MS Windows 10 (et versions ultérieures).

À partir de la version MS Windows 10, vous pouvez utiliser à la fois

* PowerShell ([doc](https://docs.microsoft.com/fr-fr/powershell/scripting/learn/ps101/01-getting-started?view=powershell-7.2#where-do-i-find-powershell))
* et le sous-système Linux pour Windows (WSL) basé sur Ubuntu ([doc](https://docs.microsoft.com/fr-fr/windows/wsl/install-win10)).

#### Configuration des paramètres SSH dans votre profil Biosphere

Tout d'abord, vous devez **configurer vos paramètres SSH avant de créer une VM avec un accès SSH**.

En effet, votre clé publique SSH sera importée dans votre VM lors de sa création et ne pourra pas être modifiée par la suite.

##### 1. Obtenir votre clé publique SSH

Ouvrez une fenêtre de terminal (Linux, MacOS) ou PowerShell (MS Windows) et tapez la commande suivante.

```
cat $HOME/.ssh/id_rsa.pub
```

Si la réponse est vide, vous n'avez pas encore de paire de clés SSH, et vous pouvez en créer une avec la commande suivante.

!!! Warning
    Si vous avez déjà une clé SSH, vous risquez de l'écraser avec cette nouvelle commande.

```
ssh-keygen -t rsa
```

##### 2. Ouvrez la page des paramètres de votre compte

Elle est accessible à partir du menu utilisateur en haut à droite du portail Biosphere [[aller](https://biosphere.france-bioinformatique.fr/cloudweb_account/settings/)].

##### 3. Cliquez sur le bouton Modifier.

##### 4. Copiez votre clé publique dans le champ « Pubkey ».

Vous pouvez coller plusieurs clés publiques, mais assurez-vous que chacune est sur une ligne unique.

#### Ouvrir la connexion SSH vers la VM

Pour vous connecter à une VM avec SSH, vous devez

* ouvrir la page de description de la VM en cliquant sur son lien « ID » dans le tableau de bord Biosphere [**myVM**](https://biosphere.france-bioinformatique.fr/cloud);
* dans la page de la VM, copier la commande « ssh » du tableau « Accès »;
* coller le texte copié dans une fenêtre de terminal (Linux, MacOS) ou PowerShell (MS Windows);
* et appuyer sur Entrée.

La connexion sera établie en fonction de la clé publique SSH que vous avez configurée dans votre profil (voir ci-dessus).

Vous pouvez également cliquer sur le lien « ssh » dans le tableau de bord Biosphere pour ouvrir une nouvelle fenêtre de terminal avec une connexion SSH automatique à votre VM.
_(Cela ne fonctionnera qu'avec MacOS et la plupart des distributions Linux.)_

### 3. Connexion à une VM avec un bureau graphique distant

Vous pouvez vous connecter à une VM avec un bureau virtuel de deux manières différentes, avec X2Go ou avec VNC.

L'ouverture d'un bureau distant nécessite

* d'avoir configuré vos paramètres SSH (voir ci-dessus),
* et d'avoir installé le client X2Go ou VNC et ses dépendances (voir ci-dessous).

!!! Avertissement
    Avec les versions récentes d'Ubuntu, il existe un bug connu avec le bureau distant X2Go lié à la compatibilité du serveur X2Go avec la bibliothèque GLX.

Donc si vous rencontrez des problèmes avec X2Go, vous devriez préférer une connexion avec VNC.

#### Connexion à un bureau virtuel avec X2Go

##### 1. Installez le client X2Go
[Instructions d'installation X2Go - Chapitre Client X2Go](https://wiki.x2go.org/doku.php/download:start).

##### 2. Installez le logiciel X server

* [MacOS] : Xquartz (https://www.xquartz.org/)
* [MS Windows 10] : VcXsrv (https://sourceforge.net/projects/vcxsrv) ou Xming (https://sourceforge.net/projects/xming/)

_Les distributions Linux ont généralement un serveur X installé par défaut._

##### 3. Ouvrir la connexion au bureau distant de la VM

Vous pouvez obtenir les paramètres de connexion de la VM dans les champs « Paramètres » de la colonne « Accès » (dans l'onglet [**myVM**](https://biosphere.france-bioinformatique.fr/cloud)) :

* `nom d'utilisateur`
* `adresse IP/nom d'hôte` de la VM
* `type de session` (généralement XFCE)

Ensuite, vous les utiliserez pour configurer une session dans le client X2Go (voir [Instructions d'utilisation X2Go](https://wiki.x2go.org/doku.php/doc:usage:x2goclient)). Et n'oubliez pas de cocher la case « Authentification automatique (avec agent SSH ou clé par défaut) ».

#### Connexion à un bureau virtuel avec VNC

Vous pouvez utiliser n'importe quel client VNC, par exemple le client TigerVNC (https://tigervnc.org)

_[Télécharger la dernière version](https://sourceforge.net/projects/tigervnc/files/stable/)_

##### 1. Connectez-vous à votre VM avec SSH

`ssh -L 5901:localhost:5901 ubuntu@<vm-ip>`

_(Valable pour les VM Ubuntu, remplacez `ubuntu` par `debian` ou `rocky` selon la VM que vous utilisez)_

##### 2. Une fois connecté à votre VM, lancez le serveur VNC

`vncserver -localhost yes -autokill no -SecurityTypes None`

##### 3. Vérifiez que le service est en cours d'exécution

`vncserver -list`

##### 4. Connectez-vous au bureau

Sur votre ordinateur local, ouvrez le client TigerVNC et remplissez la fenêtre avec le paramètre « Serveur VNC » avec la valeur `localhost:5901`.