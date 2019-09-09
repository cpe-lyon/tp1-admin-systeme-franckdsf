## Manuel

#### 1. A l’aide du manuel, identifiez le rôle de la commande which

La commande `which` a pour role de localiser une commande, un binaire. En clair, elle permet d'identifier la version d'une commande ou d'un programme.

#### 2. Quand on consulte cette page, comment peut-on rechercher, par exemple, le mot option ?

il faut appuyer sur `/` puis écrire `option` <br>
commande : `/option`

#### 3. Comment quitte-t-on le manuel ?

il suffit d'appuyer sur la touche `q`.

#### 4. Chaque section du manuel a une première page, qui présente le contenu de la section. Afficher la première page de la section 6 ; de quoi parle cette section ?

la commande `man 6 intro` permet d'afficher la première page de la section 6 du manuel.

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

la commande `sudo cd /root` éxige un mot de passe. En effet sudo signife l'éxecution d'une commande en tant qu'administrateur. Elle permet à un utilisateur lambda d'executer une commande administrateur. Pour cela, un mot de passe administrateur est requis. Une fois le mot de passe rempli, la commande s'execute

#### 7. à partir de votre dossier personnel, créez l’arborescence suivante :

tutoriel : 
-`mkdir Dossier1` <br>
-`touch Dossier1/Fichier1` <br>
-`mkdir Dossier2` <br>
-`cd Dossier2` <br>
-`mkdir -p Dossier2.{1,2}` <br>
-`cd Dossier2.2` <br>
-`touch Fichier{2,3}` <br>
