Admin système : TP 1
Emilio Maldonado
---
#### Exercie 1
Installation d'Ubuntu Server réussie
#### Exercice 2
###### Manuel :
1. La commande pour faire appel au manuel est "man" [commande]. ```man which``` nous dit que cette commande permet d'avoir le fullpath d'un fichier (chemin d'accès complet).
2. Pour rechercher dans une page du manuel il suffit de rechercher la page (en tapant par exemple ```man which```), puis une fois dans la page, il suffit de taper ```/``` puis le terme recherché (par exemple ```/option```).
3. Pour quitter le manuel il suffit de taper sur la touche **q**.
4. Cette section parle des jeux et autres petits programmes "funs" inclus dans l'OS.
######Navigation dans l'arborescence de fichier :

1. ```cd /var/log```.
2. Il suffit de taper ```cd ..```.
3. Retour dossier précédent : ```cd -```.
4. Pour accéder au dossier personnel il suffit de taper ```cd ~```, on peut également y accéder en tapant ```cd /home/*login*```.
5. En tapant simplement ```cd /root``` le terminal nous renvoie une erreur : *permission denied*.
6. Le terminal nous renvoie : *sudo: cd: command not found*. Cela s'explique par le fait que ```sudo``` sert à lancer des fichier binaires alors que ```cd``` est inclus dans shell, ainsi ```sudo``` ne trouvent pas de commande ```cd```.
7. Liste des commandes à taper (dans l'ordre) :
    * ```cd ~```
    * ```mkdir Dossier1```
    * ```mkdir Dossier2```
    * ```cd Dossier1```
    * ```touch Fichier1```
    * ```cd ~/Dossier2```
    * ```mkdir Dossier2.1```
    * ```mkdir Dossier2.2```
    * ```cd Dossier2.2```
    * ```touch Fichier2```
    * ```touch Fichier3```
8. ```rm Fichier1``` fonctionne bien si lancée depuis *Dossier1* (suffit de taper Dossier1/Fichier1 pour lancé depuis ~). ```rm Dossier1``` nous renvoie *rm: cannot remove: 'Dossier1' is a directory*. En effet la commande ```rm``` supprime les fichiers par les dossiers (```rmdir``` pour supprimer les dossiers).
9. Réponse ci-dessus **↑**.
10. Le terminal nous renvoie *failed to remove: Directory is not empty*
11. Il faut utiiser la suppression recursive : ```rm -r <nom du dossier>```.
###### Commandes importantes :
1. Pour afficher l'heure : ```date```. La commande ```time``` permet de savoir combien de temps un programme met à s'éxécuter.
2. Les fichiers avec un nom commençant par un **.** sont des fichiers cachés (```la = ls -a```).
3. ```whereis ls``` → usr/bin/ls.
4. ```ll = ls -alf```.
5. Il suffit de taper ```ls /bin```.
6. ```ls ..``` permet d'afficher le contenu du dossier parent.
7. Chemin complet dossier courant : ```pwd```.
8. ```echo 'yo' > plop``` crée le fichier *plop* si il n'existe pas puis écrit *yo* dedans. A la deuxième éxécution, réécris *yo* par dessus dans *plop*.
9. ```echo 'yo' >> plop``` crée le fichier *plop* si il n'existe pas puis écrit *yo* dedans. A la deuxième éxécution, réécris *yo* à la suite dans le fichier.
10. ```file <nom-du-fichier>``` permet d'afficher le type du fichier ainsi que quelques caractéristiques spécifiques.
11. Quand on modifie *toto*, *titi* est aussi modfié.  
Pour la suppression, *toto* est supprimé et *titi* reste.
12. Quand on modifie *titi*, *tutu* est aussi modfié.  
Quand on supprime *titi*, *tutu* est toujours visible mais on ne peut plus le consulter.
13. ```CTRL + S``` : stop le défilement.
```CTRL + Q```: reprend le défilement.
14. ```head -n 5 /var/log/syslog``` pour afficher les 5 premières et ainsi de suite.
    ```tail -n 15 /var/log/syslog``` 
    ```head -n 20 /var/log/syslog | tail -n 11```.
15. ```dmesg | less``` affiche les messages du kernel page par page.
16. Contient des informations sur les utilisateurs.  Commande : ```man /etc/passwd```.
17. ```cat /etc/passwd | cut -d":" -f 1 | sort```.
18. ```cat /etc/passwd | wc -l``` (compte le nombre de ligne de ```/etc/passwd``` car 1 ligne = 1 compte).
19. ```man -k conversion | wc -l``` &rarr; 45.
20. ```sudo find / -name passwd```.
21. ```sudo find / -name passwd > ~/list_passwd > ~/list_passwd.txt 2>/dev/null```.
22. 
23. Pour localiser ```history.log``` :  
    ```
    locate history.log 
    /var/log/apt/history.log
    ```
24. ```locate fichier``` ne trouve pas le fichier nouvellement créé car on n'a pas fait de ```sudo updatedb``` pour réindexer tous les fichiers

#### Exercice 3 : Découverte de l'éditeur nano

1. *rien à faire*

2. ```CTRL+\ ``` pour le raccourci "remplacer" et entrer les mots correspondants
3. 
4. et 5. ```CTRL+X``` pour quitter *(si il y a des modifs, nano propose d'enregistrer ou non)*

#### Exercice 4 : Personnalisation du shell

3 et 4. ```PS1='\[\033[35m\][\A]-${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[36m\]\w\[\033[00m\]\$ '```