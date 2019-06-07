# marocrafts-git

## Paramétrage de la configuration
```
3 niveaux de fichiers de config

▪ L'option --system à git config lit et écrit dans le fichier:  *sudo vi /usr/local/git/etc/gitconfig* :
Contient les valeurs pour tous les utilisateurs et tous les dépôts du système.
▪ L'option --global lit et écrit dans le fichier: *vi ~/.gitconfig*
Spécifique à votre utilisateur.
▪ Fichier config dans le répertoire Git (c'est-à-dire .git/config)
du dépôt en cours d'utilisation : spécifique au seul dépôt en cours.

Chaque niveau surcharge le niveau précédent, donc les valeurs dans .git/config surchargent celles de /etc/gitconfig.
```

## Mettre en place son environnement local

```
▪ Git init

Votre identité:
▪ git config --global user.name "Yahya Youness"
▪ git config --global user.email yahya.youness.crafts@gmail.com

Votre editeur de texte:
▪ git config --global core.editor

Votre outil de gestion de différence:
▪ git config --global merge.tool vimdiff

Vos params:
▪ git config --global color.ui true
```

## Le fichier de config est un fichier ini créé par défaut dans votre dossier utilisateur

```
▪ vi ~/.gitconfig
```

## Création d’un premier repo git :

```
▪ mkdir monrepo
▪ cd monrepo
▪ git init
```

## On ajoute un fichier et on le commit...

```
▪ touch readme.txt
▪ git add readme.txt
▪ git status
▪ git commit -m "added read me"
▪ git status
▪ git log
```

## On ajoute un fichier et on le commit...

```
▪ touch myfile.txt
▪ git add myfile.txt
▪ git status
▪ git commit -m "added myfile"
▪ git status
▪ git log

```

## Pour supprimer un fichier du repo. : git rm à la place de git add puis commit etc.

```
▪ git rm myfile.txt
▪ git status
▪ git commit -m "remove myfile"
▪ git status
▪ git log
```

## Ignorer un fichier ou un dossier pour ne pas l’envoyer dans le repo.

## Ajoutez un fichier .gitignore à la racine du repo.

```
▪ vi .gitignore
inserer les fichiers à ignorer
```

## A tout moment, vous pouvez obtenir de l’aide sur une commande git.

```
git help
◉ git help commit
◉ git help push
◉ git help <command>
```

## Commits

```
git commit -m « message » ➔ Commit tout ce qui a été stagé (git add) avec le message
message
▪ git commit -am « message » ➔ Ajoute les changements de tous les fichiers déjà versionnés
▪ git commit --amend ➔ Ajoute les modifications au dernier commit (attention à ce qu’il n’ait pas
déjà été propagé à d’autres repo. où vous aurez un conflit)
```

## Diffs

```
▪ Comparer ce qui a été fait :
▪ git diff
• git diff -> montre ce qui a été modifié depuis le dernier commit mais non stagé~ git diff HEAD
• git diff --cached -> crée un diff entre le staging et le dernier commit de la branche actuelle
• git diff --shortstat -> afficher une liste des fichiers modifiés avec un compteur sur les lignes
```


## Log

```
▪ git log --graph
▪ git log -p {filename} ▪ Voir tous les commits sur un
fichier
```

## Lister les fichiers et leurs modifs (insertion / suppression)
```
▪ git log --stat ▪ lister les fichiers et leurs modifs
(insertion / suppression)
```

git log --pretty=oneline --abbrev-commit --decorate
○ voir un log raccourci avec une ligne par
commit

● git log -n1 --format="%h"
○ Voir le short hash du dernier commit


## Alias

```
> Ajoutez un alias nommé ‘gls’ pour afficher le dernier hash de commit
● Un alias est un raccourci vers une commande.
● Définition :
○ ~/user/.bash_profile
● Syntaxe :
○ alias name=”command”
○ Exemple :
■ alias gls="git log --oneline --decorate"

● Utilisation :
○ gls

alias gaa="git add -A"
alias gba="git branch -a"
alias gco='git commit'
alias gdc='git diff --cached'
alias gfp='git fetch --prune'
alias gis='git status'
alias gpo='git push origin'
alias gpom='git push origin master'
alias gl='git log --stat'
alias gls='git log --pretty=oneline --abbrev-commit --decorate'
alias glo='git log --pretty=oneline --abbrev-commit --decor -4'
```

## Reset

Si je modifie readme.txt et que je veux le réinitialiser à l’état du dernier commit :
> git checkout readme.txt

◉ Pour annuler toutes les opérations de staging :
> git reset

◉ Pour annuler une opération de staging sur un fichier
> git reset readme.txt

◉ Pour revenir à l’état du dernier commit mais garde tous les fichiers non trackés :
> git reset --hard

## Clone && Pull

Cloner un dépôt distant pour l’avoir en local
> git clone https://gitlab.com/raiser/formation.git

◉ Voir le dépôt distant qui a été cloné
> git remote -v

◉ Mettre à jour votre branche master du dépôt local depuis le dépôt distant (et la
merger si necessaire)
> git pull origin master

## Fetch

◉ Synchroniser les informations sur le repo. distant
> git fetch origin

◉ Voir toutes les branches

> git branch -a≠≠≠≠≠≠

◉ Voir le retard de votre branche locale sur la branche remote

> git status

## Remote

Pour ajouter une référence vers un dépôt remote :
▪ git remote add monrepo git@gitlab.com:xxxx/xxxx.git
▪ git remote add monrepo https://gitlab.com/xxxx/xxxx.git

▪ Pour supprimer une référence d’un dépôt remote

▪ git remote remove monrepo
=====
