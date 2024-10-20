# Fiche de Note Git Hub
## Maitrise de GitHub
*Objectif attendu :*


- [x] installer Linux
- [ ] creer une clé SSH
- [ ] Réaliser la page sous VSCodecode
- [ ] récupérer et partager son travail sur GitHub sans dommage
- [ ] comprendre l'infrastructure de GitHub.

*A quoi il faut surtout penser :*
- faire des commits réguliers
- ne pas forcer les push `-f`, sauf cas bien partiulier
- travailler dans le bon dossier
- vérifier sur quelle branche on travaille


## 💻 Logiciel à intaller :

- [x] Linux


Pour que la travail soit fluide, nous utilisons Linux, un OS open source. Les bases sur les lignes de commande sont à connaitre que nous pouvons trouver [ici](https://cdn.hostinger.com/tutorials/pdf/Linux-Commands-Cheatsheet-FR.pdf). Thomas notre formateur nous préconise de les utiliser régulièrement pour se les approprier.

- [x] VsCode

pour réaliser la page, nous utilisons VS Code

## Comment fait-on pour travailler ensemble via GitHub ? 

*_<ins>Création d'un compte gitHub et de sa double authentification</ins>_* : ce process n'est à faire qu'une seule fois. Voici le
[lien GitHub](https://github.com/).  

<ins>Nous devons sécuriser notre travail</ins> en créant **_une clé publique_** et **_une clé privé_** correspondantes qui permettront les échanges de fichiers de **_manière sécurisée_** de la machine local à GitHub. On devra refaire des clés que si on change de machine.  
Concernant le process, on trouve plusieurs liens explicatifs sur Internet pour <ins>créer une clé SSH</ins>, en tapant [**_générer une clé SSH_**](https://docs.github.com/fr/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent). Dans le terminal, on va taper la commande `ssh-keygen -t ed25519 -C "your_email@example.com"` qui va générer <ins>la clé publique et la clé privé</ins>.  
Nous allons utiliser <ins>la clé publique en la copiant dans GitHub</ins>, la commande pour copier la clé `cat ~/.ssh/nom-de-la-cle.pub` : copier l'adresse de la clé qui apparait dans le terminal. Puis ouvrir GitHub, et cliquer sur :
1. **_la photo du profil_**
2.  ⚙️ **_parametre/setting_**
3. **_SSH/GPG KEY_**
4. **_new SH key_**
5. **_add ssh key_**

## Attention

**_Il vaut mieux ne pas mettre de mdp pour la création des clés_**  
**_Une fois les paramétrages terminés, se mettre dans le bon dossier pour travailler_**


## Quels sont les étapes pour travailler ensemble sur un dossier ?
1. Sur ton compte GitHub, crée un _repository_ de préférence en _public_ pour que l'équipe y ait accès. **_Pour choisir ton nom de dossier surtout pas de Majuscule, pas d'accent, pas d'espace_**.
2. *ajouter les collaborateurs* dans GitHub : validation à faire probablement via un email qu'on reçoit sur son adresse mail renseigné dans github. On pourra _regler des rules_ : Restrict deletions, Require linear history, Require a pull request before merging (mettre aux moins 2 personnes de l'équipe), Block force pushes...
3. Dans le terminal, crée un dossier qui sera eligible à _git_ via un `git init`qui crée un dépot GIT dans le dossier où on se trouve.
4. On partage notre dossier dans le _repository_ (créé en étape 1), on reprend la commande que l'on trouve dans le gitHub, dans le *_repository_*  
    - par exemple : `git remote add origin git@github.com:vler0ux/test.git`   

On travaille sur ses pages en faisant régulièrement 2 commandes :  
 - `git add .`ajoute tous les fichiers en *stage*  ou `git add fichier.html` pour ajouter uniquement un fichier.
 - `git commit -m "message"` qui ajoute les commits en local.
5. On tape la 1ere commande `git push -u origin main` (équivalence `git push -u origin main`) cette commande va nous permettre de pusher sur **_origine_**. Par la suite, on pourra taper uniquement `git push`, pour mettre à jour la branche *origine*.

## Les habitudes de travail
1. Vérifier qu'on est bien dans un git repository.
2. Vérifier sur quel branche on travail. commande pour changer de branche `git checkout nom-de-la-branche`
3. Dès que le travail est avancé, monter en stage, commande `git add .`
4. enregistrer en local, commande `git commit -m "message"` 
5. enregistrer sur originie, commande `git push`

## Autres choses à faire ?
- il est important d'ecrire son README.md (bien écrire README en majuscule). Ce fichier va reprendre tout ce qu'il faut savoir sur tes pages. Le texte se fait en **_Markdown_**.
- des choses à savoir comme : **_CTRL+%_** pour faire apparaitre le terminal dans Vscode, **_CTRL+C_** pour sortir d'une commande qui tourne en boucle.
- faire une recherche en ajoutant les mots clés *cheat sheet* ou *awesome* 



*_les commandes à savoir :_*
- `mkdir` crée un dossier `rmdir` supprimer un dossier
- `touch` crée un fichier
- `git push` envoie les modifications local à la branche origine
- `git pull` envoie les modifications de origine vers la branche local/main
- `git clone` clone les depots git
- `git status`montre sur quelle branche on est
- `git ls` montre les fichier du dossier/dossiers où on se trouve. Le **_flag -a_** nous permet de voir les fichiers cachés.
- `git log`montre les dernier commit qu'on a effectué
- `git stash`mettre de coté notre travail sans le commiter
- `git commit -- amend`permet de modifier le dernier commit 
- `git revert copie-du-lien-du-commit`est utilisée pour annuler un commit spécifique en créant un nouveau commit qui inverse les changements du commit à annuler, tout en préservant l'historique Git.
- `git reset copie-du-lien-du-commit`st utilisée pour supprimer ou déplacer des commits dans l’historique. Il modifie l’état de la branche locale. Les commits qui se trouvent en "sandwich" seront perdus définitivement.   
**_->_** pour trouver le lien d'un commit, il faut faire un `git log` 

## *_Insérer une branche soeur_*
La commande qu'il faut  `git checkout -b nom-de-la-nouvelle-branche` . A noter que pour <ins>changer de branche</ins>, on utilisera la même commande sans le flag **_-b_**

1. Par précaution faire un **_push_** de la branche main (ou branche locale), pour la mettre à jour via la branche **_origine_**
2. se mettre sur la branche soeur via un `git checkout branche-soeur`, puis faire un `git rebase` pour copier la branche soeur sur la branche locale
3. **_ne pas oublier de se remettre sur la branche main_**, et faire un `git push` pour mettre à jour l'ensemble de la branche

## *Pull Request* et merger sa branche 
La <ins>*_pull request_*</ins> permet de signaler qu'on a terminé les modificationss de sa branche et qu'<ins>on est prêt à l'intégrer dans la *branche main*</ins>.  
Avant cette étape, pour s'assurer de la **_qualité du code_** et **_éviter des bugs_** sur la branche principale, des **_code review_** sont fait par des developpeurs désignés. Selon les règles fixées au préalable, il faut que <ins>certains developpeurs désignés valident les PR (*Pull Request*)</ins>, pour que je puisse "merger" ma branche sur la branche main.  
Cela peut prendre du temps et il y aura tout un historique de *request*. 
Dès que toutes ces étapes sont validées, alors, on va pouvoir **_merger la branche_** avec cette commande `git merge branche-soeur`.



