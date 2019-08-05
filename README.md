# Learn-Git

## Git clone

* La commande git clone sert à télécharger un répertoire (repository) git. Elle est utilisé ainsi ``git clone <addresse>``.
* "Addresse" étant l'addresse du répertoire pour "cloner" __ce__ répertoire, il vous faudra donc faire ``git clone https://github.com/mkaku/Learn-Git.git``. Ce qui aura pour effet de créer un dossier Learn-Git à l'endroit où vous vous êtes placé.

> Attention si vous cloner un répertoire privé, il vous sera peut-être demandé de vous authentifier, si ce n'est pas déjà fait.

## Git init

* La commande git init permet d'identifier un dossier comme étant un répertoire git. Elle s'utilise comme cela ``git init`` ou ``git init <dossier>``.
* La première sans arguments prend le dossier où vous êtes situé et la seconde, un chemin vers un dossier.

> Si le dossier n'existe pas, git le créera pour vous.

## Git remote

* Git remote vous affiche les noms de vos répertoires git distans. Elle s'utilise ainsi ``git remote``.

### Git remote add
* Cette sous-commande vous permet de rajouter un répertoire git distant. Elle est utilisé comme cela ``git remote add <nom> <addresse>``.
* "nom", ici est le nom du "remote" que vous rajoutez, par convention on met "origin" et "addresse" est l'addresse du répertoire (https://machin.git).

> Bien évidemment vous ne pouvez rajouter que les répertoires dont vous disposez de l'accès.

### Git remote remove
* Cettes sous-commande supprime un remote, elle a pour syntaxe ``git remote remove <nom>``. Où "nom" est le nom du remote que vous voulez supprimer de votre liste.

## Git branch
* Imaginons que vous avez une fonctionnalité que vous devez rajouter, vous voulez donc travailler en toute liberté. C'est là que les branches rentrent en jeu, elles permettent de travailler sur un aspect individuellement pour ne pas risquer de casser tout votre programme et ensuite de porter ces modifications ("merger") vers d'autres branches une fois faites.
* ``git branch`` vous permet de voir la liste de vos branches et ``git branch <ma_branche>`` permet de rajouter la branche "ma_branche".

> Quand vous cloner avec git clone ou initialiser un répertoire avec git init, git créera automatiquement une branche master, considérez la comme votre branche principale, c'est dans celle-là que vous mergerez les commits de tout vos autres branches.

### Git branch -d
* ``git branch -d <ma_branche>`` permet de supprimer la branche "ma_branche".

## Git commit
* Un commit représente les modifications que vous avez apportés à une branche.
* Après avoir fini une modification, vous entrez ``git commit``, git va alors enregistrer ces modifications et vous pourrez y revenir plus tard.

> ``git commit`` va enregistrer un commit sans titre, il est recommendé d'en mettre. Exemple: ``git commit -m "Added text.txt"``.

## Git merge
* Merger, une branche A dans une branche B signifie en fait de porter les commits de la branche A dans la B et ainsi garder une cohésion entre vos branches.
* Pour cela, imaginons que vous avez deux branches, ``A`` et ``B``. Vous avez modifié un fichier dans B et maintenant vous voulez porter ces modifications vers votre branche A.

* I) Placez-vous dans votre branche A
* II) Rentrez ``git merge B``

## Git checkout
* Nous avons parlé plus haut de se placer sur une branche, voilà comment on fait ``git checkout <branche>``.
* Mais git checkout permet aussi de se placer dans un commit antérieur à votre branche et d'ainsi revenir à une version précise de votre projet.
* Pour cela, placez-vous dans la branche voulue et rentrer ``git checkout <SHA_du_commit>``. En bas, vous verrez comment obtenir ce sha

## Git log
* ``git log`` permet de voir la liste des commits faits dans votre branche affichée ainsi:
```
commit SHA (infos)
Author: auteur
Date:   date

    titre
```
* Exemple :
```
commit c8ee28a17dff823dc825108d45a6386d538a6e65 (HEAD -> master, origin/master, origin/HEAD)
Author: Mkdirs <39743975+Mkdirs@users.noreply.github.com>
Date:   Mon Aug 5 16:15:23 2019 +0300

    Create README.md
```

## Git pull
* On entre dans la partie intérressante car la commande ``git pull <remote> <branche>`` permet de transférer les commits de la branche du remote vers votre répertoire en local.

## Git push
* ``git push <remote> <branche>`` fait l'inverse de git pull, elle transfère les modifications apportées en local vers le remote

# Autres

## Git blame
* git blame permet d'avoir des informations précises sur un fichier comme qui a modifié x lignes, à quelle heure etc...
* Pour cela on fait ``git blame <fichier>``.

## Git stash
* git stash permet d'enregistrer les modifications que vous êtes en train d'effectuer dans un cache pour les restituer plus tard.
* Syntaxe: ``git stash``

### Git stash pop
* ``git stash pop`` restitue les modifications que vous avez mis dans le cache et vide celui-ci ensuite.

### Git stash apply
* ``git stash apply`` fait exactement la même chose que ``git stash pop`` sauf qu'elle ne vide pas le cache.

## Git reset --hard
* ``git reset --hard`` va reset toute les modifications que vous n'avez pas commité.

## Git commit --amend -m
* ``git commit --amend -m "<titre>"`` permet de modifier le titre du dernier commit de votre branche.
> Attention, cette commande affecte uniquement votre répertoire local, si vous avez déjà push le commit, votre remote ne sera pas affecté. Il vous faudra alors forcer le push avec un git push <remote> <branche> -f. Cependant, cette technique remplace les commits de votre remote par ceux en local.
  
## Git revert
* ``git revert <SHA_du_commit>`` permet de faire un commit inverse de celui dont le SHA a été mis en argument.
* Exemple vous rajoutez une ligne dans un fichier, et ensuite vous faites un commit puis, vous faites un git revert, un commit va se créer dans lequel cette ligne n'existera pas.
