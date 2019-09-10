## Manuel

#### 1. A l’aide du manuel, identifiez le rôle de la commande which

La commande `which` a pour role de localiser une commande, un binaire. En clair, elle permet d'identifier la version d'une commande ou d'un programme.

#### 2. Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option ?

Il faut appuyer sur `/` puis écrire `option` <br>
commande : `/option`

#### 3. Comment quitte-t-on le manuel ?

Il suffit d'appuyer sur la touche `q`.

#### 4. Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?

La commande `man 6 intro` permet d'afficher la première page de la section 6 du manuel. Cette section traite des jeux et des programmes disponibles sur le système.

```
    DESCRIPTION
       Section 6 of the manual describes the games and funny little programs available on the system.
```

## Navigation dans l’arborescence des fichiers
---

#### 1. allez dans le dossier /var/log

Il faut taper `cd /var/log` dans le terminal.

#### 2. remontez dans le dossier parent (/var) en utilisant un chemin relatif

Il faut taper `cd ..` dans le terminal. Cette commande permet d'acceder au dossier parent duquel nous sommes.

#### 3. retournez dans le dossier personnel

Tapez `cd`  dans le terminal, il redirigera automatiquement vers le dossier personnel de l'utilisateur.

#### 4. revenez au dossier précédent (/var)

La commande `cd -`  permet de retourner dans le dossier précédent

#### 5. essayez d’accéder au dossier /root ; que se passe-t-il ?

En essayant d'acceder au dossier /root via `cd /root` la permission est refusée. <br>
Message : *Permission denied*

#### 6. essayez la commande sudo cd /root ; que se passe-t-il ? Expliquez

La commande `sudo cd /root` éxige un mot de passe. En effet sudo signife l'éxecution d'une commande en tant qu'administrateur. Elle permet à un utilisateur lambda d'executer une commande administrateur. Pour cela, un mot de passe administrateur est requis. Cependant, la commande `sudo cd /root` ne fonctionne par car en mode sudo nous n'avons pas accès aux commandes du Shell.

#### 7. à partir de votre dossier personnel, créez l’arborescence suivante :

Tutoriel : <br>
-`mkdir Dossier1` <br>
-`touch Dossier1/Fichier1` <br>
-`mkdir Dossier2` <br>
-`cd Dossier2` <br>
-`mkdir -p Dossier2.{1,2}` <br>
-`cd Dossier2.2` <br>
-`touch Fichier{2,3}`

#### 8. revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1 ; que se passe-t-il ?

Pour revenir au dossier personnel : `cd`
Pour supprimer le Fichier1 : `rm Dossier1/Fichier1`

La commande `rm Dossier1` renvoie une erreur : <br>
_cannot remove Dossier1: Is a directory_

Il faut modifier la commande `rm` afin de supprimer un dossier.

#### 9. quelle commande permet de supprimer un dossier ?

La commande pour supprimer un dossier est `rmdir <dossier>`.

#### 10. que se passe-t-il quand on applique cette commande à Dossier2 ?

Lorsqu'on essaye de supprimer le _Dossier2_ avec la commande `rmdir Dossier2` l'action est annulée car le dossier n'est pas vide.

#### 11. comment supprimer en une seule commande Dossier2 et son contenu ?

La commande `rm -r Dossier2` permet de supprimer les sous-dossiers et fichiers du répertoire.

## Commandes importantes
---

#### 1. Quelle commande permet d’afficher l’heure ? A quoi sert la commande time ?

La commande `date` permet d'afficher l'heure tandis que la commande `time` sert à determiner le temps d'execution d'un certaine commande. Exemple: <br>

`time ls` nous renvoi : <br>
`real 0m0,001s` <br>
`user 0m0,001s` <br>
`sys 0m0,000s`

Il faut donc 0,001s pour que le système exécute la commande `ls`.

#### 2. Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire sur les fichiers commençant par un point ?

Lorsqu'on exécute `ls` puis `la` on s'aperçoit que des fichiers commençant par des points sont affichés. On en déduit que ce sont des <b>fichiers cachés</b>.

#### 3. Où se situe le programme ls ?

La commande `ls` est située dans le dossier `/usr/bin/ls`.

#### 4. Que fait la commande ll ? (indice : la commande alias peut vous aider)

`ll` permet d'afficher la totalité des informations des fichiers/dossiers (droits, propriétaire, groupe propriétaire, horodatage, nom, taille).

#### 5. Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?

La commande `ls bin`.

#### 6. Que fait la commande ls .. ?

`ls ..` permet de lister les fichiers et dossiers du dossier parent.

#### 7. Quelle commande donne le chemin complet du dossier courant ?

`pwd`.
Le résultat obtenu est : `/home/serveur`.

#### 8. Que fait la commande echo 'yo' > plop exécutée 2 fois ?

Cette commande permet de créer un fichier plop et d'y écrire 'yo'. Le contenu du fichier est alors supprimé.
On obtient un fichier 'plop' avec écrit:
<br>yo

#### 9. Que fait la commande echo 'yo' >> plop exécutée 2 fois ?

Cette commande permet de créer un fichier plop (si pas déjà fait) puis d'y insérer 'yo'.
On obtient alors un fichier 'plop' avec écrit:
<br>yo<br>yo

#### 10. A quoi sert la commande file ? Essayez la sur des fichiers de types différents.

La commande `file` permet d'identifier le type d'un fichier, ou s'il s'agit d'un dossier.

#### 11. Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi : qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?

Après avoir modifié le contenu de toto via `echo 'test' >> toto'` et qu'on utillise `cat titi` on observe que les modifications ont impactées le fichier titi. A la suppression de toto, titi reste intacte. On appelle ça un <b>soft link</b>.

#### 12. Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle conséquence cela a-t-il sur tutu ?

La modification de titi impacte tutu et inversement. Tutu devient alors rouge. Tutu ne peut plus pointer vers titi, le fichier est inutilisable, considéré comme supprimé. On appelle cela un <b>hard link</b>.

#### 13. Affichez à l’écran le fichier /var/log/syslog. Quels raccourcis clavier permettent d’interrompre et reprendre le défilement à l’écran ?

<b>CTRL + S</b> interrompt le défilement et <b>CTRL + Q</b> reprend le défilement

#### 14. Affichez les 5 premières lignes du fichier /var/log/syslog, puis les 15 dernières, puis seulement les lignes 10 à 20.

La commande `head -5 /var/log/syslog` permet d'afficher les 5 premières lignes. <br>
`tail -15 /var/log/syslog` permet d'afficher les 15 dernières. <br>
Et` head -10 /var/log/syslog | tail -n20` pour les lignes 10 à 20 lignes. 

#### 15. Que fait la commande dmesg | less ?

La commande `dmesg` permet de voir l'historique des messages du noyaux. `less` permet quant à elle de naviguer en réduisant l'espace pris par le résultat renvoyé.

#### 16. Affichez à l’écran le fichier /etc/passwd ; que contient-il ? Quelle commande permet d’afficher la page de manuel de ce fichier ?

Le fichier _/etc/passwd_ contient la liste des utilisateurs ainsi que des données sur leur compte comme l'id, le chemin d'accès au dossier utilisateur, le shell utilisé (/bin/false pour interdire).<br>
La commande pour accéder au manuel de ce fichier est `man 5 passwd`.

#### 17. Affichez seulement la première colonne triée par ordre alphabétique inverse

Il faut utiliser `sort -r +0 /etc/passwd`.<br>
`sort` permet trier les colonnes.<br>
`-r` permet de trier dans l'ordre alphabétique.<br>
`+0` signifie que l'on souhaite converser que la premiere colonne.


#### 18. Quelle commande nous donne le nombre d’utilisateurs ?

Le nombre d'utilisateurs est égal au nombre de lignes du fichier passwd _(fichier qui contient les informations des utilisateurs)_.
Pour cela nous utiliserons la command `wc -l /etc/passwd`.

#### 19. Combien de pages de manuel comportent le mot-clé _conversion_ dans leur description ?

--

#### 20. A l’aide de la commande find, recherchez tous les fichiers se nommant passwd présents sur la machine

Pour chercher tous les fichiers nommés passwd dans la totalité du système il faut utiliser la commande `find / -name 'passwd'`.

#### 21. Modifiez la commande précédente pour que la liste des fichiers trouvés soit enregistrée dans le fichier ~/list_passwd_files.txt et que les erreurs soient redirigées vers le fichier spécial /dev/null

`find / -name 'passwd' > ~/list_passwd_files.txt 2> /dev/null` <br>
`> ~/list_passwd_files.txt` stock le resultat dans le fichier _list_passwd_files.txt_ de l'utilisateur courant.   

" _2> /dev/null implies that STDERR be redirected to the null device /dev/null._ "  
`2>` permet donc de rediriger les erreurs vers un autre fichier. STDERR = erreur standard.

#### 22. Dans votre dossier personnel, utilisez la commande grep pour chercher où est défini l’alias ll vu précédemment

-- 

#### 23. Utilisez la commande locate pour trouver le fichier history.log.

`locate history.log` renvoie `/var/log/apt/history.log`.

#### 24. Créer un fichier dans votre dossier personnel puis utilisez locate pour le trouver. Apparaît-il ? Pourquoi ?

`locate` permet comme la commande `find` de localiser des fichiers mais elle se fait depuis une base de données mise à jour quotidiennement (à 7h30) là où `find` effectue sa recherche en temps réel.
Ainsi, comme la base de données n'est pas à jour on ne peut trouver le fichier créé à l'instant.

### Travailler avec plusieurs shells
_On peut utiliser jusqu’à 6 shells en parallèle. Ils portent les noms ttyX (où X va de 1 à 6) et sont
accessibles via Alt + FX_

## Découverte de l’éditeur de texte nano
---

<br>
<br>

| Commande         	| Action                                                                             	|
|------------------	|------------------------------------------------------------------------------------	|
| F1F1 ou Ctrl + G 	| Affichage de l'aide                                                                	|
| Ctrl + X         	| Quitter nano / Fermer une fenêtre / Exécuter une commande                          	|
| Ctrl + R         	| Ouvrir un fichier                                                                  	|
| Ctrl + O         	| Enregistrer sous                                                                   	|
| Ctrl + S         	| Enregistrer                                                                        	|
| Ctrl + K         	| Couper                                                                             	|
| Ctrl + U         	| Coller                                                                             	|
| Ctrl + W         	| Rechercher                                                                         	|
| Ctrl + \         	| Remplacer                                                                          	|
| Ctrl + C         	| Afficher des informations sur la position du curseur (numéro de ligne, de colonne) 	|
| Alt + U          	| Annuler                                                                            	|
| Alt + E          	| Refaire                                                                            	|
|                  	|                                                                                    	|
|                  	|                                                                                    	|

#### 1. Copiez le fichier /var/log/syslog dans votre dossier personnel sous le nom log.txt, puis ouvrez-le avec nano

Pour copier un fichier il faut utiliser la commande `cp SOURCE DEST` 
<br>ici `cp /var/log/syslog ~/`

#### 2. Remplacez toutes les occurrences du mot kernel par le mot noyau

pour remplacer une occurence il faut :
- Ctrl + \ <br>
- Entrer le mot à remplacer
- Appuyer sur _entrer_
- Entrer le mot 
- Appuyer sur _a_

#### 3. Déplacer les 10 premières lignes à la fin du fichier

- ^K (selectionner les 10 premières lignes).<br>
- ^_ (aller à la ligne 10000).<br>
- ^U (coller les 10 premières lignes).

#### 4. Annulez cette action

M-U (Alt + U)

#### 5. Enregistrez le fichier avant de quitter nano

Ctrl+S


