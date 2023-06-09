#RAPPORT FINAL


## Remerciements

Avant de commencer à rentrer dans le vive du sujet de mon satge je tenais à présenter mes
remerciement et ma gratitude envers un certains nombre de personnes.Je voudrais tout d'abord 
présenter mes remerciement et ma reconnaisance à mon tuteur de stage Mr.Alexandre Dulaunoy qui à 
qui m'accompagené de la meilleurs des façons durant ma periode de stage dans l'entreprise CIRCL
(Computer Incident Response Center Luxembourg) . Sa manière de travailler et sa manière de me suivre
à été à mon sens optimal pour le bon déroulement de cette experience, il à sue me venir en aide tout
en se mettant en retrait afin de me donner la possibilité d'en apprendre un maximum sur les outils
que j'utiliser et selon moi cela à été la meilleurs manière d'entreprendre les choses.
Je voudrais aussi remercier l'ensemble du groupe CIRCL qui m'ont extremement bien acceuillis
en me donnant directement l'impression de faire partie de leur equipe en n'hesitant pas de la même
façons que mon tuteur à me venir en aide par moment.Leur amabilité, leur cohésion d'equipe et leur
hospitalitée m'ont permis directement de me sentir à l'aise et de travailler dans une bonne
ambiance, chose primordiale au vu du temps qui va etre passer dans les locaux avec
ces même personnes .Je tiens à remercier mon proffesseur Mr.Romain Jager qui endosse le rôle de
tuteur de stage à l'IUT. Ayant suivis ses enseigenements durant l'année je suis très
reconnaisssante de présenter ma soutenance devant un proffeseur que j'admire pour ses methodes d'enseigements
et sa volonté de faire réussir ses élèves. Pour continuer sur les proffesseur qui me tenais à coeur de remercier nous avons
Mme. Marie-Aimee Coquillat qui à entreprit un travail constant sur tout le long de l'année et m'a beaucoup aider lors de ma 
recherche de stage , Mr.Pierre Laroche qui à assurer toute les procédure administrative très rapidement et très efficacement tout 
en répondant à toute les question que l'ont se poser lors du remplissage des différents formulaire chose que j'ai eu la chance de retrouver aussi au sein de mon entreprise 
grace à Mme.Rita Bressanutti qui n'a pas héister à me donner des indications sur le fonctionnement de l'entreprise, à me faire visiter les locaux et à veiller que tout 
se passe bien pour moi chose pour les-quels je lui suis énormément reconnaissante. Enfin pour finir je tenais
biensur à remercier Mme.Anne Spengler qui prend à coeur de suivre chacun de ses étudiants et qui travail dur depuis notre rentrée
en première année pour nous faciliter au plus l'entrée dans cette nouvelle réforme du Bachelor Universitaire de Techenologie (BUT) 
anciènement Diplome Universitaire de Technologie (DUT).
Nous pouvons ,après avoir passer ce point important,entrez dans le vive du sujet.

#L'ENTREPRISE 

 
### Qui est CIRCL ?
 
L'entreprise Computer Incident Response Center, également appelée CIRCL, est une initiative gouvernementale lancée en 2012 par le gouvernement luxembourgeois dans le but de proposer un service de
réponse aux menaces de sécurité informatique pour les entités non gouvernementales, les entreprises privées et les collectivités, afin de minimiser les pertes potentielles liées à ces attaques.
Cette organisation est gérée par SMILE (Security Made in Lëtzebuerg), une initiative publique et privée visant à promouvoir la sécurité informatique dans le pays tout en stimulant le développement
de l'industrie pour laquelle cette même entreprise fait la promotion, à savoir encore une fois la sécurité informatique.

La mise en place de CIRCL il y a une dizaine d'années était un réel coup de génie compte tenu des progrès considérables réalisés en informatique, car depuis sa création, cette dernière ne fait que
croître et continue d'être un acteur majeur dans le domaine et de travailler au niveau national et international. Pour mener à bien toutes ces actions, l'entreprise est composée de plusieurs
spécialistes en sécurité informatique qui sont en mesure de fournir rapidement, efficacement et précisément des réponses aux différents incidents susceptibles d'être rencontrés par les personnes
en détresse qui font appel à ces services. Par conséquent, elle vise à apporter des solutions réelles et joue le rôle de "protectrice" en matière informatique au Luxembourg.

Nous pourrions penser qu'une telle entreprise serait nécessairement payante compte tenu de l'aide qu'elle apporte et du fait que nous sommes actuellement dans une ère où l'informatique occupe une place
prépondérante dans nos vies, que ce soit dans le cadre du travail, des loisirs ou même de nos objets personnels (objets connectés : smartwatch, smartTV, smartFridge...), ce qui accroît considérablement
le risque que n'importe qui puisse nuire à nos données à caractère personnel. Mais détrompez-vous : depuis 2014, CIRCL est une entreprise à but non lucratif, motivée par la promotion de la sécurité
informatique au Luxembourg.

Outre le fait que cette société vienne en aide à ceux qui le demandent en cas de cyberattaques, elle s'occupe également de la mise en place de certains projets et de leur maintien à long terme.
En voici trois exemples :
- CIRCLean : Cet outil a été développé dans le but de nettoyer automatiquement les fichiers malveillants, et il est utilisé par d'autres entreprises.

- Cyber Threat Intelligence : Il s'agit de la collecte d'informations sur les attaques et menaces informatiques à travers le monde, dans le but de les partager avec le plus grand nombre possible de
personnes en les publiant sur des plateformes de partage d'informations telles que MISP, ce qui nous amène au troisième exemple.

- MISP : Également appelée Malware Information Sharing Platform, MISP est une plateforme de partage d'informations dans laquelle les différentes organisations partagent des informations sur les attaques
et les menaces dans le but de mieux les comprendre et de mettre en place de nouvelles mesures pour mieux les contrer.

### Fonctionnemenet de l'entreprise 
Ainsi que vous l'aurez compris, l'entreprise gère la gestion de plusieurs tâches simultanément et pour gérer correctement ces différentes tâches, le travail est réparti en plusieurs groupes.
Nous avons tout d'abord un groupe s'occupant des recherches, portant sur les dernières actualités en termes de criminalité informatique et de l'élaboration des derniers outils pouvant être utiles à la
sécurité informatique. Nous avons ensuite un groupe qui s'occupe du développement de la plateforme MISP que nous avons évoquée précédemment. Il s'occupe ainsi du maintien de la plateforme et de
l'apport d'améliorations si possible. Continuons avec la fonction principale de cette entreprise, à savoir la réponse aux incidents. Une équipe est spécialement mobilisée à ces fins, à la suite de
signalements de différentes organisations, qu'elles soient gouvernementales, privées ou encore des particuliers. Pour rester dans le même esprit, un groupe va être mis en place afin de mener une
campagne de sensibilisation face aux incidents de sécurité informatique auprès des entreprises et en proposant également une formation pour renforcer leur riposte en cas d'acte malveillant envers leur
service informatique. Enfin, pour que tout ceci puisse convenablement se coordonner, une équipe de gestion de projet doit nécessairement être mise en place, et c'est chose faite. Ce groupe s'occupera de
tout ce qui se rattache à la gestion de projet, allant de la planification à la mise en place du projet, et ce pour l'ensemble des projets CIRCL.

Comme vous l'aurez compris, cette entreprise s'est fait une réelle place dans le monde de la cybersécurité grâce à ses services qualitatifs, ses projets de grande envergure, son étroite collaboration
avec un bon nombre d'entreprises qu'elles soient privées ou publiques, son organisation et sa manière de travailler, le tout appuyé par le fait que ce ne soit pas une société à but lucratif mais qui
apporte des solutions rapides et claires.

Maintenant que vous vous êtes familiarisé avec cette organisation en apprenant davantage sur ses spécificités, sa création, sa structure sociale et ses projets, nous pouvons passer à la présentation
et à l'explication de mon sujet.

Avant de commencer à entrer dans le vive du dujet de mon stage, je voudrais tout d'abord remercier
quelques personnes. Je remercie tout d'abord mon tuteur de stage Mr.Alexandre Dulaunoy qui m'a
accompagnée tout au long de mon stage dans l'entrerpise CIRCL (Computer Incident Response Center
Luxembourg). Il a sur me guider tout au long de la réalisation de mon projet de stage tout en me
sachant etre autonome afin d'appprendre un maximum de cette experience.


Dans le cadre de la formation de mon BUT informatique et de l'obtention de la deuxième année de ce diplomes nous avions pour but moi ainsi que l'ensemble de mes camardes de trouver un stage d'une
durée de 8 semaines au sein d'une entreprise informatique au sein de laquel nous allons étre confrontée au monde du travail. Durant cette periode de stage chaque élèvese trouve attribuer par 
l'entreprise l'acceuillant une sujet de stage qu'il devra lors des 2 mois essayer de l'accomplir. Le choix de son stage est donc très important car nous avons la possibilité de directement baigner
dans le même bain que tout nos autres collegues qui pour la plupart sont la depuis un petit moment, de plus cela pourrait constituer un choix crutial dans le choix de notre poursuite d'étude, nous
avions peut être un choix d'études fixé avant de se commencer notre stage et ce choix peut changer si l'on a choisi un stage en rapport avce nos choix et qui nous a pas plus fianelement, ou au
contraire pourrait nous conforter dans nos choix.
Voulant m'orienter dans le domaine de la cybersécurité à la fin de BUT informatique, le fait de rechercher un stage en rapport direct avce ce monde était chose évidente. 
J'ai donc contacter l'entreprise CIRCL (Computer Incident Response Center Luxembourg) et ai été accepter à l'issue d'un entretient telephonique avce mon tuteur de stage Alexandre Dulaunoy.
CIRCL est initiative gouvernemental luxembourgoise crée en 2012 et qui est depuis 2014 une entreprise à but non lucratif. Cette dernière offre des services gratuit a des collectivité publiques et ou 
privée pour leur venir en aide en cas d'incident de sécurité informatique ou simplement pour faire de la prévention, mais ce n'est pas leur seul activite. En parrallèle cette entreprises gère
plusieurs d'envergure nationale et international. CIRCL a sue se faire une réel place dans le monde de la cybersécurité et est un acteur majeur dans ce domaine au luxembourg. Sa rigeure, son
professionnalisme et son serieux leur a permis d'évoluer depuis leur début de manière constante en débutant avce 8 salariée jusqu'a arrivée à 38 aujourd'hui. C'est d'ailleurs cette évoluton qui leur a
nottament permis d'acceuillir plusieurs étudiant par année en leur attribuant chacun un sujet qu'il devront accomplir durant cette periode et vais sans plus attendre vous expliquer brièvement le mien.
Ma mission lors de ce stage concerne l'un des nombreux projets de l'entreprise qui MISP. Vulguairement expliquer MISP en quelques sorte le réseau social de la cybersécurité. Il va permettre aux
personnes faisant partie de la commuauté MISP d'en apprendre sur les nouvelle methodes de cybersécurité mais aussi sue les nouvelles methodes de cyberattaques, tout en ayant par la même occasion de
aussi la possibilité de publier ces informations. Mon travail serat donc reliée à tout ceci, le dossier de ce projet sur lequel je travalle est MISP-Vagrant, ainsi j'ai pour but de metre à jour 
l'ensemble des fichier le constituant. Ce travaille est assez complexes notamment à cause de part coherence des versions des outils que je dois installer car elle doit bien évidement s'adapter au
reste du grand projet MISP donc beaucoup de modification sont apportée. Pour travailler sur ce projet j'ai été amenerà utilisée des outils que je n'avais jamais utilisée auparavant tel que Virtualbox
ou encore Vagrant.
Pour vous presenter mon stage aisni que mon projet de ka manière qui soit nous allons tout d'baord commencer à parler de l'entreprise hebergeante afin que l'on ai un peu plus de détails, nous 
poursuivrons par explquer le fonctionnement de l'entreprise, nous passrosne ensuite par la présentation détaillé de mon projet et de tout le travail que j'ai accomplis et nous finirons enfin par une 
conclusion 
