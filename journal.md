1)
DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire
$ git init
Initialized empty Git repository in C:/Users/DELL/Desktop/TP/tp-02-zones-git/inventaire/.git/

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ ^C

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)

$ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        pom.xml
        src/

nothing added to commit but untracked files present (use "git add" to track)

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ ^C

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$

2) Le contenu de .git/


DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ ls -a .git
./  ../  HEAD  config  description  hooks/  info/  objects/  refs/

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ ^C

Etape paire de ma prédiction pour 

3)untracked/untracked

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git status
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        journal.md
        pom.xml
        src/

nothing added to commit but untracked files present (use "git add" to track)



4)staged/unmodified


DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git add README.md
warning: in the working copy of 'README.md', LF will be replaced by CRLF the next time Git touches it

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/


DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ ^C



5)staged/modified

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/


DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$


6)unmodified/modified

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git commit -m "ajouter README"
[main (root-commit) ce0db2b] ajouter README
 1 file changed, 11 insertions(+)
 create mode 100644 README.md

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$  git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/

nothing added to commit but untracked files present (use "git add" to track)

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$


7)unmodified/unmodified

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git add README.md

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git commit -m "complète README"
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/

nothing added to commit but untracked files present (use "git add" to track)

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git status
On branch main
Untracked files:
  (use "git add <file>..." to include in what will be committed)
        journal.md
        pom.xml
        src/

nothing added to commit but untracked files present (use "git add" to track)

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$

8)Modifier readme.md et indexer pom.xml

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git add pom.xml
warning: in the working copy of 'pom.xml', LF will be replaced by CRLF the next time Git touches it

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git status -s
A  pom.xml
?? journal.md
?? src/

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$

9) explication des colones

première colone(gauche) : état dans l'index
deuxième colonr(droite) : état dans le répertoire 

fichier , code ,signification

pom.xml , M, modifié et indexé
README.md , M ,modifié non indexé
src/, non suivi(untracked)


10)retirer pom.xml de l'index

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git status -s
A  pom.xml
?? journal.md
?? src/

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ ^C

DELL@DESKTOP-OCF6B43 MINGW64 ~/Desktop/TP/tp-02-zones-git/inventaire (main)
$ git status
On branch main
Changes to be committed:
  (us



