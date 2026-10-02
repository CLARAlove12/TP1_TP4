# TP 04 — Maîtriser les fusions

## Prédiction de l'étape 3

Je n'attends pas de commit de fusion. main n'a pas divergé depuis la création de feature-a, donc Git devrait faire une avance rapide.

## Réponse à l'étape 4

Git n'a pas créé de commit de fusion parce que main n'avait aucun commit absent de feature-a : il suffit de déplacer le pointeur de main, c'est une avance rapide.

## Réponse à l'étape 6

Le commit de fusion a deux parents.

Vérification (git cat-file -p HEAD | grep parent) :

parent  <hash main>
parent  <hash feature-b>

## Fichier en conflit verbatim (étape 9)

<<<<<<< HEAD
Version main
=======
Version feature-c
>>>>>>> feature-c

## Message d'erreur exact de Git (étape 9)

Auto-merging fichier.txt
CONFLICT (content): Merge conflict in fichier.txt
Automatic merge failed; fix conflicts and then commit the result.

## Réponse à l'étape 10

Commande qui termine la fusion : git commit

Ce qui se passe si on oublie git add :

error: Committing is not possible because you have unmerged files.

La fusion reste en cours. git merge --continue exige aussi que tous les conflits soient indexés.

## Sortie git lg (étape 3)

* <hash> (HEAD -> main, feature-a) Ajoute une ligne sur feature-a
* <hash> Premier commit

## Sortie git lg (étape 7)

*   <hash> (HEAD -> main) Merge branch 'feature-b'
|\
| * <hash> (feature-b) Travail sur feature-b
* | <hash> Travail sur main
|/
* <hash> Premier commit

## Étape 12 — Niveau 4 de learngitbranching.js.org

Suite de commandes du niveau 4 :

git branch -f main HEAD~3
git rebase main bugFix
git rebase bugFix side

Ce que je retiens sur rebase :

rebase rejoue les commits sur une nouvelle base. L'historique devient linéaire et les hash des commits rejoués changent. En équipe, on ne rebase jamais une branche déjà poussée et partagée.