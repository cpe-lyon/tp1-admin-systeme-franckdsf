## Manuel

#### 1. A l’aide du manuel, identifiez le rôle de la commande which

La commande `which` a pour role de localiser une commande, un binaire. En clair, elle permet d'identifier la version d'une commande ou d'un programme.

#### 2. Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option ?

il faut appuyer sur `/` puis écrire `option` <br>
commande : `/option`

#### 3. Comment quitte-t-on le manuel ?

il suffit d'appuyer sur la touche `q`.

#### 4. Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?

la commande `man 6 intro` permet d'afficher la première page de la section 6 du manuel. Cette section traite des jeux et des programmes disponibles sur le système.

## Navigation dans l’arborescence des fichiers

#### 1. allez dans le dossier /var/log

il faut taper `cd /var/log` dans le terminal.

#### 2. remontez dans le dossier parent (/var) en utilisant un chemin relatif

il faut taper `cd ..` dans le terminal. Cette commande permet d'acceder au dossier parent duquel nous sommes.

#### 3. retournez dans le dossier personnel

tapez `cd`  dans le terminal, il redirigera automatiquement vers le dossier personnel de l'utilisateur.

#### 4. revenez au dossier précédent (/var)

la commande `cd -`  permet de retourner dans le dossier précédent

#### 5. essayez d’accéder au dossier /root ; que se passe-t-il ?

En essayant d'acceder au dossier /root via `cd /root` la permission est refusée. <br>
Message : *Permission denied*

#### 6. essayez la commande sudo cd /root ; que se passe-t-il ? Expliquez

la commande `sudo cd /root` éxige un mot de passe. En effet sudo signife l'éxecution d'une commande en tant qu'administrateur. Elle permet à un utilisateur lambda d'executer une commande administrateur. Pour cela, un mot de passe administrateur est requis. Cependant, la commande `sudo cd /root` ne fonctionne par car en mode sudo nous n'avons pas accès aux commandes du Shell.

#### 7. à partir de votre dossier personnel, créez l’arborescence suivante :

tutoriel : <br>
-`mkdir Dossier1` <br>
-`touch Dossier1/Fichier1` <br>
-`mkdir Dossier2` <br>
-`cd Dossier2` <br>
-`mkdir -p Dossier2.{1,2}` <br>
-`cd Dossier2.2` <br>
-`touch Fichier{2,3}`

#### 8. revenez dans votre dossier personnel ; à l’aide de la commande rm, essayez de supprimer Fichier1, puis Dossier1 ; que se passe-t-il ?

pour revenir au dossier personnel : `cd`
pour supprimer le Fichier1 : `rm Dossier1/Fichier1`

la commande `rm Dossier1` renvoie une erreur : <br>
_cannot remove Dossier1: Is a directory_

Il faut modifier la commande `rm` afin de supprimer un dossier.

#### 9. quelle commande permet de supprimer un dossier ?

La commande pour supprimer un dossier est `rmdir <dossier>`.

#### 10. que se passe-t-il quand on applique cette commande à Dossier2 ?

Lorsqu'on essaye de supprimer le _Dossier2_ avec la commande `rmdir Dossier2` l'action est annulée car le dossier n'est pas vide.

#### 11. comment supprimer en une seule commande Dossier2 et son contenu ?

la commande `rm -r Dossier2` permet de supprimer les sous-dossiers et fichiers du répertoire.

## Commandes importantes

#### 1. Quelle commande permet d’afficher l’heure ? A quoi sert la commande time ?

la commande `date` permet d'afficher l'heure tandis que la commande `time` sert à determiner le temps d'execution d'un certaine commande. Exemple: <br>

`time ls` nous renvoi : <br>
`real 0m0,001s` <br>
`user 0m0,001s` <br>
`sys 0m0,000s`

il faut donc 0,001s pour que le système exécute la commande `ls`.

#### 2. Dans votre dossier personnel, tapez successivement les commandes ls puis la ; que peut-on en déduire sur les fichiers commençant par un point ?

lorsqu'on exécute `ls` puis `la` on s'aperçoit que des fichiers commençant par des points sont affichés. On en déduit que ce sont des <b>fichiers cachés</b>.

#### 3. Où se situe le programme ls ?

la commande `ls` est située dans le dossier `/usr/bin/ls`.

#### 4. Que fait la commande ll ? (indice : la commande alias peut vous aider)

`ll` permet d'afficher la totalité des informations des fichiers/dossiers (droits, propriétaire, groupe propriétaire, horodatage, nom, taille).

#### 5. Quelle commande permet d’afficher les fichiers contenus dans le dossier /bin ?

la commande `ls bin`

#### 6. Que fait la commande ls .. ?

`ls ..` permet de lister les fichiers et dossiers du dossier parent.

#### 7. Quelle commande donne le chemin complet du dossier courant ?

`pwd`.
Le résultat obtenu est : `/home/serveur`.

#### 8. Que fait la commande echo 'yo' > plop exécutée 2 fois ?

cette commande permet de créer un fichier plop et d'y écrire 'yo'. Cependant cette opération n'est pas répétée.
On obtient alors un fichier 'plop' avec écrit:
<br>yo

#### 9. Que fait la commande echo 'yo' >> plop exécutée 2 fois ?

cette commande permet de créer un fichier plop (si pas déjà fait) puis d'y insérer 'yo'. Cette opération est répétée.
On obtient alors un fichier 'plop' avec écrit:
<br>yo<br>yo

#### 10. A quoi sert la commande file ? Essayez la sur des fichiers de types différents.

La commande `file` permet d'identifier le type d'un fichier.

#### 11. Créez un fichier toto qui contient la chaîne Hello Toto ! ; créer ensuite un lien titi vers ce fichier avec la commande ln toto titi. Modifiez à présent le contenu de toto et affichez le contenu de titi : qu’observe-t-on ? Supprimez le fichier toto ; quelle conséquence cela a-t-il sur titi ?

après avoir modifié le contenu de toto via `echo 'test' >> toto'` et qu'on utillise `cat titi` on observe que les modifications ont impactées le fichier titi. A la suppression de toto, titi reste intacte.

#### 12. Créez à présent un lien symbolique tutu sur titi avec la commande ln -s titi tutu. Modifiez le contenu de titi ; quelle conséquence pour tutu ? Et inversement ? Supprimez le fichier titi ; quelle conséquence cela a-t-il sur tutu ?

La modification de titi impacte tutu et inversement. 
