<p align="center">
    <img height="100px" src="Images/Bash.png">
</p>
<div align="center">
    <h2>Apprendre le Bash par @colasnaudi</h2>
</div>

## Table des matières
<!--ts-->
   * [Commandes de bases](#commandes-de-bases)
      * [Se déplacer](##se-déplacer)
      * [Afficher l'endroit où l'on se trouve](##afficher-l-endroit-où-l-on-se-trouve)
      * [Commande ls](##commande-ls)
      * [Créer un fichier/dossier](##créer-un-fichier/dossier)
      * [Déplacer un fichier](##déplacer-un-fichier)
      * [Copier un fichier](##copier-un-fichier)
      * [Supprimer un fichier/dossier](##supprimer-un-fichier/dossier)
      * [Attribuer les droits à un fichier/dossier](##supprimer-un-fichier/dossier)
      * [Afficher les processus en cours](##afficher-les-processus-en-cours)
      * [Trouver un fichier](##trouver-un-fichier)
      * [Commande >](##commande->)
      * [Commande who](##commande-who)
      * [Commande top](##commande-top)
      * [Commande cat](##commande-cat)
      * [Commande more](##commande-more)
      * [Commande head](##commande-head)
      * [Commande tail](##commande-tail)
      * [Commande grep](##commande-grep)
      * [Effacer le terminal](##effacer-le-terminal)
   * [Script Shell](#script-shell)
      * [Créer le fichier](##créer-le-fichier)
      * [Exécuter le script](##exécuter-le-script)
      * [En-tête du script](##sen-tête-du-script)
      * [Commande echo](##commande-echo)
      * [Arguments](##arguments)
      * [Comparateurs](##comparateurs)
      * [Déclarer variable](##déclarer-variable)
      * [Expression](##expression)
      * [Commande read](##commande-read)
      * [Fonctions](##fonctions)
      * [Commande sed)](##commande-sed)
      * [Boucles](##boucles)
      * [Conditions](##conditions)
      * [Utiles](##utiles)
   * [Scripts](#scripts)
<!--te-->


# Commandes de bases

## Se déplacer
```bash
cd  #Aller au chemin indiqué après cd
cd ~    #Aller à la racine du répertoire
```

## Afficher l'endroit où l'on se trouve
```bash
pwd     #Affiche l'endoit où l'on se trouve
```

## Commande ls
```bash
ls      #Affiche l'arborescence du dossier dans lequel on est
ls -l   #Affiche les droits des dossiers/fichiers du dossier dans lequel on est
```

## Créer un fichier/dossier
```bash
touch   #Créer un fichier
mkdir   #Créer un dossier
```

## Déplacer un fichier
```bash
mv      #Déplacer un fichier
```

## Copier un fichier
```bash
cp      #Copier un fichier
```

## Supprimer un fichier/dossier
```bash
rm      #Supprimer un fichier ou dossier vide
rm -r   #Supprimer un dossier et ce qu'il contient
```

## Attribuer les droits à un fichier/dossier
```bash
chmod   #Attribuer les droits à un dossier/fichier
```

## Afficher les processus en cours
```bash
ps      #Affiche les processus en cours sur la machine et leurs PID
kill    #Fermer un processus en cours d'éxecution
killall nomProcessus    #Ferme tout les processus ayant ce nom
```

## Trouver un fichier
```bash
find -name      #Affiche le chemin où se trouve le fichier
```

## Commande >
```bash
ls > repertoire     #Créer un fichier répertoire contenant une ligne, l'arborescence du dossier dans lequel on est
```

## Commande who
```bash
who     #Affiche une liste des utilisateurs actuellement connectés à l'ordinateur.
```

## Commande top
```bash
top     #Afficher les tâches
```

## Commande cat
```bash
cat     #Afficher le contenu d'un fichier
```

## Commande more
```bash
more    #Permet de voir du texte page par page
```

## Commande head
```bash
head        #Afficher par défaut les 10 premières lignes du fichier
head -nA    #Affiche les A premières lignes du fichier
```

## Commande tail
```bash
tail -nA    #Affiche les A dernières lignes du fichier
tail -n+A   #Affiche de la ligne A à la fin du fichier
```

## Commande grep
```bash
grep chaine nom_fichier     #Recherche une chaine de cracatères dans un fichier
```

## Effacer le terminal
```bash
clear   #Effacer le terminal
```

# Script Shell

## Créer le fichier
```bash
touch nomFichier.sh
```

## Exécuter le script
```bash
./nomFichier.sh
sh nomFichier.sh
source nom_fichier.sh; fonction arg1 arg2 arg3
```

## En-tête du script
```bash
#!/bin/bash
```

## Commande echo
```bash
echo "Hello World!"     #Affiche Hello World!
``` 

## Arguments
```bash
$1      #Premier argument
$N      #N-ième argument
$#      #Nombre total d'arguments
```

## Comparateurs
```bash
-eq     #Est égal à
-ne     #N'est pas égal à     
-gt     #Est plus grand que
-ge     #Est plus grand ou égal à
-lt     #Est plus petit que
-le     #Est plus petit ou égal à
```

## Déclarer variable
```bash
declare -a list=("Un" "Deux" "Trois" "Quatre" "Cinq" "Six" "Sept" "Huit" "Neuf" "Dix")      #Tableau
declare -f nom_fonction      #Fonction
declare -i var=5      #Entier
```

## Expression
```bash
let "nbr1=nbr1*3"       #nbr1 <- nbr1 * 3
let "nbr2=nbr1%2"       #nbr2 <- nb1 modulo 2
```

## Commande read
```bash
read variable? "Message à afficher"
read -p "Message à afficher" variable
echo $variable          #Affiche ce que l'utilisateur à saisi
```

## Fonctions
```bash
#Définition fonction
function nom_fonction {
   #Code
}

#Appel de la fonction
nom_function arg1 arg2
```

## Commande sed
```bash
#####################
#   Remplacer les -ET- en &   #
#####################
sed 's/-ET-/ \& /g' texteSource.txt > texteModifie.txt

###########################
#   Ne pas afficher les lignes 2 à 4   #
###########################
sed '2,4 d' Exercice2.txt > test2-5.txt

###########################
#   Supprimer les lignes contenant 30  #
###########################
sed '/30/d' Exercice2.txt > test2-6.txt

###############################
#  Supprimer les lignes ne contenant pas 20  #
###############################
sed '/20/!d' Exercice2.txt > test2-7.txt

###########################################
##   Remplacer les lettres < / > par une virgule et les       ##
##   caractères < ; > par un < @ > en une seule commande sed  ##
###########################################
sed 's# /#,#g; s/;/@/g' Exercice2.txt > test2-4.txt

############################################
#   Remplacer les lettres < t > en début de ligne par un < T >   #
############################################
sed 's/^t/T/'  Exercice2.txt > test2-2.txt

```

## Boucles
```bash
################
#     Boucle while     #
################
while (( test )) ; do
#Code
done

################################
#   Boucle for avec nombre d'itération connu   # 
################################
for (( i=0; i<=5; i++ )) ; do  
#Code
done

################
#      Même chose      #
################
for i in {1..5} ; do
#Code
done

################
#    Boucle infinie    #
################
for (( ; ; )) ; do
#Code
done

```

## Conditions
```bash
################
#       If else        #
################
if [ test ]; then
#Code
fi

################
#     If elif else     #
################
if [ test ] ; then
#Code
elif [ test ] ; then
#Code
else
#Code
fi

################
#        Switch        #
################
case word in
   pattern1)
      Statement(s) to be executed if pattern1 matches
      ;;
   pattern2)
      Statement(s) to be executed if pattern2 matches
      ;;
   pattern3)
      Statement(s) to be executed if pattern3 matches
      ;;
   *)
     Default condition to be executed
     ;;
esac
``` 

## Utiles
```bash
# Si le dossier nom_dossier n'existe pas on le crée
function create {
    if [ ! -d "nom_dossier" ]; then
    mkdir nom_dossier
    fi
}

# Récupération de l'extension du paramètre
extension=".${argument##*.}"
# Récupération du nom du paramètre avant l'extension
nomFichier="${argument%%.*}"
```

# Scripts

### La fonction `argmin`
> Cette fonction lorqu'elle est appelée, regarde le nombre d'argument(s) passé(s) en paramètre, si ce nombre est inférieur à 2, la fonction retournera le nombre d'arguments manquants pour arriver à 2 et si le nombre d'arguments est supérieur à 2, alors la fontion retournera le nombre d'arguments passés en paramètre.

```sh
function argMin() {
    if [ $# -lt 2 ];
    then
        echo $((2 - $#)) "arguments missing"
    else
        echo Il y a $# arguments
    fi
```
#### Exemple d'appel
```sh
argmin arg1 arg2
```

### La fonction `supBot`
> Cette fonction, selon le deuxième argument entré permet de supprimer les fichier .bak `-b`, .old `-o`, .~ `-t`ou tous `-a` du dossier entré en premier argument.

```sh
function supBot() {
    if [ $2 == "-a" ]
    then
            rm -r $1/*.bak
            rm -r $1/*.old
            rm -r $1/*~
    elif [ $2 == "-b" ]
    then
            rm -r $1/*.bak
    elif [ $2 == "-o" ]
    then
            rm -r $1/*.old
    elif [ $2 == "-t" ]
    then
            rm -r $1/*~
    fi
}
```

#### Exemple d'appel
```sh
supBot ./test -t
```

### La fonction `ficNumbered`
> Cette fonction crée un dossier Exo3 dans l'emplacement actuel et y crée 10 fichiers nommés 'Un', 'Deux'... avec dans chacun une ligne écrite, pour le fichier 'Un' il y a 'Première ligne', pour le fichier 'Deux' il y a 'Deuxième ligne'.

```sh
function ficNumbered() {
    mkdir Exo3

    declare -a list=("Un" "Deux" "Trois" "Quatre" "Cinq" "Six" "Sept" "Huit" "Neuf" "Dix")
    listText=("Premiere" "Deuxieme" "Troisieme" "Quatrieme" "Cinquieme" "Sixieme" "Septieme" "Huitieme" "Neuvieme" "Dixieme")

    for i in {0..9}
    do
        touch Exo3/${list[$i]}.txt
        echo ${listText[$i]} ligne > Exo3/${list[$i]}.txt
    done
}
```

#### Exemple d'appel
```sh
ficNumbered
```

### La fonction `verifNote`
> Cette fonction affiche une appréciation en fonction de la note entrée.

```sh
function verifNote() {
    echo "Entrer votre note : "
    read -r note

    if [ "$note" -ge 16 ] ; then
        echo "très bien !!"
    elif [ "$note" -ge 14 ] ; then
        echo "bien !"
    elif [ "$note" -ge 12 ] ; then
        echo "assez bien :)"
    elif [ "$note" -ge 10 ] ; then
        echo "moyen"
    else
        echo "insuffisant :("
    fi
}
```

#### Exemple d'appel
```sh
verifNote
```

### La fonction `puissance`
> Cette fonction affiche le résultat du nombre entré à sa propre puissance.

```sh
function puissance() {
    somme=1
    read -p 'Entrer un nombre : ' n
    for (( i=1; i <= $n; i++ ))
    do
        somme=$(($somme*$n))
    done
    echo $n puissance $n est egal à $somme
}
```

#### Exemple d'appel
```sh
puissance
```

### La fonction `dossierNum`
> Cette fonction crée un dossier du nom de l'argument 1 puis y insère 10 dossiers numérotés à l'intérieur.

```sh
function dossierNum() {
    # Si le dossier n'existe pas, on le crée
    if [ ! -d $1 ] ; then
    mkdir $1
    fi

    # Boucle de 1 à 1O qui crée les 10 dossiers numérotés dans le premier
    for ((i=1; i<=10; i++))
    do
        # Si le dossier n'existe pas on le crée
        if [ ! -d "$1/$1$i" ] ; then
            mkdir "$1/$1$i"
        fi
    done
}
```

#### Exemple d'appel
```sh
dossierNum test0
```

### La fonction `sauvegarde`
> Cette fonction crée un dossier sauvegarde dans le repertoire racine s'il 'existe pas déjà, y crée s'il y a une extension le fichier demandé, sinon le dossier demandé. Si le nom est déjà utilisé il sera créé et numéroté. À la fin le nom du/des fichier(s)/dossier(s) créé(s) seront affiché(s).

```sh
function sauvegarde() {
    # Si le dossier n'existe pas on le crée
    if [ ! -d ~/"sauvegarde" ]; then
        mkdir ~/sauvegarde
    fi

    # Remise des droits d'écriture sur le répertoire sauvegarde
    chmod 700 ~/sauvegarde

    # Determiner si c'est un fichier ou un dossier
    for argument in $@
    do
        # Récupération de l'extension du paramètre
        extension=".${argument##*.}"
        # Récupération du nom du fichier/dossier
        nomFichier="${argument%%.*}"
        #Traitement des dossiers
        if [[ $extension == ".$nomFichier" ]] ; then
            # Si le dossier n'existe pas dans le dossier sauvegarde on le crée
            if [ ! -e ~/sauvegarde/$nomFichier ]; then
                mkdir ~/sauvegarde/$nomFichier
            else
                # Initialisation du compteur
                declare -i compt=0
                for (( ; ; )) ; do
                    let "compt=compt+1"
                    # Si le nom du dossier + compteur n'existe pas on le crée
                    if [ ! -e ~/sauvegarde/$nomFichier$compt ]; then
                        mkdir ~/sauvegarde/$nomFichier$compt
                        break
                    fi
                    #Sinon le compteur prend +1 et réessaye
                done
            fi
            echo "Dossier sauvegarder sous le nom" $nomFichier$compt
        else    # Traitement des fichiers
            #Si le fichier n'existe pas dans le dossier sauvegarde on le crée
            if [ ! -e ~/sauvegarde/$nomFichier$extension ]; then
                touch ~/sauvegarde/$nomFichier$extension
            else
                # Initialisation du compteur
                declare -i compt=0
                for (( ; ; )) ; do
                    let "compt=compt+1"
                    # Si le nom du fichier + compteur n'existe pas on le crée
                    if [ ! -e ~/sauvegarde/$nomFichier$compt$extension ]; then
                        touch ~/sauvegarde/$nomFichier$compt$extension
                        break
                    fi
                    #Sinon le compteur prend +1 et réessaye
                done
            fi
            echo "Fichier sauvegardé sous le nom" $nomFichier$compt$extension
        fi
    done

    # Suppression des droits d'écriture sur le dossier sauvegarde
    chmod 500 ~/sauvegarde
}
```

#### Exemple d'appel
```sh
sauvegarde fichier.txt dossier
```

### La fonction `afficheShift`
> Cette fonction affiche tous les arguments à l'aide de la fonction `shift`

```sh
function afficheShift() {
    tour=$#
    for (( i = 0; i < $tour; i++ )) ; do
        echo $1
        shift
    done
}
```

#### Exemple d'appel
```sh
afficheShift arg1 arg2 arg3 arg4
```