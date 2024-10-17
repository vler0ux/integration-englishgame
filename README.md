# Fiche de Note Git Hub
## Maitrise de GitHub
*Objectif attendu :*

- 
- [x] installer Linux
- [ ] creer une clé SSH
- [ ] Réaliser la page sous VSCodecode
- [ ] récupérer et partager son travail sur GitHub sans dommage
- [ ] comprendre l'infrastructure de Github.

*A quoi il faut surtout penser :*
- faire des commits réguliers
- ne pas forcer les push `-f`, sauf cas bien partiulier

*moyen et outils :*  
## Logiciel à intaller :

- [x] Linux


Pour que la travail soit fluide, nous utilisons Linux, un OS open source. Les bases sur les lignes de commande sont à connaitre que nous pouvons trouver [ici](chrome-extension://efaidnbmnnnibpcajpcglclefindmkaj/https://cdn.hostinger.com/tutorials/pdf/Linux-Commands-Cheatsheet-FR.pdf). Thomas notre formateur nous préconise de les utiliser régulièrement pour se les approprier.

- [x] VsCode

pour réaliser la page, nous utilisons VS Code

## Comment fait-on pour travailler ensemble via GitHub ?

*_<ins>Création d'un compte gitHub et de sa double authentification</ins>_* : ce process n'est à faire qu'une seule fois. Nous trouvons un lien
[lien GitHub](https://github.com/) explicatif, puis <ins>création d'une clé SSH</ins>, nous trouvons plusieurs sites en tapant **_générer une clé SSH_**, de même nous trouvons un [lien d'exemple](https://docs.github.com/fr/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) et notamment cette ligne de commande `ssh-keygen -t ed25519 -C "your_email@example.com"` pour la générer. Le process à suivre est bien expliqué sur la page. 

**_Il vaut mieux ne pas mettre de mdp pour la clé_**

## Quels sont les étapes pour travailler ensemble sur un dossier ?
1. Sur ton compte GitHub, créer un _repository_ de préférence en _public_ pour que l'équipe y ait accès. **_Pour choisir ton nom de dossier surtout pas de Majuscule, pas d'accent, pas d'espace_**
2. *ajouter les collaborateurs* dans GitHub, les validations seront à faire probablement via un email qu'on reçoit sur son adresse mail github. On pourra _regler les rules_ : Restrict deletions, Require linear history, Require a pull request before merging (mettre aux moins 2 personnes de l'équipe), Block force pushes. 
3. Dans le terminal, créer un dossier qui sera eligible à _git_ via un `git.init`qui crée un dépot GIT dans le dossier où on se trouve.
4. On travaille sur ses pages en faisant régulièrement 2 commandes :
    - `git add .`ajoute les fichiers contenu dans le dossier vers la branche local
    - `git commit -m "message"` qui nous permettrons de voir l'avancement des travaux sur la page lorsque celle ci sera sur **_origine_**
5. on veut partager notre travail le _repository_ (créé en étape 1), on reprend la commande que l'on trouve dans le gitHub, dans le *_repository_*
    - par exemple : `git remote add origin git@github.com:vler0ux/test.git` 
6. On tape la commande `git push -u origin main` (équivalence `git push -u origin main`) cette commande va nous permettre de pusher sur **_origine_**. Par la suite, on pourra taper uniquement `git push`

## autres choses à faire ?
- il est important d'ecrire son README.md (attention l'orthographe et les majuscules sont importantes). Ce fichier va reprendre tout ce qu'il faut savoir sur tes pages. Le texte se fait en **_Markdown_**.
- des choses à savoir comme : **_CTRL+%_** pour faire apparaitre le terminal dans Vscode, **_CTRL+C_** pour sortir d'une commande qui tourne en boucle, quand on veut trouver des infos sur le net taper comme mots clés *cheat sheet* ou *awesome*



*_les commandes à savoir :_*

- `git push` envoie les modifications local à la branche origine
- `git pull` envoie les modifications de origine vers la branche local/main
- `git clone` clone les depots git
- `git status`affiche la liste des fichiers dans le terminal
- `git log`montre les dernier commit qu'on a effectué
- `git stash`mettre de coté notre travail sans le commit
- `git commit -- amend`
- `git revert`
- `git reset`

## *_Inserer une branche soeur_*
la commande qu'il faut  `git checkout -b nom-de-la-nouvelle-branche` . 

1. Attention ! Faire est un **_push_** de la branche main (ou branche locale), pour la mettre à jour via la branche **_origine_**
2. on pourra faire un `git rebase` pour lier la branche soeur sur la branche locale
3. ne pas oublier de refaire un `git push` pour mettre à jour l'ensemble de la branche

## Faire une *Pull Request*
Quand notre branche enfant est dans orgine, il n'est pas judicieux de la fusionner directement avec la branche main, cela pourrait causer des interferences (rapelle des *rules* mis en place + haut). La branche est en *PR* et de nombreuses *request* sont en cours de validation, dès que toutes (ou les ppx) sont validés, on va pouvoir *merge la PR* avec cette commande `git merge nom-de-la-branche-enfant`



