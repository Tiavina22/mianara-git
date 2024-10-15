# GIT C'EST QUOI ?
Git est système de gestion de versionning, permmettant de suivre les modifications dans les fichiers de n'importe quelle projet. Il permet à plusieurs collaborateurs de collaborer efficacement sur le même projet, surtout projet IT.

## How to install Git ?
- Si vous êtes sur `windows` : Débrouillez-vous seul
- Si vous êtes sur `macOS` : Débrouillez-vous seul aussi
- Si vous êtes sur `Linux` : ok, suivez les instructions suivantes :
1 - Mettre à jour votre paquet d'abord
```shell
sudo apt update
```
2 - Installer git maintenant
```shell
sudo apt install git
```
De vita ny chocolat

## Il faut le configurer 
Aprè l'installation, il faut que vous configure votre informations d'utilisateur pour que git puisse les utiliser dans vos commits
```shell
git config --global user.name = "Votre Nom"
```
```shell
git config --global user.email = "Votre Email"
```

## Initialisation
Git fonctionne sur un dépôt ou repository en anglais dans lequel IGt suivra l'évolution de nos fichier.
Imaginons, on créer un simple projet avec dart avec le structure suivante :

<img src="src/structure.png" alt="Texte alternatif" width="250">

Pour initialiser git dans notre projet, il faut qu'on positionne dans le répértoire root de notre projet, et puis
```shell
git init
```
Cela crée un répertoire .git dans notre dossier, où git stockera les informations sur l'historique des versions

<img src="src/init.png" alt="Texte alternatif" width="500">