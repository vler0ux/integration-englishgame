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
    - `git add .`ajoute les fichiers en *stage*
    - `git commit -m "message"` qui nous permettrons de voir l'avancement des travaux sur la page lorsque celle ci sera sur **_origine_**
5. on veut partager notre travail le _repository_ (créé en étape 1), on reprend la commande que l'on trouve dans le gitHub, dans le *_repository_*
    - par exemple : `git remote add origin git@github.com:vler0ux/test.git` 
6. On tape la commande `git push -u origin main` (équivalence `git push -u origin main`) cette commande va nous permettre de pusher sur **_origine_**. Par la suite, on pourra taper uniquement `git push`

##_ Les habitudes de travail
1. Vérifier qu'on est bien dans un git repository.
2. Vérifier sur quel branche on travail. commande pour changer de branche `git checkout nom-de-la-branche`
3. Dès que le travail est avancé, monter en stage, commande `git add .`
4. enregistrer en local, commande `git commit -m "message"` 
5. enregistrer sur originie, commande `git push`

## autres choses à faire ?
- il est important d'ecrire son README.md (attention l'orthographe et les majuscules sont importantes). Ce fichier va reprendre tout ce qu'il faut savoir sur tes pages. Le texte se fait en **_Markdown_**.
- des choses à savoir comme : **_CTRL+%_** pour faire apparaitre le terminal dans Vscode, **_CTRL+C_** pour sortir d'une commande qui tourne en boucle, quand on veut trouver des infos sur le net taper comme mots clés *cheat sheet* ou *awesome*



*_les commandes à savoir :_*
- `mkdir` crée un dossier
- `touch` crée un fichier
- `git push` envoie les modifications local à la branche origine
- `git pull` envoie les modifications de origine vers la branche local/main
- `git clone` clone les depots git
- `git status`montre sur quelle branche on est
- `git ls` montre les fichier du dossier/dossiers où on se trouve
- `git log`montre les dernier commit qu'on a effectué
- `git stash`mettre de coté notre travail sans le commit
- `git commit -- amend`permet de modifier le dernier commit 
- `git revert copie-du-lien-du-commit`est utilisée pour annuler un commit spécifique en créant un nouveau commit qui inverse les changements du commit à annuler, tout en préservant l'historique Git.
- `git reset copie-du-lien-du-commit`st utilisée pour supprimer ou déplacer des commits dans l’historique. Il modifie l’état de la branche locale. Les commits qui se trouvent en "sandwich" seront perdus définitivement.   
**_->_** pour trouver le lien d'un commit, il faut faire un `git log` 

## *_Inserer une branche soeur_*
la commande qu'il faut  `git checkout -b nom-de-la-nouvelle-branche` . 

1. Attention ! Faire est un **_push_** de la branche main (ou branche locale), pour la mettre à jour via la branche **_origine_**
2. on pourra faire un `git rebase` pour lier la branche soeur sur la branche locale
3. ne pas oublier de refaire un `git push` pour mettre à jour l'ensemble de la branche

## *Pull Request* et merger sa branche 
La <ins>*_pull request_*</ins> permet de signaler qu'on a terminé les modificationss de sa branche et qu'<ins>on est prêt à l'intégrer dans la *branche main*</ins>.  
Avant cette étape, pour s'assurer de la **_qualité du code_** et **_éviter des bugs_** sur la branche principale, des **_code review_** sont fait par des developpeurs désignés. Selon les règles fixées au préalable, il faut que <ins>certains developpeurs désignés valident les PR (*Pull Request*)</ins>, pour que je puisse "merger" ma branche sur la branche main.  
Cela peut prendre du temps et il y aura tout un historique de *request*. 
Dès que toutes ces étapes sont validées, alors, on va pouvoir **_merger la branche_** avec cette commande `git merge nom-de-la-branche-enfant`



