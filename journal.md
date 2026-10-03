 Journal TP 02  Comprendre les zones Git

1) Un dépôt neuf

$ git init
Initialized empty Git repository in C:/Users/DELL/Desktop/TP/tp-02-zones-git/inventaire/.git/

$ git status
On branch main
No commits yet
Untracked files:
        README.md
        pom.xml
        src/
nothing added to commit but untracked files present

- Phrase exacte quand aucun commit n'existe : "No commits yet"
- Ce que Git dit de src/ : affiché comme "src/" (avec slash) = un dossier, pas un fichier

2) Contenu de .git/

$ ls -a .git
./  ../  HEAD  config  description  hooks/  info/  objects/  refs/

- Nombre d'entrées : 9 (dont ./ et ../)
- Entrée pour la branche courante : HEAD
- Entrée pour le stockage du contenu : objects/

3) Paire prévue : untracked/untracked

$ git status
On branch main
No commits yet
Untracked files:
        README.md
        journal.md
        pom.xml
        src/
nothing added to commit but untracked files present

Paire réelle : untracked/untracked

4) Paire prévue : staged/unmodified

$ git add README.md
$ git status
On branch main
No commits yet
Changes to be committed:
        new file:   README.md
Untracked files:
        journal.md
        pom.xml
        src/

Paire réelle : staged/unmodified

 5) Paire prévue : staged/modified

$ git status
On branch main
Changes to be committed:
        new file:   README.md
Untracked files:
        journal.md
        pom.xml
        src/

Paire réelle : staged/modified

- Nombre d'apparitions de README.md : 2 fois
  → 1 fois dans "Changes to be committed" (version index)
  → 1 fois dans "Changes not staged for commit" (version disque modifiée)

6) Paire prévue : unmodified/modified

$ git commit -m "ajouter README"
[main (root-commit) ce0db2b] ajouter README
 1 file changed, 11 insertions(+)

$ git status
On branch main
Untracked files:
        journal.md
        pom.xml
        src/

Paire réelle : unmodified/modified
Ce qui reste : README.md reste modifié non stagé (la modification de l'étape 5 n'était pas dans l'index)

7) Paire prévue : unmodified/unmodified

$ git add README.md
$ git commit -m "complète README"
$ git status
On branch main
Untracked files:
        journal.md
        pom.xml
        src/
nothing added to commit but untracked files present

Paire réelle : unmodified/unmodified

8) Modifier README.md et indexer pom.xml

$ git add pom.xml
$ git status -s
A  pom.xml
?? journal.md
?? src/

9) Explication des colonnes

- 1ère colonne (gauche) : état dans l'INDEX
- 2ème colonne (droite) : état dans le RÉPERTOIRE DE TRAVAIL

Fichier , Code , Signification 
pom.xml , A  , Ajouté à l'index 
 journal.md ,??, Non suivi(untracked) 
 src/ ,?? ,Non suivi(untracked) 

10) Retirer pom.xml de l'index

 Commande trouvée dans git status : git restore --staged 
 Commande utilisée : git restore --staged pom.xml
 Zone après : répertoire de travail (untracked)

11) git log --oneline

$ git log --oneline
5766e0a (HEAD -> main) ajout du README

- Nombre de commits : 2 (après le commit final)
- 7 caractères du plus récent : ba0af06

Fin du TP 02

$ git status
On branch main
nothing to commit, working tree clean

$ git log --oneline
ba0af06 (HEAD -> main) fin du TP 02
5766e0a ajout du README