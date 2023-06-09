# Projet de stage

## Les outils mis à ma disposition 


## Outils et logiciels mis à disposition

Bien évidemment, au vu de mon sujet de stage, je ne serai pas amené à utiliser des switchs ou des routeurs ou ce genre de choses que l'on a pu pratiquer de nombreuses fois en travaux pratiques de
réseaux avancés, par exemple, mais à manipuler exclusivement grâce à un ordinateur comme en cours de virtualisation, par exemple. De ce fait, un ordinateur portable sur lequel je travaille sous 
Ubuntu 22.04 est le seul outil matériel qui m'a été fourni. En termes de logiciel, j'ai été amené à utiliser principalement Vagrant et VirtualBox.
J'ai par ailleurs utilisé d'autres outils suite aux conseils avisés de mon tuteur, tels que HedgeDoc qui me permet de mettre en page chaque jour les tâches accomplies, en donnant la possibilité par la
même occasion à mes collègues de voir mon avancée et d'apporter des modifications à ce que j'ai fait. Mais ce n'est en revanche pas le seul outil de collaboration utilisé. On m'a proposé d'utiliser 
Element afin d'échanger avec chacune des personnes présentes ou avec elles toutes en même temps, afin d'avoir des réponses rapides. L'ensemble de ces outils va me permettre de modifier le dossier
misp-vagrant qui regroupe l'ensemble des fichiers sur lesquels je dois travailler lors de mon projet.


Par conséquent, voici l'ensemble des outils que j'ai dû apprendre à utiliser :

- Vagrant: Vagrant est un outil open source qui a pour but de gérer la création et la configuration de machines virtuelles. Ainsi, il rend possible la configuration, la création et la gestion
d'environnements de développement virtuels qui permettent d'exécuter des tâches de développement et de test, de tester des applications et aussi pour toute autre manipulation requérant l'emploi de
développement stable et reproductible. C'est un outil nous permettant de créer des machines virtuelles à partir de modèles qui sont préconfigurés et que l'on appelle des box. En bref, il permet aux
utilisateurs la création simple et rapide d'un environnement de développement reproductible qui permettrait de réduire par conséquent les erreurs de configuration tout en facilitant le travail 
collaboratif.

- VirtualBox: Ce logiciel open source de virtualisation de système d'exploitation permet à notre ordinateur de créer et gérer des machines virtuelles, offrant ainsi la possibilité d'exécuter et de 
tester plusieurs systèmes d'exploitation sur une seule et unique machine physique. L'utilisateur peut donc installer différents systèmes d'exploitation tels que Linux, macOS ou encore Windows. Chacune
de ces machines virtuelles possède ses propres ressources et configurations, et aucune d'entre elles n'a accès aux fichiers pouvant être présents sur la machine hôte, ce qui signifie que les tests se 
font de manière complètement isolée.

- HedgeDoc : Cette application de prise de notes et de collaboration est un projet open source accessible via un navigateur web. Elle permet de faire de multiples choses, telles que la prise de notes 
seule ou en collaboration simultanée, étant un outil collaboratif. Elle permet également, lors de la prise de notes, la création de tableaux, de listes, de diagrammes de Gantt, d'ajouter des 
commentaires et bien d'autres fonctionnalités. C'est donc un outil de collaboration en ligne facile à utiliser et offrant de multiples fonctionnalités.

- Element : Element est un outil de communication instantanée permettant à ses utilisateurs de communiquer par appel vidéo, audio et par messagerie, que ce soit individuellement ou en groupe. Il est 
disponible sur plusieurs systèmes d'exploitation et offre des fonctionnalités avancées en termes de sécurité et de confidentialité.

- misp-vagrant : Misp-vagrant est un environnement de développement virtuel qui a été spécialement pré-configuré pour le système de prévention des incidents de sécurité informatique qu'est MISP.
Ainsi, il permet la création et l'installation locale de MISP pour le tester, bien sûr, en utilisant une machine virtuelle basée sur Vagrant, afin que cela n'affecte en rien la machine hôte.

- Langage de programmation Markdown pour rédiger mon rapport intermédiaire de stage.

J'ai bien sûr utilisé d'autres outils que je connaissais, tels que Git ou encore le langage de programmation Bash, dans lesquels j'ai quelques difficultés.

Du fait qu'il n'y a pas beaucoup de nouveaux outils matériels et/ou logiciels, instinctivement, une personne peut penser que l'apprentissage de l'utilisation de ces équipements n'est pas si compliqué,
mais c'est uniquement lorsque l'on entre dans le vif du sujet que nous mesurons la difficulté, chose que nous allons analyser directement au point suivant.

## Intitulé du projet
 
### Explication du but du projet
Voici l'intutulé de mon sujet tel qu'il m'a été présenter lorsque je faisait mon choix : “MSc Student Internship Position - Improvement of Virtualisation and Orchestration of Training Infrastructure”
qui se traduit par "Poste de stage pour étudiant en Master - Amélioration de la virtualisation et de l'orchestration de l'infrastructure de formation". Comme vous pouvez le remarquer ceci n'est pas un
sujet qui est directement adaptée à mon niveau d'études mais lors de mon choix de sujet parmis tout les sujet qui m'était proposer, ce sujet m'attirais et m'interessais plus particulièrement. Ormis le
fait que cela soit un sujet extremement intéressant, il constitue une réel défi pour moi car si j'arrive a terme de ce sujet cela serais extrêmement gratifiant et dans le cas ou le niveau serais
beaucoup trop élevé pour moi je pourrais tout de même en retenir que de bonne chose car cela m'aura permis de me dépasser en me poussant dans mes retranchements, j'aurais par la même occasion
énormément appris tant de par mes recherches que par les manipulations des différents outils qui m'est etait possible d'utiliser.
À l'écoute de l'intitulé de mon sujet on ne pas directement savoir en quoi consiste ce derniers chose que je vais maintenant vous expliquer de manière simplifier.
Il m'est confié comme mission de mettre à jour un dossier composer de plusieurs fichier de configuration, dans ce dossier son présent plusieurs fichier mais vais travailler sur deux fichier en
particulier. ce dossier se nomme Misp-Vagrant et est une petite pierre dans l'édifice qu'est MISP, MISP projet dont on à fait mention précédement et sur lequel nous allons plus longuement nous 
intéresser.

### MISP

MISP est une pateforme de partage mis en place il y a plusieurs et qui compte aujourd'hui plus de 4000 utilisateur. L'idée de l'élaboration de cette plateforme s'est fait en 2012 suite à une séance de
travail durant laquel a été remarquer le fait que plusieurs personnes au sein de ce groupe de travail trvailler sur le même logiciel malveillant. Suite à la découverte qu'il travailler tout les deux
sur le même sujet, il eu l'idée de vouloir mettre en place une plateforme leur permettant d'cahnger leur connaissance pour minimiser le temsp de travail mais aussi d'éviter la duplication.
Ainsi Christophe Vandeplas qui travailler à ce moment la au CERT pour le ministère belge de la Défense à présenter son travail qui deviendra par la suite MISP. Pour rappel Circl est une initiative
gouvernemenatal et ai donc considéré en tant que CERT ( Computer emergency response team ) dans ce pays. Par conséquent CIRCL est à la tête de cette plateforme Open source MISP et gere par conséquenr 
un bon nombre de communuté de partge MISP se basant sur le partage d'information concerant les menaces et ce de manière active.
Mais concretement c'est quoi MISP ?
Vous l'aurez bien compris au vu de mes explication précédentes que MISP est une plateforme de partage dans le domaine de la cybersécurité, ainsi il permete des partages des information sur les 
nouvelles menaces. C'est biensur un logiciel open source c'est à dire dont le code est visible publiquement pouvant etre ainsi consulté, modifier, partager par tout le monde, il facilite ainsi la 
collaboration et l'échange d'information entre plusieurs communauté nous permettant ainsi de mettre en relation nos information mais plus important encore de les enrichir. Nous n'avons pas tous les
même façons de dévellopée et de travailler te avoir un point de vu et une methode travaile externe à la notre est essentiel en informatique. Conséquement on peut releever en quelques sorte différents
groupe de divulagation d'informations, nous avons par exemple les analystes de fraude qui vont partager des indicateurs financiers afin de pouvoir relevée des fraudes finacière, nous avons aussi dans
le thème les analyste de sécurité qui ont vont pour avoir pour role de tout d'abord rechercher des indicateur biensur toujours dans un context de sécuritée opérationnelle, ils continuerons ensuite par
les valider pour ensuite bien évidement les utiliser. Je voudrais tout de même vous présenter un derniers types d'utilisateur car nous pouvons penser qu'avec les exemples que je viens de vous présenter
seulement les personnes directement liée à la cybersécuritée utilse cette plateforme mais ne perdont pas de vu le but principale de ce projet, biensur le partage d'informations mais plus précisémdent
en terme de sécurité information donc nécessairement de cybercriminalité, qui sont donc des fraudes et toute fraude doit être obligatoiremeent etre puni par la lois, ce quoi dont nous emmène à notre
troisième et derniers exemple d'utilissateur qui ne sont autres que les force de l'ordre  qui elles vont s'appuyer sur les indicateur partger par les expert en cybersécurité afin de soutenir ou encore
d'initier leur enquêtes leur perméttant de répondre de la meilleurs manière possibles aux incidents.Et A mons sens c'est à partir de ce moment la que nous voyons réellement l'aboutissement des
recherches entreprises et communiquer de ces personnes, elle participes activement à la sécrité de tous et c'est à mon sens une réel gratification pour ces que d'oeuvrer au sécurité de la population.
Car biensur les force de l'odre ne sont pas les seul organisme de confiances utilisant les services de MISP nous avons par exemple le service millitaire ou encore le secteur de la finance.


METTRE L'IMAGE DU MODEL DE GOUVERNACE DE MISP QUE L'ON RETROUVE SUR LA SLIDE 7


 

### Misp-Vagrant
### Misp-Packer

## Apport du stage


