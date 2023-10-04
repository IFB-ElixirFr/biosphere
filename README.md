## Welcome to Biosphere - IFB Clouds Federation for Life Science

**French Institute of Bioinformatics - IFB** is providing cloud services to analyze life science data.
These services rely on a federation of clouds - **Biosphere** - built on interconnected IT infrastructures of some IFB’s platforms, 

Biosphere provides multi-cloud deployments to increase the availability of cloud resources, to propose larger CPU resources or different hardwares (GPU, big memory, high-frequency CPU), or to use different data sources. Biosphere is used for scientific production in the life sciences, developments, and to support events like scientific training and schools, university courses, hackathons or workshops.

The Biosphere portal provides different high-level cloud interfaces to analyze your data:

![Biosphere portal top banner](https://raw.githubusercontent.com/IFB-ElixirFr/biosphere/master/assets/img/biosphere-portal-top.png)

* [1] The [RAINBio](https://biosphere.france-bioinformatique.fr/catalogue) catalogue to select the bioinformatics cloud appliances, useful for your analysis,
* [2] An operating center (tab [myVM](https://biosphere.france-bioinformatique.fr/cloud)) to manage your cloud deployments with single virtual machines (VM) or complex applications with multiple VM,
* [3] A [data center](https://biosphere.france-bioinformatique.fr/catalogue/data) where you will find common public data available in the clouds.

To use the clouds of IFB-Biosphere, you need to ask for an account, and get membership of an active group (see `Signing in`). Then, you will need to set up your personnal parameters [5]. And finally, you are ready to launch your virtual machines (VM) from the RAINBio catalogue.

The Support menu [4] provides the **current status and usage** of the whole infrastructure and the **contact email address** to get help in case of troubles.

**Biosphere federates 8 academic clouds** deployed in regional IFB platforms:
[IFB-core](https://www.france-bioinformatique.fr/fr/core),
[GenOuest](https://ressources.france-bioinformatique.fr/fr/plateformes/genouest),
[PRABI-LBBE](https://ressources.france-bioinformatique.fr/fr/plateformes/prabi-doua),
[BiRD](https://ressources.france-bioinformatique.fr/fr/plateformes/bird),
[BIstrO](https://ressources.france-bioinformatique.fr/fr/plateformes/bistro),
[Bilille](https://ressources.france-bioinformatique.fr/fr/plateformes/bilille),
[PSMN ENSL-Lyon](http://www.ens-lyon.fr/PSMN/doku.php),
[AuBi](https://ressources.france-bioinformatique.fr/fr/plateformes/aubi).

## Project layout

```bash
    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
```

## For collaborators and developers

This part is for collaborators and developers.

### Modify content

When you are in the repository, add and/or modify your markdown tutorials in the docs directory. The arborescence of the website menu is to setup in the mkdocs.yml file.

### Mkdocs

To work locally with this project, you'll have to follow the steps below:

1. Fork, clone or download this project
2. Create and activate conda env

```bash
cd biosphere
conda env create -f env_docs.yml
conda activate docs
```

3. Preview your project

```bash
mkdocs serve
```

Note : *The site can be accessed under http://localhost:8000/*

4. Add content

Add/update markdown files in docs folder

5. Test

```bash
mkdocs build
```

6. Deploy

**Only if previous command is Ok !**

```bash
mkdocs gh-deploy --force
```

If you add an extension to (Material) MKdocs that requires the installation of a new package.
Don't forget to export the conda environment (env_docs.yml) using the command line below.

```bash
conda env export --no-builds env_docs.yml
```

Read more at:

- MkDocs [documentation](https://www.mkdocs.org/)
- Mkdocs Material [documentation](https://squidfunk.github.io/mkdocs-material/)


## Acknowledgement

- All contributors

## Ressources

### mkdocs

- Official documentation : https://www.mkdocs.org/
- Material (best extension !) : https://squidfunk.github.io/mkdocs-material/
- Multi language structure : https://github.com/squidfunk/mkdocs-material/discussions/2346
