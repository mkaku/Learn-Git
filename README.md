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

## Git pull
* On entre dans la partie intérressante car la commande ``git pull <remote> <branche>`` permet de transférer les modifications (commits) vers le remote spécifié dans la branche renseignée.
> Nous parlerons des branches et des commits plus tard, pour l'instant contentez-vous de ``git pull <nom_remote> master``.

## Git push
* ``git push <remote> <branche>`` fait l'inverse de git pull, elle transfère les modifications apportées au remote vers votre répertoire local.
