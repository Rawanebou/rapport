Maintenant que nous avons fait une études détaillée sur le projet Misp-Vagrant passons à l'analyse du second projet qui à été étudier et cette fois réussi à être fini. Pour ce faire nous allons tout d'abord chercher savoir qu'est-ce que Misp-packer et nius contunerosn par expliquer ce qui m'a été possible de faire et enfin les modifications que j'ai apportée dans ce projet.

Misp-packer comme l'outils présenter précédement est un projet open-sources mis en place assurément par l'équipe qui s'occupe du projet MISP. Ce derniers à pour utilité la creation d'image virtuelle qui sont préalablement configurée qui contient l'installation de MISP prête à l'emplois et prend en charge plusieurs plateforme de virtualisation tel de VMWare, VirtualBox et bien d'autre encore.
Du fait de l'utilisation de cette outils et de la création d'images virtuelles MISP étant au préable déjà prête la manipulation ainsi que toutes les configuation manuelle ne seront pas utiles 
car tout aura été auparavant fait permettant ainsi un déploiment très rapide de MISP. 
Afin de spécifier les paramètre de son images virtuelle Misp packer va utiliser des fichier de configuration là ou d'autres distribution on par exemple utilisert des certifocat SSL, des packages à installer ou encore des clés API par exemple. Ainsi la configuration de cette outils est beaucoup plus simple et nous pouvons même changer l'image en ajoutant ou tout simplement en modifiant un script déjà existant.
Pour conclure nous pourrions definir ce projet comme un moyen de faciliter d'accélérer le déploiment de MIPS en créant des images virtuelles configuré préalablement et en fournissant une installation completes prête à l'installation pour que l'utilisateur n'est pas à faire l'ensemble des manipulation manuellement.


# Qu'est ce que j'ai fait 

Les bases poser et les termes éclairicis nous pouvons dès à présent mettre les pieds dans le plat.
Nous disons souvents que "Les petits ruisseaux font les grandes rivières" et vous l'aurez très bien assimilée au vu de l'avancée de votre de votre lecture que les projet que j'ai entrepris sont en rapport avec le projet MISP. Il à été pour très gratifiant de contribuer à ce grand projet et ce même si les projets entrepris sont minimes en comparaison à l'imposance de ce grand projet car chaques maillon de la chaines compte et passons sans plus tarder à l'explication dans les grandes lignes de ce j'ai pue faire pour ce travail pour passer à une explication détailler de ce j'ai fait.

Pour mener à aboutissement ce projet j'ai décider de fonctionner de la mêmem manière dont j'ai procéder depuis le début de mon stage, j'ai donc découper l'oganisation de mon travail en trois partie. J'ai tout d'abord entrepris des recherches pour en savoir d'avanatages sur le sujet dans le but de partir sur des bases solides qui me permettrons de répondre à mes propres questions sans grand soucis. Par la suite je suis passer à la phase de teste ce qui consiste à faire des changements à plusieurs endroits dans plusieurs fichiers afin de voir ce qui peut m'être retournée c'est ainsi le moment de faire le plus de manipulation possibles afin d'analyser le plus de possibilités. Enfin je finis par la phases purement pratiques qui me permettra d'alier les connaissance que j'ai pu accumuler lors de mes recherches ainsi que celle lors de la phase de test qui me guidera dans le fait des choses à faire ou non. Contrairement au projet précédent je ne travaille principalement sur un ou deux fichier de configuation mais sur plusieurs, je dois donc avoir une assez bonne connaissance de chacun des fichiers que je serais mener à utiliser ou non mais le but reste tout de même pareil à savoir la mise à jour de l'ensemble des fichiers.
Pour finir je voudrais apporter une clarification de la manière dont ja'ai été amner à travailler pour que vous puissiez vous faire une idée plus précise.
J'ai besoin pour la réalisation de ce travail indubitablement de VirtualBox. J'ai tout d'abord cloner le dépot git du projet déjà existante sur mon ordinateur, je vais ensuite apporter des modification toujours sur ma machines hôtes et dès lors que je décide de tester ces modifications j'éxécute la commande "bash build_vbox.sh" et ce toujours sur ma machine hôte puis lorsque l'éxécution de mon travail est terminer c'est seulement à ce moment que je suis ammener à utiliser la machine pour simplement voir si les modification que j'ai apporter on abboutis.


Après ce cours préambule nous pouvons passez à une explication plus précise des modifications apportée et pour ce faire nous allons analyser le code initial et les changements apporter mais surtout dans quel but elle ont été apporter 

# EXPLICATION DÉTAILLÉE

//////////////////////////CONFIG.SH///////////////////////////////
- METTRE config.png

La seul et uniques modification qui à son importance dans ce code à pour but la modification de la version d'Ubuntu que l'on va utiliser au moment de la création de l'image virtuellle. Pour se faire  j'ai donc ajouter la variable  " UBUNTU_VERSION="20.04" ", l'ajout de cette variable va permrettre l'indiquation que c'est la version que l'ont a spécifier qui doit etre 
employer lrs de la création de l'image à savoir ici la version 20.04. Ainsi cette modification participe activement à la mise à jour de la version de Ubuntu.



//////////////////////////MISP.JSON//////////////////////////////
Il ya eu dans ce fichier beaucoup de modification ,mais tout ne sont pas crutial, pratiquement l'entièreté de ce code a été modifier dans le but de rendre plus agréables à lire et nous ne nous attarderons pas sur ce ces modification mais analyserons que celle qui sont réelement importante lors de l'execution de notre code.
 Voici les modification qui sont importante dans ce code :
- METTRE misp1.png
 
La première modification à pour but la modification du nom de l'ISO que l'on va utiliser pour la nouvelle version d'ubuntu qui sera installer. Nous sommes ainsi passer de "iso_name": "ubuntu-18.04.6-server-amd64.iso", à "iso_name": "ubuntu-20.04.6-server-amd64.iso". Nous notifions ici précisement que nous passon de la version 18.04.6 d'Ubuntu à la version 20.04.6.
La seconde modification apportée ici est la valeur "iso_url" qui indique comme le nom l'indiques l'URL de la version de l'ISO que nous souhaitons télécharger. En corrélation avec le nom de l'ISO qui a été passer d'une version à une autres nous passons de la version de la version 18.04.6 installer à la version 20.04.6. 
Ces modification sont crutial à la mise à jour de la version ubuntu installer car comme expliquer précédement la ou les autres distrubution impose d'installer des packages et bine d'autre choses, nous avonsi ici normalement besoin de télevharger l'image ISO de la version que m'on désire pour que tout puisse se mettre à jour selon notre convenance.


///////////////////////INTERFACE.SH/////////////////////////////

- METTRE interface.png

Ici la modification est minime mais à tout de même son importance. Nous avons remplacer la commande "sed" et avons ajouter l'option "-i" à cette commande soit "sed -i". La rasion pour laquel cette modification à été faites est qu'initialement elle était pour apporter des modification dans le fichier précis à savoir "etc/default/grub" mais devais obligatoirement se soumettre à l'utilisation de la redirection avec "tee" qui est une commande permmetant de prendre la sortie d'une commande afin de la rediriger vers un fichers en affichant simultanément celle ci à l'écran.
L'utilisation de cette option va tout simplement va donner la possibilité de modification direct du fichier citée précédement sans exiger une redirection.


//////////////////////USERS.SH////////////////////////////////

-METTRE users.png

Plus de modification on l'air d'avoir été apporter dans ce script en comparaison avec les dernires que l'ont a pue analyser mais ce n'est pas réélement le cas car au total nous avons deux modification réellement importantes. Des lignes de codes permttant de creer un utilisateur que l'on nomme "thehive" on été commenter et ai choisi de les décommenter afin de permettre la creation de cette utilisateur ainsi avec par la même occasion la configuration d'un mot de passe "thehive1234" et en donnant enfin l'ajout de la commande sudo elle va permettre à cet utilisateur aisni qu'a l'utilisateur misp de pouvoir utilser des lignes de commande en mode privilèges sans avoir besoin d'entrer de mot de passe. Nous avons ensuite mis à jour le système de manière complete en éxécutant les deux commandes "apt update" et "apt upgrade -y" puis nous avons mis à niveau de notre version d'ubuntu  en utilisant la commande  "do-release-upgrade -f DistUpgradeViewNonInteractive" qui va elle tout simplement faire passer la version d'ubuntu actuellement installer à la version 20.04 


//////////////////////UPLOAD.SH///////////////////////////////

- METTRE upload.sh ( en annexe ) (faire pareil avec les fichier 
Comme pour l'exemple précédents nous avons l'impression qu'un grand nombre de modification ont été apportée et nous nous redons compte qu'elle ne sont pas ni nombreuse mais tout autant efficaces.
Les modification ici on été apporter à un fin bien précis, celui de remplacer la commande wget par la commande curl. Pour ce faire nous avons tout d'abord procédée à la mise à jour des paquets biensur avec la commande "apt-get update" puis sommes directement passer à l'installation de curl avec la commande "apt-get install -y curl". Nous avons par la suite utilisé cette commande "curl "$GITHUB_OAUTH_BASIC" --data-binary @"$filename" -H "Authorization: token $github_api_token" -H "Content-Type: application/octet-stream" $GH_ASSET" pour tout simplementd donnée la possibilitée à curl de telecharger et de réaliser des actions qui sont en rapport avec GitHub.

DIRE POUR LA MISE À JOUR DES OUTILS 


///////////////////COMMENT JE SAIS QUE J'AI RÉUSSI////////////

Mon but était de mettre à jour la version d'ubuntu ainsi que les outils devant être installer pour le déploiement de misp. Lorsque j'executer mon code sur ma machine hôte cela générer automatiquement une machine vitrtuelle. Lorsque cette machine virtuelle était lancer le but pour moi était que la version d'Ubuntu 20.04 soit directement installer et que la version des outils soit la bonne. Lors du lancement de ma machine virtuelle une adresse IP devais être automatique afficher ( avec un text par la suite ainsi que la nomination des port ). Cette addresse IP devais me permettre de me permettree de me loger dans le MISP en entrant l'adresse suivante "http://adresse_IP_apparue_sur_ma_machine_virtuelle".
lorsque j'était en mesure d'accéder à MISP via cette adresse IP je pouvais me connecter grâce à un identifiant et un mot de passe par défaut puis devais changer mon mots de passer et accéder à MISP.
Lorsque tout ceci fonctionne correctement, le projet à été terminer pour moi.



# DIFFICULTÉS

Alexander Graham Bell à dit "la diffculté réside souvent dans les détails.", et c'est une choses qui m'est été pleienement possible de remarquer au vu de mon experience et de mon sujets lors de ces deux mois de stage. Ce projet étant réellement abboutis je me sent apte à pouvoir exposer les difficultés que j'ai pu rencontrer lors de ce projet et commençons directement pas la mise à jour de la version Ubuntu installer. Ayant travailler tout d'abord sur misp-vagrant cette mise à jour de version n'a pas été personnelement compliquée à mettre en place car, j'avais une image avec un nom bien précis que j'ai changer et le tour était jouer. En commençant à travailler sur ce deuxième outils je suis partie du même principe et ai très vite penser que pour passez à la version 20.04 il fallais que je change simplement le "iso_name" et surtout le "iso_url" ( dont je vous ai parler dans mon explication sur le fichier misp.json). Mais j'ai vite compris que cela ne suffisait pas et devais de ce fait changer plusieurs ligne de code dans plusieurs fichiers et y est finalement parvenu. La deuxièeme "difficulté" que je nommerais plus comme un contrainte et le temps d'éxecution de mon code qui était estimer à plus de 25min en moyennes, ce qui à pour conséquences de me faire "perde" un certain temps qui était tout de même utiliser à bon escient. Du fait du temps d'éxecution de mon programme je devais essayer donc de minimiser les test en étant la plus efficace possibles dans le choix de mes modifications. Mais comme diraist William Shakespear "Les diffultés sont faites pour être surmontées",chose qui à été faites. 





































































