# GIT C'EST QUOI ?
Git est système de gestion de versionning, permmettant de suivre les modifications dans les fichiers de n'importe quelle projet. Il permet à plusieurs collaborateurs de collaborer efficacement sur le même projet, surtout projet IT.

## How to install Git ?
- Si vous êtes sur `windows` : Débrouillez-vous seul
- Si vous êtes sur `macOS` : Débrouillez-vous seul aussi
- Si vous êtes sur `Linux` : ok, suivez les instructions suivantes :
1 - Mettre à jour votre paquet d'abord
```bash
sudo apt update
```
2 - Installer git maintenant
```bash
sudo apt install git
```
De vita ny chocolat

## Il faut le configurer 
Aprè l'installation, il faut que vous configure votre informations d'utilisateur pour que git puisse les utiliser dans vos commits
```bash
git config --global user.name = "Votre Nom"
```
```bash
git config --global user.email = "Votre Email"
```

## Initialisation
Git fonctionne sur un dépôt ou repository en anglais dans lequel git suivra l'évolution de nos fichier.
Imaginons, on créer un simple projet avec dart avec le structure suivante :

<img src="src/structure.png" alt="Texte alternatif" width="250">

Pour initialiser git dans notre projet, il faut qu'on positionne dans le répértoire root de notre projet, et puis :
```bash
git init
```
Cela crée un répertoire .git dans notre dossier, où git stockera les informations sur l'historique des versions :

<img src="src/init.png" alt="Texte alternatif" width="500">

## Suivi d'ajout des fichiers
Git ne suit pas automaquement tous les fichiers dans notre répertoire. On devrait ajouter manuellement les fichiers qu'on souhaite suivre :
```bash
git add nom_du_fichier
```
Pour ajouter tous les fichiers d'un coup
```bash
git add .
```

<img src="src/ajout.png" alt="Texte alternatif" width="500">

## Validation des commit (ou modifications)
Une fois les fichiers ajoutés, on devra `commiter` les changements pour les sauvegarder dans l'historique git :
```bash
git commit -m "Votre message de commit, ici essayer de spécifier ou de quoi vraiment votre modification"
```

## Visualisation des historiques du commit
Pour voir l'historique des changements sauvegarder dans le dépôt :
```bash
git log
```

<img src="src/log.png" alt="Texte alternatif" width="500">

## Travaille avec des branches
Une `branche`c'est quoi ? C'est une version parallèle du p'un projet. Par défaut git commence avec une branche `main` ou `master` . Mais on peut créer d'autres branches pour travailler sur des fonctionnalités et implémentations spécifiques pour les séparer et de les fusionner plus tard.
- pour créer une nouvelle branche :
```bash
git branch nom_du_nouvelle_branche
```
- pour basculer vers une branche
```bash
git checkout nom_du_nouvelle_branche
```
- pour créer et de passer vers une nouvelle branche d'un coup
```bash
git checkout -b nom_du_nouvelle_branche
```

## Fusion des branches (ce qu'on appelle merge)
Imaginons, on a terminé de travailler sur une branche, on peut le fusionner dans une autre branche (généralement main)
- il faut basculer vers la branche cible (ici main par exemple) :
```bash
git checkout main
```
- on le fusionne
```bash
git merge nom_du_nouvelle_branche
```

## Les conflits
Lors d'une fusion, parfois git détecte des conflits entre les modifications des différentes branches. On devrait resoudre ces conflits manuellement dans les fichiers concernés, puis valider la résolution
```bash
git add nom_du_fichier_conflit
```
```bash
git commit -m "Résolution des conflits"
```

## Travailler avec des dépôts distants
Git permet de collaborer via des dépôts distants (Sur github, gitlab et d'autres aussi). 
- pour cloner un dépôt distant (c-à-d copier un dépôt sur votre machine) :
```bash
git clone URL_du_DEPOT
```
- pour ajouter un dépôt distant
```bash
git remote add origin URL_du_DEPOT
```
- pour envoyer les changements vers le dépôt distant
```bash
git push origin nom_de_la_branche
```
Mais on peut faire ça aussi :
```bash
git push -u origin nom_de_la_branche
```
Leur difference c'est que l'option `-u` : pousse la branche et configurer la branche locale pour suivre la branche distante
- pour récupérer les changements depuis un dépôt distant :
```bash
git pull origin nom_de_la_branche
```

## Comment ignorer les fichiers (comme les node_modules kkkk) ?
On devrait créer un fichier `.gitignore` . Ce fichier indique à git quels fichiers ne doivent pas êtres suivis, et ne pas les envoyer, pour ignorer les fichiers et les dossier par exemple :
- on créer le fichier .gitignore d'abord
```bash
touch .gitignore
```
- puis copiez ce code dans ce fichier .gitignore
```bash
# On peut ignorer les fichiers .log, .env par exemple
*.log
.env

# On peut ignorer les dossiers aussi comme les dossier importants par exemple ou les dossier inutiles
importants/
```