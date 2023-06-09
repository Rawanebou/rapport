#MISP-VAGRANT

Misp-vagrant est un projet open-source qui apporte la possibilité d'effectuer le déploiement d'une instance MISP et ce de manière très rapide. Et pour cause ce projet utilise la technologie de la virtualisation dans le but de crée un environnement de déploiement virtuel prêt à l'emploie.
Poue vous expliquer concrêtement comment MISP-Vagrant se compose d'un ensemble de script et de fichier de configuration, l'ensemble de tout ces fichier vont permettre la création de machine virtuelle avce MISP directement préinstaller. 
le gros aventage de la mise en place de misp-vagrant est le gain de temps énorme pour l'utilisateur. Par conséquent la grande efficacite de cette outils permet aux utilisateur de se lancer dans un travail sur l'instance MISP sans pour autant être freiner par par la configuartion ou encore l'installation manuelle qui prend généralement du temps et qui est dans certains cas assez complexe, il leur suffira de cloner le dépot git qui à été mis en place ainsi que quelques lignes de commande. En sommes cette le but de soucis s'inscrit dans une démarche de simplification pour les utilisateurs au déploiement de MISP en fournissant une solution d'ores et déjà prête l'emploie et biensur basé sur machine virtuelle afin que cela n’affecte en rien la machine hôte.


# Qu'est ce que j'ai fait 

Maintenant que vous vous êtes familiarisé avec la notion de Misp-Vagrant voyons quelle était la liaison entre ceci est mon proejt de stage.
MISP est projet de très grande envergure, Misp-vagrant est une pierre constituant cette édifice, mais ce n'est pas le seul, et comme nous le savons les progrès informatiques son gargantuesque et surtout très rapides. Du fait de la vitesse des progès ces dernieres années, du nombre et de la complexité des projet nous n'avons pas forcément la possibilité de remttre de manière vraiment régulière l'ensemble des codes de tout les projet MISP, et c'est nottament le cas pour ce projet.
Les denières modifications sur ce projet dates d'il y déjà quatres ans, c'est pourquoi mon but est donc de remettre à jour l'ensemble des fichiers composant ce dossier chose qui à l'air très simple en apprences mais qui est beaucoup plus complexes lorsqu'on se penche sur le sujet.
voici le dépot git actuelle

METTRE IMAGE depot_git.png

Vous l'aurez compris je travaillerais principalement sur deux fichier à savoir Vagrantfile et bootstrap.sh je vais donc vous présenter quel est l'utilité de chacun de ces fichiers afin de vous expliquer les modification apporter.

# EXPLICATION DÉTAILLÉE

## Vagrantfile 

Le fichier Vagrantfile vous permet de personnaliser divers aspects de la machine virtuelle, tels que la configuration réseau, la mémoire, le nombre de CPU, les partages de dossiers, etc. Il peut également inclure des scripts de provisionnement pour installer et configurer MISP sur la machine virtuelle.


Commençons par l'explication du fichier Vagrantfile, ce dernires est un fichier offrant la possibilité à son utilisateur de procédée à la personnalisation de cerataisn aspcet concerant la machine virtuelle comme par exemple la mémoire , les partages de dossiers ou encore la configuration réseau, il inclue par ailleurs du script de provisionnement pour aboutir à l'installation et à la configuration MISP sur sa machine virtuelle.
Pour arriver à mes fins j'ai personnelement utiliser ce fichier afin de metre à jour la version d'ubuntu installer.
Pour l'avancée et la mise à jour de de Misp-vagrant je devais la mis à jour de la version d'Ubuntu devant être installer est essentiel

Ce fichier m'a permis de metrr à jour la version d'ubuntu installer et vais vous expliquer tout d'abord quelle est la version d'ubuntu installer et pourquoi devrais-je la changer, quel version a été installer et enfin comment je l'ai installer.
Tout d'abord la version d'ubuntu installer acteulemment sur ce projet est la version 18.04 qui date du mois d'avril de l'année 2018, à ce moment le grand projet MISP fonctionne en se basant sur cette version mais depuis il ya eu quelques changement et la version d'ubuntu installer en fait partie et est très importante car selon les version d'ubuntu installer la configuration et les version des outiles que l'on va installer par la suite sera susceptible de changer. La derière version d'ubuntu actuellement disponible actuellelement est la 22.04 mais bien que ce soit la dernières version installer ce n'est pas celle que nous serons ammener à installer, ce qui nous ammène par consquéquent au deuxièeme point à savoir la version installer. Malgrès le fait que la dernière version est la 22.04 nous allons intsaller la version 20.04 de ubuntu et il y a une cause à cela. Comme nous l'on précédement expliquer la version initialement installer est la version 18.04 car c'était la version qui était en corrélation avce l'ensemble du projet MISP, et c'est ici la même chose qui va se reproduire nous installons donc la version 20.04 et pas la dernières car c'est la version qui est en adéquation l'emble du grand projet. Vous vous demander donc très certainement comme pouvons nous procéder à l'intsallation de ces version et c'est le sujet de notre derniers point. Pour l'intsallation je n'ai pas procéder traditionnellement et j'entend par là le fait de rechercher sur un moteur de recherche ce que je veux installer et de l'installer directement par la suite, j'ai pour ce faire fait une modification au sein du code Vagrantfile en changeant l'image Ubuntu. Une image ubuntu se definit par la représentation numérique d'une installation complète d'Ubuntu en comprenant evidement le noyau du système,les configuration par défaut, les logiciels préinstaller et les pilotes.Donc l'appelelation d'une image varie selon la version Ubuntu voulant être installer. Voici le code permettant l'installation de la version 18.04 :
METTRE IMAGE image_ubuntu18.png
et voici maintenat le code permettant l'installtion de la version dont nouus avons besoin à savoir la 20.04 :
METTRE IMAGE image_ubuntu20.png
Mis à part ce changement un autres changement, pratique pour moi, est le changement du nom de la machine virtuelle. Du fait nombre de test effectuer avoir plusieurs machine virtuelles avec le même nom est très cintraigant c'est pourquoi le nom était toujours changer.
c'est globalement toutes les modification qui ont été faites sur ce fichier et pouvons maintenant passer au second fichier.

## Bootstrap.sh

Nous passons maintenant au fichier le plus complexe avec le plus de modification.
La complexitée de ce fichier est très facielement explicable car elle comporte la plus grande partie de la configuration, nous avons certe dans le fichier Vagrantfile mis à jour Ubuntu en le passer de 18.04 à 20.04 et nous pourrions pensée que l'on à fait une très grande partie du travaile mais c'est loin d'etre le cas. Au sein de ce deuxième document nous retrouvons l'ensemble de la configuration et de l'installation des outils essentiel au déploiement de l'instance MISP.
Comme nous l'avons précédement dis le fait de changer la version d'ubuntu installer aura nécessairement des conséquences sur les outils installer et leurs version, c'est une chose qui m'es été possible de remarqué très rapidement dès lors le début des test et manipulation que j'ai pue faire. Et pour cause ce fichier contient la configuration et l'installation d'un beau nombre d'ooutils et, comme vous vous en doutez le changement d'images, les version des outils installer ne vont plus correpondre et c'est à ce moment la que mon travaile débute.
Je dois donc pour ma part analyser pour chacun des outils isntaller le version aisni que leur configation actuelles, examiner au vu des erreurs que je recois lors de l'execution si je rencontre un problèmes et finalement modifier correctement mon script afin que tout soit en corrélation avce l'ensemble du reste du projet misp et de la version 20.04 nouvellement installer. C'est un exercice assez complexes qui demande tant d'avoir de bonne connaissance en bahs et unix scripting tout en recherchant quel sont les version adéqutates.
J'ai ainsi changer une bonne partie du code et les ai longuement tester.
Commençons par la version de php qui est installer qui est initialement la version 7.2 pour ubuntu 18.04 mais qui dorénavent la version 7.4 j'ai donc était contrainte de changer certain bout de code :

////////////////////////////////////PHP//////////////////////////////////// 
- Version_php.png
Voici les modification apporter a la configuration de php par défaut
- Conf_php.png
- Conf_php.png
plusieurs modification ont été faites ici afin d'apporter plus de fonctionnalité :
Tout d'abord il y a eu l'ajout de la première foncionnalié qui n'est autres que la validation de la valeur de configuration afin de veiller que notre valeur corresponde correctement format spécifique, c'est pour
quoi dans cas la valeur qui devrais nous être retournée suivis d'un "M"ou d'un "m". Biensur après la modification de de la un message de confirmation est retournée afin que l'on ai une idée de l'état d'avancement 
Pour continuer une vérification d'existance de nos fichier à été mis en place pour comme au vu du nom que je lui donner permettre de vérifier si les fichiers de configuration son bel et bien existant en retournant comme pour la vérification des valeurs une message selon le résultat obtenu.
enfin l'utilisation de la commande "sudo" pour l'éxecution de la commande "sed" à été nécessaire dans le cas ou l'utilisateur nécessite de privilèges afin de modifier le fichier de configuration.
- CakePHP.png 
Ici aussi plusieurs modification été apportéeet plus précisement trois : 
Tout d'abord nous avons modifier la commande "sudo -u www-data -H git submodule init" en le remplançant par "sudo -u www-data -H git submodule update --init --recursive" et ce pour permettre la mise à jour des sous-module git de CakePHP en permettant de ce fait la récupération des versions les plus récentes des sous modules pour être sur que toutes les dépendnaces sont correctement initialisées.
la deuxième modifications concernent aussi le changement d'une ligne de commande déja existante , 
nous avons modifier cette ligne de comande "sudo -u www-data -H php composer.phar install" par celle-ci "sudo -u www-data -H php composer.phar install --no-cache --no-dev" avce l'option 
"--no-cache" ayant pour but d'indiquer à composer de ne pas utiliser de cache lors de l'intallationce qui peut être pratiques pour acquérir les versions les plus récentes.
Enfin la dernière modification apporter ici est une permissions qui permettra à l'utilisateur "www-data" d'etre en mesure d'accéder et surtout d'utiliser le cache composer.

///////////////////////////////////PYTHON/////////////////////////////////////
- python.png
Ici nous installons les paquets de base et la modification apportée ici est la version de python, nous aons spécifiée que la version de python qu l'on va installer est la 3.7.

//////////////////////////////////MISP///////////////////////////////////////
J'ai par la suite relver des erreur dans le code avce des élement directeement liée à MISP 
CHERCHER DES BOUT DE CODE EN RAPPORT AVCE PHP, PRENDRE CAPTURE D'ECRAN, ET LES METTRE ICI :
- Retrieving_MISP.png
Sur ce bout de code deux fonctionnalité en essaynat tout d'abord de changer de répertoir cournat cers celui qui est spécifiée dans la variable "$PATH_TO_MISP" donc le chemin '/var/www/MISP' si cela n'aboutis pas 1 sera retourné en guise d'erreur puis nous tentons la verification afin de voir si le répertoire courant git est valide et si cele ne l'est pas biensur un message d'erreur est retournée.

- Misp_modules.png 
les modfification ici sont très simple à dicernée et à comprendre, nous avons modiffier la version des packages python installer en spécifiant que la nouvelle version de python est la version 3.7. 
puis nous avons a deux reprise dans notre code ajouté la commande sudo afin de tout simplement spécifiée qie ces commandes doivent être exécétuer en tant que root.


//////////////////////////////////MITRE'S STIX///////////////////////////////////////
- STIX.png
Nous arrivons maintenant à la partie de code qui à été à mon sens le plus modifier et vais vous expliquer en details toutes le modification qui ont ete apportée.
nous avons au tout d'abord mis à jour les paquets disponible avce a modificationb de la ligne de commande "apt-get update".
Nous avons continuer par spécifiée la version de python puis des verification portant sur l'existance de répertoir ont faite au préalable de certaines opération.
Pour continuer sur les vérification une nouvelles est faites avant de procéder au clonage des depots git afin de vérifier si la destination est la suivante"/var/www/MISP/app/files/scripts/python-cybox" puis si celui-ci existe il effectue sa suppression .
Puis le clonage des depots git de "python-cybox", "python-stix" et "mixbox" s'effectue et l'utilisation de la commande "git checkouk" va permettre au deux premier depot que j'ai citer de basuler sur une version specifique.

///////////////////////////////GALAXIES////////////////////////////////////////////
- galaxies.png
les modifications sont assez minime mais ont tout de même leur importances. 
Nous avons modifier tout d'abord l'oprion "--header" par "-H" pour bien évidement indiquer les en-têtes de requêtes mais pour apporter aussi une meilleurs lisibilité du code.
pour continuer sur les options la suivante "-o /dev/null"à été supprimer adin de spécifier la la réponse ne sera pas redirigé vers "/dev/null".
Pour finir sur les optioons, l'options "-s" pour ne plus afficher la progression et les informations supplémentaire qui s'affiche en temsp normal lors de l'éxecution de la requête.
enfin nous afons modifier "http://127.0.0.1/galaxies/update" par "http://localhost/galaxies/sync" dans le but de synchrioniser les galaxies 
 Ces modification sont semblables dans ces trois autres bout de codes :
 - taxonomies.png
 - waring_list.png
 - object_templates.png 



Pour apporter une dernières précision je voudrais vous détaillée la manière que j'avais pour travailler car, pour une personnes, n'étant pas habituer à ce gerne de travaux cela peut être quelques peut perturbant.
Pour recontectuliser, nous avons un projet qui sur lesqules nous travaillons principalement sur deux fichiers, bootstrap.sh et Vagrantfiles.
J'ai donc cloner le dépot git ou se trouve mon projet sur mon ordinateur. J'ai aussi par la même occasion installer virtualbox.
Toutes les modifications que j'ai entreprises ont été faites sur ma machine hôtes (donc bootstrap.sh et Vagrantfile) et dès lors que je voulais tester si les modifications que j'ai apporter ont fonctionner j'entrer la commande "vagrant up" pour démarrer ma machine virtuelle en se basant sur la configuration que j'ai faites sur Vagrantfile. Cela rejoins les explications que je vous avez faites au sujet de Vagrantfile ou je stipulé que ce fichier me permet de changer le nom de ma machine virtuelle, nous en avons donc la démonstration ici.
Puis j'effectuer la commane "vagrant provision" afin d'executer mon script (bootstrap.sh) ce qui me renverras tout les résultat et ce qui me permettra de cette façon de relever les erreurs et d'essayer de les résoudres.
voila une bonne description assez détaillée du travail que j'ai pue effectuer sur le projet vagrant, malgrès mes heures de travailles sur ce projet ce deniers n'a pas pue être aboutis au vu de sa grande complexité (pour mon niveau d'études) et du temps qui m'est accordée pour sa
réalisation.C'est pourquoi au cours de ma cinquièeme semaine de stage mon tuteur à décider de 
m'attribuer un autres projets qui est semblables à celui-ci mais qui est tout de même très différent et que nous allons voir sans plus attendre dans la partie suivante.





























 
































