# TP 01 — Installer & configurer Git

## 1) Version de Git
- Prédiction avant l'installation : 2.45.0
- Version réelle : git version 2.55.0.windows.5

## 2) Terminal neuf
La commande `git --version` a fonctionné directement dans le terminal neuf,
aucune correction nécessaire.

## 3) Fichier de configuration global
C:/Users/DELL/.gitconfig

## 4) Priorité des niveaux de configuration
Deux valeurs user.email étaient présentes : une dans la configuration globale
et une dans la configuration locale du dépôt.

`git config user.email` renvoyait la valeur LOCALE : moi@autre-domaine.fr

Après suppression de la valeur locale (git config --unset user.email),
`git config user.email` renvoie de nouveau la valeur GLOBALE :
adetouclaris@gmail.com

Règle : lorsqu'un même réglage est défini à plusieurs niveaux, la configuration
la plus spécifique l'emporte — local > global > système.

## 5) core.autocrlf
Sur Windows, core.autocrlf=true fait que les fichiers du disque sont écrits
avec des fins de ligne CRLF, tandis que Git normalise les fins de ligne en LF
à l'intérieur du dépôt.

## 6) Sortie complète de `git config --global --list --show-origin`
file:C:/Users/DELL/.gitconfig user.name=CLARAlove12
file:C:/Users/DELL/.gitconfig user.email=adetouclaris@gmail.com
file:C:/Users/DELL/.gitconfig init.defaultBranch=main
file:C:/Users/DELL/.gitconfig core.editor=code --wait
file:C:/Users/DELL/.gitconfig core.autocrlf=true