{\rtf1\ansi\ansicpg1252\cocoartf1404\cocoasubrtf460
{\fonttbl\f0\fswiss\fcharset0 Helvetica;\f1\fnil\fcharset128 HiraginoSans-W4;}
{\colortbl;\red255\green255\blue255;}
\paperw11900\paperh16840\margl1440\margr1440\vieww13940\viewh24080\viewkind0
\pard\tx566\tx1133\tx1700\tx2267\tx2834\tx3401\tx3968\tx4535\tx5102\tx5669\tx6236\tx6803\pardirnatural\partightenfactor0

\f0\fs24 \cf0 #Introduction\
L\'92IHM 4Me r\'e9pond \'e0 un besoin d\'92int\'e9gration de plusieurs services non connect\'e9 aux syst\'e8mes op\'e9rationnels sur la position de contr\'f4le. L\'92application 4Me est   \'e0 la fois destin\'e9e \'e0 l\'92accueil d\'92applicatif existant comme XMAN et aux applicatifs futurs. 4Me devra \'eatre le support de nouveaux concepts op\'e9rationnels en exp\'e9rimentation. Les IHM 4Me sont param\'e9tr\'e9es par secteur et par regroupement de secteur, celles ci doivent donc correspondre au secteur r\'e9ellement ouvert sur la position de contr\'f4le.\
Ce document a pour but d\'92identifier et d\'92exprimer les besoins pour la r\'e9alisation de l\'92IHM pr\'e9sentant aux diff\'e9rents acteurs op\'e9rationnels et techniques les informations n\'e9cessaires \'e0 l\'92int\'e9gration des diff\'e9rents services ATM Light.\
##Documents applicables\'a0:\
[1] \
[2] \
[3] Note d\'92Architecture Technique\
[4] \
##Terminologie\'a0:\
Voir Annexes 2 et 3.\
##Pr\'e9sentation du syst\'e8me\
##Finalit\'e9, mission et objectifs du syst\'e8me\
- Finalit\'e9 du syst\'e8me : Pour les applicatifs d\'e9finis, la finalit\'e9 du syst\'e8me est d\'92int\'e9grer des applicatifs ind\'e9pendants dans une seule IHM et de fournir \'e0 l\'92utilisateurs des donn\'e9es sur l\'92etat des services ainsi que des notifications d\'92action.\
- Missions\'a0: Pour chaque  service  concern\'e9, le syst\'e8me permettra\'a0:\
o	d\'92informer les acteurs op\'e9rationnels de la n\'e9cessit\'e9 d\'92une action,\
o	d\'92informer les acteurs op\'e9rationnels de l\'92\'e9tat de service des applicatifs\
-Objectifs du syst\'e8me \'e9valuables : Pr\'e9sentation de 100% des donn\'e9es de chaque service\
\
##Parties prenante\
###DSNA/DTI\
	D\'e9finition des exigences et de l\'92architecture techniques cot\'e9 DSNA\
###Service Technique\
####Installation et maintenance de l'outil.\
###Service Exploitation\
####Projet XMAN\

\f1 - 
\f0 Gestion de projet\

\f1 - 
\f0 D\'e9finition des besoins (Ateliers D\'e9veloppement Outils)\
- Analyse et Conception (Sub ETU)\
####Subdivision ETU\

\f1 - 
\f0 Suivi de l\'92outil apr\'e8s MESO\
- Analyse post-op\'e9ratoire sur la base des logs de l\'92outil.\
####Chef de Salle \
Utiliser l\'92IHM 4Me SPVR pour mapper correctement les IHM Secteur 4Me en salle de contr\'f4le et assurer ainsi la correspondance entre les secteurs ouverts sur la position de contr\'f4le et l\'92IHM 4Me Secteur.\
####ACDS\
Utilise l\'92IHM 4Me pour y int\'e9grer les donn\'e9es ad hoc correspondant aux services dont il a la responsabilit\'e9.\
####CWP\
Secteurs de contr\'f4le mettent en \'9cuvre les proc\'e9dures relatives aux services int\'e9gr\'e9s dans 4Me. Ce sont les utilisateurs principaux de l\'92IHM.\
##Environnement & Contexte op\'e9rationnel\
Les contr\'f4leurs utilisent l\'92IHM directement sur les positions de contr\'f4le o\'f9 elle est d\'e9ploy\'e9e sur un \'e9cran \'ab\'a04ME\'a0\'bb \'e0 vocation multiservices qui est d\'e9di\'e9es \'e0 des applications non connect\'e9es au syst\'e8me op\'e9rationnel.\
Les CDS et ACDS utilisent l\'92IHM sur les postes \'ab\'a04ME\'a0\'bb d\'e9ploy\'e9s \'e0 l\'92\'eelot central. Les clients IHM d\'e9ploy\'e9s sur ces postes ont des besoins et fonctionnalit\'e9s sp\'e9cifiques. Ils peuvent \'eatre consid\'e9r\'e9s comme des clients-ma\'eetres.\
Le service technique utilise en salle de param\'e9trage, un client IHM sp\'e9cifique permettant le monitoring des services d\'92acquisition de donn\'e9es et  la relance de l\'92applicatif. \
M\'eame si le niveau de criticit\'e9 est faible, l\'92outil est utilis\'e9 de fa\'e7on op\'e9rationnelle. A ce titre, il doit respecter les r\'e8gles de d\'e9veloppement en vigueur \'e0 la DSNA (METLOG).\
L'int\'e9grit\'e9 et la disponibilit\'e9 des informations sont importantes dans le domaine ATC toutefois en ce qui concerne les services propos\'e9s par 4Me\'a0:\
\'95	La perte totale des informations n\'92a pas d\'92impact s\'e9curit\'e9\'a0: l\'92indisponibilit\'e9 du syst\'e8me est notifi\'e9e aux centres impact\'e9s, \
\'95	La corruption d\'e9tectable des informations n\'92a pas d\'92impact s\'e9curit\'e9, l\'92information erron\'e9e \'e9tant annul\'e9e par les contr\'f4leurs ou les \'e9quipages avant application. Cette situation conduit les op\'e9rateurs \'e0 d\'e9clarer le syst\'e8me comme indisponible et ram\'e8ne au cas pr\'e9c\'e9dent.\
\'95	La corruption non d\'e9tectable des informations a un impact limit\'e9 sur la s\'e9curit\'e9 qui est li\'e9 \'e0 une \'e9ventuelle augmentation des coordinations avec les centres en aval qui auraient une vision diff\'e9rente de la situation.\
La plupart des utilisateurs op\'e9rationnels n'ont pas de connaissance informatique pouss\'e9e et il n\'92est pas pr\'e9vu d\'92outil de supervision pour la maintenance op\'e9rationnelle au service technique. Des informations de diagnostic simples sur l\'92\'e9tat connu du service sont n\'e9cessaires pour que les acteurs op\'e9rationnels puissent effectuer les coordinations n\'e9cessaires avec les centres avals et la maintenance op\'e9rationnelle. Pour cette derni\'e8re, des fonctionnalit\'e9s simples de relance \'e0 chaud depuis le client en salle de param\'e9trage sont \'e0 pr\'e9voir.\
##Cycle de vie\
Pour ce qui concerne le d\'e9ploiement et la mise en service op\'e9rationnelle au CRNA/Est, l'outil sera con\'e7u, d\'e9velopp\'e9, install\'e9, exploit\'e9 et maintenu par le CRNA/Est.\
\
#Analyse de l\'92existant\
##Presentation G\'e9n\'e9rale du webservice (cas de EGLL)\
Pour le centre de LACC (Swanwick) o\'f9 il est install\'e9, le webservice est un nouveau composant du syst\'e8me ATFM. Le serveur SWIM-WS re\'e7oit de l\'92AMAN chaque message d\'92information de gestion des arriv\'e9es comprenant la s\'e9quence et le d\'e9lai sous la forme d\'92un message au format xml. Il publie ensuite ce message aupr\'e8s de clients ext\'e9rieurs qui en font la requ\'eate (principe de Request/Reply) via diff\'e9rents r\'e9seaux.\
\
L\'92architecture r\'e9seau pour la DSNA est la suivante\'a0: (Cf Note d\'92AT produite par DTI/ESA)\
\
##Schema descriptif des messages d\'92information de gestion des arrivees\
Chaque message d\'92information de gestion des arriv\'e9es \'e0 requ\'e9rir aupr\'e8s du webservice comprend notamment\'a0:\
\'95	L\'92information de s\'e9quence \'e0 la piste\
\'95	La strat\'e9gie d\'92utilisation des pistes\
\'95	Les informations de d\'e9lai total ou partag\'e9\
\'95	Les heures souhait\'e9es de passage au COP, \'e0 l\'92IAF et au seuil de piste\
Le service est d\'e9pendant de l\'92AMAN du NATS qui produit le message pour ce service.\
Le sch\'e9ma de complet de description de la charge utile est le suivant\'a0:\
\
##Description de l\'92interface \
\'95	Bandeau d\'92\'e9tat de service\'a0:\
\'95	Bandeau lat\'e9ral de service\'a0:\
\'95	Pav\'e9 d\'92applicatif:\
##Sc\'e9nario de travail\
Scenario 1\
Sur les plages horaires 06h30 \'e0 22h00 UTC (heure d\'92hiver) et 05h30 \'e0 21h00 UTC (heure d\'92\'e9t\'e9), les proc\'e9dures XMAN EGLL sont en vigueur.\
Gr\'e2ce \'e0 la prise en compte des donn\'e9es ETFMS, l\'92AMAN EGLL commence \'e0 \'e9laborer ses s\'e9quences 85 min (environ 550NM) avant la piste. Le d\'e9lai calcul\'e9 \'e0 la piste est alors partag\'e9 entre les diff\'e9rents acteurs\'a0: LATC (Terminal Center), LACC (Area Center) et un centre en route dont Reims UAC pour le flux d\'92arriv\'e9e via ABNUR.\
La table ci-apr\'e8s r\'e9sume la strat\'e9gie de r\'e9partition du d\'e9lai\'a0:\
\
La r\'e9partition du d\'e9lai est appliqu\'e9e au niveau du webservice de l\'92AMAN et le fichier obtenu apr\'e8s requ\'eate contient donc pour chaque vol le d\'e9lai total et le d\'e9lai Reims.\
Scenario 2\'a0:\
L\'92horizon d\'92activit\'e9 pour XMAN EGLL a \'e9t\'e9 fix\'e9 avec les partenaires \'e0 350NM de la piste. A l\'92int\'e9rieur de cet horizon, les secteurs des centres amont appliquent les r\'e9ductions de vitesse qui permettent d\'92absorber le d\'e9lai qui leur est attribu\'e9.\
\
Une r\'e9duction de vitesse est propos\'e9e aux contr\'f4leurs pour absorber le d\'e9lai attribu\'e9 \'e0 Reims UAC. Ellen\'92est pas fournie par le message d\'92information de gestion des arriv\'e9es et doit donc \'eatre le r\'e9sultat d\'92un calcul local. Dans un premier temps, une approche simpliste pourra \'eatre utilis\'e9e selon les principes suivants\'a0:\
\
Scenario 3\'a0:\
Les contr\'f4leurs du centre amont renseignent l\'92IHM des r\'e9ductions de vitesse qu\'92ils ont impl\'e9ment\'e9es de fa\'e7on \'e0 ce que l\'92information soit partag\'e9e entre les diff\'e9rents acteurs op\'e9rationnels au niveau de ce centre. Dans un premier temps, cette information reste interne au centre amont et n\'92est pas partag\'e9e avec le centre aval.\
Scenario 4\'a0: \
Scenario 5\'a0:\
Pour faciliter les analyses post-op\'e9ratoires des dysfonctionnements, et r\'e9pondre aux interrogations des contr\'f4leurs sur le comportement des outils, il est plus efficace de rejouer une situation sur l\'92IHM que de proc\'e9der \'e0 l\'92analyse fastidieuse des fichiers.\
##Synth\'e8se des sc\'e9narios de travail\
Id\
Point faible\
Origine (indiquer le ou les sc\'e9narios mettant en valeur le point)\
Expression du besoin\
1\
Pas d\'92acquisition possible des donn\'e9es produites par l\'92AMAN et mises \'e0 disposition au niveau du webservice par l\'92interm\'e9diaire des connections existantes (Msg OLDI AMA par ex)  \
Sc\'e9nario n\'b01\
L'outil permet de d\'92acqu\'e9rir et d\'92afficher les donn\'e9es d\'92information de gestion des arriv\'e9es au niveau du webservice mis en place \'e0 cet effet.\
2\
Pas de proposition de vitesse produite par l\'92AMAN.\
Sc\'e9nario n\'b02\
L'outil permet de proposer aux contr\'f4leurs une conversion du d\'e9lai \'e0 absorber en une proposition de r\'e9duction de point de Mach.\
3\
Pas de possibilit\'e9 dans le syst\'e8me ATM actuel de renseigner et partager les instructions de contr\'f4le de vitesse transmises aux \'e9quipages.\
Sc\'e9nario n\'b03\
L'outil permet aux contr\'f4leurs de renseigner les instructions de r\'e9duction de point de Mach transmises aux \'e9quipages et de les partager entre les diff\'e9rentes IHM.\
4\
Pas d\'92archivage des donn\'e9es du c\'f4t\'e9 du centre amont en particulier pour ce qui concerne les instructions de contr\'f4le de vitesse transmises aux \'e9quipages\
Sc\'e9nario n\'b04\
L\'92outil permet d\'92enregistrer et de stocker les donn\'e9es d\'92information de gestion des arriv\'e9es acquises aupr\'e8s du webservice ainsi que les instructions de r\'e9duction de point de Mach transmises aux \'e9quipages y compris le lieu, l\'92heure et le secteur concern\'e9 au moment de l\'92application.\
5\
Pas de rejeu possible des donn\'e9es d\'92information de gestion des arriv\'e9es re\'e7ues dans le pass\'e9\
Sc\'e9nario n\'b05\
L\'92outil permet de rejouer des donn\'e9es d\'92information de gestion des arriv\'e9es re\'e7ues dans le pass\'e9 et stock\'e9es localement.\
Tableau 1\'a0: synth\'e8se des points faibles et besoins correspondants\
ID\
Point fort\
Origine\
Expression du besoin\
1\
Les contr\'f4leurs int\'e8grent les informations de gestions des arriv\'e9es et  propositions de r\'e9duction de point de Mach dans leur analyse. Ils valident la pertinence de leur prise en compte en fonction de leur charge de travail et de la situation a\'e9rienne globale\
Sc\'e9nario 1, 2et 3\
L'outil fournit une information compl\'e9mentaire \'e0 celles qui sont d\'e9j\'e0 accessibles par l\'92ATC et qui restent LA r\'e9f\'e9rence pour ce qui concerne les conditions de sortie. Elles ne permettent sur la base du principe \'ab\'a0Best effort\'a0\'bb que d\'92am\'e9liorer l\'92efficacit\'e9 \'ab\'a0carburant\'a0\'bb des vols \'e0 l\'92arriv\'e9e.\
2\
La disponibilit\'e9 de l\'92AMAN et duwebservice est r\'e9put\'e9e bonne.\
Sp\'e9cifications AMAN et Webservice\
Du point de vue du centre aval, l\'92AMAN et le webservice associ\'e9e sont des syst\'e8mes op\'e9rationnels ayant un niveau de criticit\'e9 relativement fort et ainsi supervis\'e9s pour atteindre une disponibilit\'e9 \'e9lev\'e9e.\
Tableau 2\'a0: synth\'e8se des points forts et besoins correspondants\
\
#	Analyse Fonctionnelle\
##\'c9l\'e9ments du Milieu Ext\'e9rieur (EME) :\
\'95	Contr\'f4leurs Ex\'e9cutif ou Planneur sur position de contr\'f4le (CWP)\
\'95	Chef de Salle et ACDS\
\'95	Subdivision \'c9tudes\
\'95	Service Technique\
##Fonctions principales\'a0:\
\'95	FP1\'a0: Afficher une s\'e9lection des \'e9l\'e9ments pr\'e9sents dans les messages d\'92information de gestion des arriv\'e9es compl\'e9t\'e9e d\'92\'e9l\'e9ments de donn\'e9es RADAR\
\'95	FP2\'a0: Produire une proposition de r\'e9duction de point de Mach fonction du d\'e9lai attribu\'e9 au centre DSNA concern\'e9.\
\'95	FP3\'a0: Recueillir et partager entre toutes les IHM, les instructions de r\'e9duction de point de Mach transmises par les contr\'f4leurs aux \'e9quipages.\
\'95	FP4\'a0: Permettre \'e0 des clients-ma\'eetre de piloter des fonctions particuli\'e8res (ON/OFF, relance \'85)\
\'95	FP5\'a0: Enregistrer et stocker les donn\'e9es relatives \'e0 la gestion des arriv\'e9es aux fins d\'92analyses post-op\'e9ratoires et de rejeux.\
\'95	FP6\'a0: Rejouer une situation ant\'e9rieure\
\
##Fonctions contraintes\'a0:\
\'95	FC1\'a0: \'catre tol\'e9rant \'e0 l\'92interruption de la production des messages d\'92information de gestion des arriv\'e9es par le webservice distant ou \'e0 l\'92interruption de r\'e9ception de donn\'e9es RADAR.\
\'95	FC2\'a0: L'outil devra pouvoir \'eatre adaptatif pour inclure ult\'e9rieurement des informations de gestion des arriv\'e9es pour d\'92autres a\'e9roports.\
\'95	FC3\'a0: Offrir une interface simple d\'92utilisation.\
\
4.4	Relations entre fonctions et 4ME\
Les relations entre les diff\'e9rentes fonctions et les EME sont repr\'e9sent\'e9es sur la pieuvre ci-apr\'e8s\'a0:\
\
\
\
\
\
\
\
\
\
\
\
4.5	Justification des fonctions et crit\'e8res de valeur\'a0\
Fonction\
ID point faible\
Crit\'e8re de valeur\
FP 1\
1, 4, 5\
Acqu\'e9rir les informations de gestion des arriv\'e9es \'e0 une fr\'e9quence d\'92au moins 1 message correct par minute.\
Acqu\'e9rir les informations RADAR pour les vols de la s\'e9quence pour lesquels elles sont disponibles dans 80% des cas.\
Afficher les donn\'e9es choisies pour  100% des messages correctement acquis aupr\'e8s du webservice\
FP 2\
2, 4, 5\
Production d\'92une proposition de r\'e9duction de vitesse selon l\'92algorithme propos\'e9 pour 100% des vols pr\'e9sents dans la s\'e9quence contenue dans les messages correctement acquis.\
FP 3\
3, 4\
100% des informations saisies par les contr\'f4leurs sont correctement enregistr\'e9es et partag\'e9es.\
FP 4\
NA\
Les CDS, ACDS, op\'e9rateur de maintenance doivent avoir acc\'e8s \'e0 des fonctions privil\'e9gi\'e9es.\
FP5\
4, 5\
100% des informations re\'e7ues et celles saisies par les contr\'f4leurs sont correctement enregistr\'e9es et stock\'e9es.\
FP6\
5\
L'outil permet de rejouer une situation pass\'e9e pour l'afficher dans la m\'eame interface de visualisation.\
FC1\
NA\
En cas d\'92interruption prolong\'e9e de la r\'e9ception des messages d\'92information de gestion des arriv\'e9es, l\'92outil doit indiquer le non rafraichissement des donn\'e9es sans pour autant provoquer l\'92arr\'eat de l\'92applicatif. L\'92applicatif doit \'eatre tol\'e9rant \'e0 l\'92absence de donn\'e9es RADAR. \
FC2\
NA\
L\'92outil doit \'eatre d\'e9velopp\'e9 de fa\'e7on g\'e9n\'e9rique de fa\'e7on \'e0 pourvoir \'eatre \'e9tendu rapidement \'e0 d\'92autres a\'e9roports (LSZH par exemple) \
FC3\
NA\
L\'92IHM doit proposer aux contr\'f4leurs une vision claire des vols soumis aux proc\'e9dures XMAN. Elle permet notamment de renseigner les instructions transmises en un seul clic. Par ailleurs, l\'92IHM sur les secteurs de contr\'f4le ne doit  faire appel \'e0 aucune saisie clavier.\
Tableau 3\'a0: Origine des fonctions et crit\'e8res de valeur\
\
\
\
5	Besoins\
5.1	Mod\'e8le conceptuel des donn\'e9es du domaine\
Le diagramme ci-apr\'e8s permet de se repr\'e9senter les diff\'e9rentes entit\'e9s mises en \'9cuvre et les relations entre elles. Il ne pr\'e9sume en rien des classes r\'e9ellement utilis\'e9es dans le code.\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
5.2	Cas d\'92utilisation (Use Cases)\
La figure ci-dessous repr\'e9sente les cas d'utilisations que devra r\'e9aliser le futur outil\'a0:\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
Cas d\'92utilisation\
Description\
CU1 \'96 Calculer Mach R\'e9duction\
Fournir aux utilisateurs une proposition de r\'e9duction de point de Mach qui correspond au d\'e9lai allou\'e9 pour chaque vol. Voir Annexe 1 pour une description de l'interface souhait\'e9e.ex\'a0: ade\
CU2 \'96 G\'e9n\'e9rer des archives\
Cr\'e9er des archives de mani\'e8re automatique (tout ce qui est re\'e7u et calcul\'e9) et manuelle (sur action utilisateur).\
CU3 \'96 Rejouer des archives\
Permettre \'e0 des utilisateurs de rejouer des archives afin de pouvoir observer une situation pass\'e9e. L'outil de visualisation utilis\'e9 sera le m\'eame que celui utilis\'e9 en temps r\'e9el.\
CU4 \'96 Param\'e9trer \
Permettre \'e0 un utilisateur de param\'e9trer l'application du point de vue super-utilisateur (ex\'a0: ON/OFF proc\'e9dures XMAN; Proc\'e9dures Minimum Clean Speed)\
CU5 \'96 Relancer\
Permettre \'e0 un utilisateur de maintenance op\'e9rationnelle une analyse simple de l\'92\'e9tat des services pour une relance rapide de l\'92applicatif.\
Tableau 4\'a0: Description des Cas d'Utilisation du syst\'e8me\
5.3	Synth\'e8se des besoins\
Dans le tableau ci-dessous, sont regroup\'e9s tous les besoins associ\'e9s au syst\'e8me.\
Niveau de priorit\'e9\'a0: 1 = le plus prioritaire, 5 = le moins prioritaire\
Identifiant\
Besoin\
Justification\
Priorit\'e9\
B1\
Fonctions\
\
\
B1.1\
Afficher verticalement la liste des vols \'e0 destination de EGLL qui sont dans la zone de responsabilit\'e9 du CRNA/Est class\'e9s selon l\'92heure estim\'e9e de passage \'e0 ABNUR de la plus petite \'e0 la plus grande.\
FP1, CU1\
1\
B1.2\
Un param\'e9trage client permet d\'92effacer les vols lorsqu\'92ils sont sortis de l\'92emprise g\'e9ographique du secteur auquel est affect\'e9 l\'92IHM.\
FP1, CU 1\
3\
B1.3\
Afficher la configuration piste \'e0 EGLL\
Atelier XMAN\
4\
B1.4\
Afficher l\'92heure UTC courante\
Atelier XMAN\
2\
B1.5\
Pour chaque vol, on indique\'a0:\
\'95	Delay Total courant\
\'95	Indicatif (ARCID)\
\'95	Flight Level courant (Mode C)\
\'95	Heure calcul\'e9e comme objectif \'e0 ABNUR par l\'92AMAN\
\'95	D\'e9lai allou\'e9 \'e0 Reims selon la strat\'e9gie de r\'e9partition du d\'e9lai\
FP1, CU1\
1\
B1.6\
Les champs ARCID, Mode C, TT@ABNUR, Reims Delay permettent d\'92identifier les \'e9tats suivants\'a0:\
\'95	Vols en dehors de la plage horaire de mise en \'9cuvre des proc\'e9dures XMAN  (ARCID en blanc et \'ab\'a0zZzzZz\'a0\'bb dans les autres champs)\
\'95	Vols situ\'e9s entre l\'92horizon d\'92\'e9ligibilit\'e9 (ie pr\'e9sent dans la s\'e9quence) et l\'92horizon d\'92activit\'e9 (350NM de EGLL) (ARCID et Mode C en blanc et absence de valeur TT@ABNUR et Reims Delay)\
\'95	Vols avec un d\'e9lai Reims nul\'a0(toutes valeurs en blanc)\
\'95	Vols avec un d\'e9lai Reims \'e0 r\'e9sorber sans action r\'e9alis\'e9e (toutes valeurs en rouge)\
\'95	Vols pour lesquels une action a \'e9t\'e9 r\'e9alis\'e9e (toutes valeurs en vert)\
\
FP1, CU1\
1\
B1.7\
La valeur du Mode C est NA s\'92il n\'92y a pas de donn\'e9es RADAR disponible pour le vol consid\'e9r\'e9.\
FP1, CU1\
3\
B1.8\
Un codage couleur est appliqu\'e9 \'e0 la valeur de d\'e9lai total\'a0:\
\'95	Jaune\'a0: d\'e9lai total \uc0\u8804  5\'92\
\'95	Orange\'a0: 6\'92 \uc0\u8804  d\'e9lai total \u8804  7\'92\
\'95	Rouge\'a0: 7\'92 \uc0\u8804  d\'e9lai total\
FP1, CU1, Atelier XMAN\
2\
B1.9\
Pour chaque vol, en fonction du d\'e9lai Reims, l\'92op\'e9rateur est inform\'e9 de la r\'e9duction de point de Mach propos\'e9e pour absorber le d\'e9lai consid\'e9rer selon la table au \'a73.4\
FP2, CU1\
1\
B1.10\
Pour chaque vol, l\'92op\'e9rateur peut indiquer la valeur de la r\'e9duction de point de Mach qui a \'e9t\'e9 transmise \'e0 l\'92a\'e9ronef.\
FP3, CU1\
1\
B1.11\
Toutes les informations entr\'e9es \'e0 l\'92IHM par un op\'e9rateur sur un vol donn\'e9 doivent \'eatre partag\'e9es sur l\'92ensemble des IHM affichant ce vol.\
FP3, CU1\
1\
B1.12\
Un codage couleur doit permettre d\'92identifier si l\'92instruction transmise correspond ou pas \'e0 la proposition initiale.\
FP3, CU1\
2\
B1.13\
L\'92op\'e9rateur doit pouvoir indiquer si l\'92instruction transmise a \'e9t\'e9 modifi\'e9e suite \'e0 impossibilit\'e9 pour l\'92\'e9quipage d\'92accepter la proposition initiale.\
FP3, CU1\
2\
B1.14\
Pour les vols ayant un d\'e9lai Reims non nul, une alarme visuelle doit indiquer pour chaque secteur si aucune action n\'92a \'e9t\'e9 r\'e9alis\'e9e 20NM apr\'e8s la pr\'e9sentation initiale du d\'e9lai ou 20NM apr\'e8s l\'92entr\'e9e secteur si la pr\'e9sentation initiale du d\'e9lai a \'e9t\'e9 faite dans un secteur amont.\
FP1, CU1\
3\
B1.15\
En cas d\'92erreur de saisie, l\'92op\'e9rateur doit pouvoir remettre l\'92IHM \'e0 l\'92\'e9tat imm\'e9diatement pr\'e9c\'e9dent.\
Atelier XMAN, CU1\
3\
B1.16\
Pour chaque vol, l\'92identification du secteur qui a transmis la derni\'e8re instruction de vitesse doit \'eatre partag\'e9e, sur toutes les IHM affichant le vol.\
FP3, CU1\
1\
B1.17\
Un param\'e9trage client permet de particulariser les IHM ACDS, CDS et Technique avec des fonctionnalit\'e9s suppl\'e9mentaires.\
FP4, CU4\
3\
B1.18\
Depuis les clients CDS et ACDS, il est possible de faire afficher \'e0 la demande sur l\'92ensemble des IHM un message en surimpression pour indiquer qu\'92il a \'e9t\'e9 d\'e9cid\'e9 par le couple CDS/ACDS de ne pas appliquer les proc\'e9dures XMAN.\
FP4, CU4\
2\
B1.19\
Un message en surimpression s\'92affiche automatiquement pour indiquer que les donn\'e9es ne sont plus mises \'e0 jour.\
FC1\
1\
B1.20\
Depuis les clients CDS et ACDS, il est possible de forcer une indication \'ab\'a0Minimum Clean Speed\'a0\'bb \'e0 la place des propositions de r\'e9duction de point de Mach.\
FP4, CU4\
2\
B1.20\
Le syst\'e8me devra proposer une supervision simple ou des informations techniques permettant un diagnostic de son \'e9tat.\
FP4, CU5\
4\
B2\
Performances attendues\
\
\
B2.1\
Acqu\'e9rir les informations de gestion des arriv\'e9es \'e0 une fr\'e9quence d\'92au moins 1 message correct par minute.\
FP1, CU1\
1\
B2.2\
Afficher les donn\'e9es choisies pour  100% des messages correctement acquis aupr\'e8s du webservice\
FP1, CU1\
1\
B2.3\
Production d\'92une proposition de r\'e9duction de vitesse selon l\'92algorithme propos\'e9 pour 100% des vols pr\'e9sents dans la s\'e9quence contenue dans les messages correctement acquis.\
FP1, CU1\
1\
B2.4\
Acqu\'e9rir les informations RADAR pour les vols de la s\'e9quence pour lesquels elles sont disponibles dans 80% des cas.\
FP1, CU1\
4\
B2.5\
Production d\'92une proposition de r\'e9duction de vitesse selon l\'92algorithme propos\'e9 pour 100% des vols pr\'e9sents dans la s\'e9quence contenue dans les messages correctement acquis.\
FP2, CU1\
1\
B2.6\
100% des informations saisies par les contr\'f4leurs sont correctement enregistr\'e9es et partag\'e9es.\
FP3, CU1, CU2\
1\
B2.7\
100% des informations re\'e7ues et celles saisies par les contr\'f4leurs sont correctement enregistr\'e9es et stock\'e9es.\
FP4, CU2\
2\
B3\
Interfaces\
\
\
B3.1\
L\'92outil doit \'eatre d\'e9velopp\'e9 de fa\'e7on g\'e9n\'e9rique de fa\'e7on \'e0 pourvoir \'eatre \'e9tendu rapidement \'e0 d\'92autres a\'e9roports (LSZH par exemple)\
FC2\
3\
B4\
Sc\'e9narios op\'e9rationnels\
\
\
B4.1\
Le syst\'e8me permet de r\'e9aliser le cas d\'92utilisation CU1\
CU1 et Annexe 1\
1\
B4.2\
Le syst\'e8me permet de r\'e9aliser le cas d\'92utilisation CU2 \'a0\
CU2\
1\
B4.3\
Le syst\'e8me permet de r\'e9aliser le cas d\'92utilisation CU3 \'a0\
CU3\
3\
B4.4\
Le syst\'e8me permet de r\'e9aliser le cas d\'92utilisation CU4 \'a0\
CU4\
3\
B4.5\
Le syst\'e8me permet de r\'e9aliser le cas d\'92utilisation CU5\
CU5\
4\
B5\
Contraintes\
\
\
B5.1\
Le d\'e9veloppement du syst\'e8me respecte la METLOG\
Environnement et contexte op\'e9rationnel\
2\
B5.2\
En cas d\'92interruption prolong\'e9e de la r\'e9ception des messages d\'92information de gestion des arriv\'e9es, l\'92outil doit indiquer le non rafraichissement des donn\'e9es sans pour autant provoquer l\'92arr\'eat de l\'92applicatif.L\'92applicatif doit \'eatre tol\'e9rant \'e0 l\'92absence de donn\'e9es RADAR.\
FC1\
1\
B5.3\
L\'92IHM doit proposer aux contr\'f4leurs une vision claire des vols soumis aux proc\'e9dures XMAN. Elle permet notamment de renseigner les instructions transmises en un seul clic. Par ailleurs, l\'92IHM sur les secteurs de contr\'f4le ne doit  faire appel \'e0 aucune saisie clavier.\
FC3 et Annexe 1\
1\
Tableau 5\'a0: Tableau de synth\'e8se des besoins\
\page \
Annexe 1\'a0: Description de l\'92interface secteur\
\
\page \
Annexe 2: Glossaire\
Term\
Definition\
Active Advisory Area\
Located between the Frozen Horizon and the Active Advisory Horizon and encompasses the different minimum stability threshold levels which ANSP\'92s may require to begin sending advisories to upstream centres\
Active Advisory Horizon\
The point from which XMAN advisories are acted upon\
4D Contract\
An ATC clearance that prescribes the containment of the trajectory in all 4 dimensions for the period of the contract during which the uncertainty associated with future predicted position does not increase with the prediction horizon.\
4D Trajectory\
A set of consecutive segments linking waypoints and/or points computed by FMS (airborne) or by TP (ground) to build the vertical profile and the lateral transitions; each point defined by a longitude, a latitude, a level and a time.\
Actor\
An implementation independent unit of responsibility that performs an action to achieve an effect that contributes to a desired end state.\
Airborne Delay\
Delay incurred in the air, either en-route or when holding.\
Airspace\
A defined three dimensional region of space relevant to air traffic.\
Air Traffic Management\
The aggregation of the airborne functions and ground-based functions (air traffic services, airspace management and air traffic flow management) required to ensure the safe and efficient movement of aircraft during all phases of operations.\
Air Traffic Service\
A generic term meaning variously, flight information service, alerting service, air traffic advisory service, air traffic control service (area control service, approach control service or aerodrome control service).\
Air Traffic Services Unit\
A generic term meaning variously, air traffic control unit, flight information centre or air traffic services reporting office.\
Arrival Management Service\
Arrival Management Service is provided through procedures used to establish sequences and related times e.g. as planned by an arrival manager.\
Arrival Manager\
An AMAN is a planning system to improve arrival flows at one or more airports by calculating the optimised approach / landing sequence and Target Landing Times (TLDT) and where needed times for specific fixes for each flight, taking multiple constraints and preferences into account.\
Business Trajectory\
A 4D trajectory which expresses the business or mission intentions of the user with or without constraints. It includes both ground and airborne segments of the aircraft operation (gate-to-gate) and is built from, and updated with, the most timely and accurate data available.\
Collaborative Decision Making\
A set of applications aimed at improving flight operations through the increased involvement of airspace users, ATM service providers, airport operators and other stakeholders in the process of air traffic management.\
An environment in which the consequences of decisions taken are visible to all partners.\
Concept of Operation\
The tool used by an organisation to establish the desired approach it wishes to take to realise a system or service. The CONOPS documents the high level decisions and agreement that define the approach and the organisational structure needed to put that approach into operation.\
Constraint\
Any restriction brought to the preferred trajectory of an aircraft, being either a tactical constraint such as ATCO instruction, or a strategic constraint derived from the operations of the network.\
Any limitation on the implementation of an AMAN Information Extension to En-route Sectors Concept of Operations operational improvement, or a limitation on reaching the desired level of service. We use this term generically to refer to time, speed, lateral and vertical data issued to the aircraft that restrict the options of the flight crew or FMS on how the aircraft is to be flown.\
Constraint Waypoint\
Waypoint for which a time constraint has been agreed.\
Continuous Descent Operation\
An operation, enabled by airspace design, procedure design and ATC facilitation, in which an arriving aircraft descends continuously, to the greatest possible extent, by employing minimum engine thrust, ideally in a low drag configuration, prior to the final approach fix /final approach point.\
Controlled Time of Arrival\
An ATM imposed time constraint at a point associated with the arrival of a flight.\
Controlled Time Over\
An ATM imposed time constraint over a point.\
Departure Manager\
A DMAN isa planning system to improve departure flows at one or more airports by calculating the Target Take Off Time (TTOT) and\'a0{\field{\*\fldinst{HYPERLINK "https://extranet.eurocontrol.int/http:/atmlexicon.eurocontrol.int/lexicon/en/index.php/Target_Start_Up_Approval_Time%22%20%5Co%20%22Target%20Start%20Up%20Approval%20Time"}}{\fldrslt Target Start Up Approval Time}}\'a0(TSAT) for each flight, taking multiple constraints and preferences into account.\
Eligibility Horizon\
The point from which AMAN receives data and begins processing a sequence\
ETA min/max\
ETA min/max is a reliable earliest/latest ETA at a waypoint; wind/temp error is also taken into account in order to guarantee that any CTA defined within associated ETA min/max interval will be satisfied with high probability (95%).\
The ETA min/max can be reported using ADS-C\
Extended TMA (E-TMA)\
The E-TMA corresponds to ACC terminal sector(s) (between Top Of Descent (ToD) and the Initial Approach Fix (IAF)) which make(s) the transition between the En-Route and the TMA sectors which encompass the Approach airspace (between IAF and Final Approach Fix (FAF) or transfer to the Tower).\
In the present document, arrival management starts in E-TMA to feed TMA entry points.\
Flight Object\
The system instance view of a flight. It is the flight object that is shared between the IOP stakeholders.\
Flight Plan\
Specified information provided to air traffic services units, relative to an intended flight or portion of a flight of an aircraft.\
Frozen Horizon\
The point at which the AMAN landing sequence is fixed and cannot be changed automatically by AMAN\
Ground Delay\
Delay incurred on the ground, either at the gate or on the taxiway.\
Interoperable\
Characteristic indicating the ability to exchange, integrate and manage content between systems.\
In Horizon Departures\
Flights departing from Airports within the AAH of the Destination Airport\
Level\
A generic term relating to the vertical position of an aircraft in flight and meaning variously, height, altitude or flight level.\
Level Constraint\
The constraint defined by an objective to set the cleared flight level (CFL) for the flight.\
Managed Airspace\
Airspace in which all traffic is known to the Air Traffic System\
Net-centric\
Participating as a part of a continuously-evolving, complex community of people, devices, information and services interconnected by a communications network to achieve optimal benefit of resources and better synchronisation of events and their consequences. (Wikipedia)\
Network Operations \
Plan\
The Network Operations Plan is a set of collaborative applications providing access to traffic demand, airspace and airport capacity and constraints and scenarios to assist in managing diverse events. The aim of the NOP is to facilitate the processes needed to reach agreements on demand and capacity.\
Operating Environment\
An environment with a consistent type of flight operations.\
Operational Concept\
A proposed system in terms of the user needs it will fulfil, its relationship to existing systems or procedures and the ways it will be used. It is used to obtain consensus among the acquirer, developer, support, and user agencies on the operational concept of a proposed system.\
Performance-Based Navigation\
Area navigation based on performance requirements for aircraft operating along an ATS route, on an instrument approach procedure or in a designated airspace.\
Pop Up Flights\
Flights which are added into the sequence, and thus have delay and XMAN advisories assigned to them, only when they get airborne and not before due lack of accurate data\
Pre-Planned Departures\
Flights where ACDM / DPI information available thus could be added into the sequence before departure\
Queue Management\
The tactical establishment and maintenance of a safe, orderly and efficient flow of traffic. It includes the handling of queues, both in the air and on the ground. It operates on individual flights and is closely related to, and sometimes indistinguishable from, the Separation Provision process. It aims to facilitate the highest achievable capacity of the ATM System and to manage delays in a fuel-efficient and environmentally acceptable manner.\
Reference Business \
Trajectory\
The business trajectory which the airspace user agrees to fly and the ANSP and Airports agree to facilitate (subject to separation provision). Most times indicated in the RBT are estimates, some may be target times (TTA) to facilitate planning and some of them may become constraints (CTA, CTO) to assist in queue management when appropriate, e.g. at XMAN/AMAN horizon.\
Required Navigation Performance\
A statement of the navigation performance necessary for operation within a defined airspace.\
Required Time of \
Arrival\
Only refers to the aircraft FMS RTA function.\
SARA\
Speed and Route Advisory. An ATM tool that gives advice on speed and routing for inbound traffic to an airport.\
SESAR Programme\
The programme which defines the Research and Development activities and Projects for the SJU.\
SJU Work Programme\
The programme which addresses all activities of the SESAR Joint Undertaking Agency.\
System Wide \
Information \
Management\
A distributed processing environment which replaces data level interoperability and closely coupled interfaces with an open, flexible, modular and secure data architecture totally transparent to users and their applications.\
Time Based Operation\
Time-based Operations is the basis of the SESAR Concept. It focuses on flight efficiency, predictability and the environment. The goal is a synchronised European ATM system where partners are aware of the business and operational situations and collaborate to optimise their operations.\
Top of Descend\
The Top of Descend is the computed transition from the cruise phase of a flight to the descend phase, the point at which the planned descent to final approach altitude is initiated.\
Trajectory Based Operations\
SESAR Trajectory-based Operations focuses on a further-evolved flight efficiency, predictability and environment and adds capacity. The goal is a trajectory-based ATM system where partners optimise \'93business and mission trajectories\'94 through common 4D trajectory information and user defined priorities in the network.\
Trajectory Prediction\
The trajectory prediction is continually updated and corresponds to what the aircraft is predicted to fly.\
Traffic Metering\
Traffic metering is the process of organising aircraft into a flow of aircraft with a specific rate.\
Traffic Sequencing\
Traffic sequencing is the process of organising aircraft into a specific order.\
Vectoring\
\
Air traffic controllers may have to vector aircraft on their course, e.g. in the frame of a tactical intervention involving a deviation from the planned route for safety reasons, or in a more systematic way \'96 as is often the case in terminal airspace, to sequence aircraft towards the runway(s). \
Open-loop vectors, as opposed to closed-loop vectors, correspond to the case when no indication is given as to the duration or limit of the ATC vector instruction, nor how the aircraft will re-join its initial route. Typically, a simple heading instruction is an open-loop vector, while a \'93Direct-to\'94 instruction is a closed-loop vector. \
Throughout this document, the term vectoring without additional indication refer to open-loop vectors.\
XMAN\
Cross Border Arrival Management (or Extended Arrival Management): Describes the extension of Arrival Management procedures across FIR borders with the help of upgraded AMAN systems and information provision to adjacent ATS units\
\
\
Annexe 3: Abr\'e9viations et Acronymes\
Term\
Definition\
AAA\
Active Advisory Area\
AAH\
Active Advisory Horizon\
ABI\
Advance Boundary Information (OLDI)\
ACARS\
Aircraft Communications Adressing and Reporting System\
A-DPI\
Departure Progress Message with Actual Off-Block time\
ACC\
Area Control Centre\
ACFT\
Aircraft\
ACK\
Acknowledge\
ACT\
Activation Message (OLDI)\
ADS-B/C\
Automatic Dependent Surveillance \'96 Broadcast/Contract\
AIP\
Aeronautical Information Publication\
AFP\
ATC Flight Plan Proposal\
AMA\
Arrival Management Message (OLDI)\
AMAN\
Arrival Manager (dedicated system support software) \
ANSP\
Air Navigation Service Provider\
AOI\
Area of Interest\
AOC\
Airline Operations Centre\
AOR\
Area of Responsibility\
APP\
Approach control unit\
ASAS\
Airborne Separation Assistance System\
ATC\
Air Traffic Control\
ATCO\
Air Traffic Controller\
ATD\
Actual Time of Departure\
ATFCM \
Air Traffic Flow and Capacity Management\
ATM\
Air Traffic Management\
ATO\
Actual Time Over\
ATS\
Air Traffic Services\
ATSU\
Air Traffic Service Unit\
BADA\
Base of Aircraft Data\
CB\
Cumulonimbus\
CDA\
Continuous Descent Approach\
CDM\
Collaborative Decision Making\
CDO\
Continuous Descend Operations\
CHMI\
Collaborative HMI\
CNS\
Communication Navigation Surveillance\
CONOPS\
Concept of Operations\
COP\
Coordination Point\
CPDLC\
Controller-Pilot Data Link Communications\
CPR\
Compact Position Reporting Message\
CTA\
Controlled Time of Arrival\
CTO\
Controlled Time Over/ Calculated Time over COP\
CTOT\
Calculated Take-Off Time \
CWP\
Controller Working Position\
CTA\
Controlled Time of Arrival\
DCB\
Demand \'96 Capacity Balancing\
DCT\
Direct\
DFS\
Deutsche Flugsicherung GmbH\
DMAN\
Departure Manager\
DPI\
Departure Planning Information\
DSNA\
Direction des Services de la Navigation A\'e9rienne\
EAT\
Estimated/Expected Approach Time\
ECAC\
European Civil Aviation Conference\
E-DPI\
Early DPI Message based on expected aircraft ready time\
EEC\
EUROCONTROL Experimental Centre\
EET\
Estimated Elapsed Time\
EFD\
ETFMS Flight Data\
EH\
Eligibility Horizon\
ELDT\
Estimated Landing Time\
ENR\
En-route\
ENV\
Environment\
EOBT\
Estimated Off Block Time\
E-OCVM\
European Operational Concept Validation Methodology\
E-TMA\
Extended-Terminal Manoeuvring Area\
ETA\
Estimated Time of Arrival\
ETFMS\
Enhanced Tactical Flow Management System\
ETO\
Estimated Time Over\
ETOT\
Estimated Take-Off Time\
EUROCONTROL\
European Organisation for the Safety of Air Navigation\
FABEC\
Functional Airspace Block Europe Central\
FAF\
Final Approach Fix\
FH\
Frozen Horizon \
FDPS\
Flight Data Processing System\
FIR\
Flight Information Region\
FIXM\
Flight Information Exchange Model\
FL\
Flight Level, unit of altitude (expressed in 100's of feet)\
FLAS\
Flight Level Allocation Scheme\
FMS\
Flight Management System\
FPL\
Flight Plan\
FSA\
First System Activation Message \
FUM\
Flight Update Message\
HF\
Human Factor\
HMI\
Human Machine Interface\
HR\
Human Resources\
IAF\
Initial Approach Fix\
IAS\
Indicated Air Speed\
IBP\
Industry Based Platform\
ICAO\
International Civil Aviation Organisation\
IFPS\
Integrated Initial Flight Plan System\
IMH\
Initial Metering Horizon\
IMP\
Initial Metering Point\
IOP\
Interoperability\
KPA\
Key Performance Area\
KPI\
Key Performance Indicator\
Kts\
Knots\
LOA\
Letter Of Agreement\
LVNL\
Luchtverkeersleiding Nederland (Air Traffic Control the Netherlands)\
LVP\
Low Visibility Procedures\
MET\
Meteorological Information\
MONA\
ATC Monitoring Aids\
MOPS\
Method of Operations\
MP\
Metering Point\
MUAC\
Maastricht Upper Area Control Centre\
NATS\
National Air Traffic Services\
NM\
Nautical Miles\
NOP\
Network Operations Plan\
OCD\
Operational Concept Document\
ODT\
Operational Requirements and Data Processing Team\
OLDI\
On-Line Data Interchange\
OR\
Operational Requirement\
OSED\
Operational Service and Environment Description\
PAC\
Pre-Activation Message (OLDI)\
PBN\
Performance Based Navigation\
P-RNAV\
Precision Area Navigation\
RADNET\
Radar Data Network\
RBT\
Reference Business Trajectory\
RDA\
Runway Delay Allocation\
RDPS\
Radar Data Processing System\
REV\
Revision Message\
RNP\
Required Navigation Performance\
R/T\
Radio Telephony\
RTA\
Required Time of Arrival\
RTD\
Required Time of Departure\
RTE\
Route\
RTS\
Real Time Simulation\
RWY\
Runway\
SA\
Situation Awareness\
SAAM\
System for traffic Assignment &Analysis at Macroscopic level\
SAF\
Safety \
SARA\
Speed And Route Advisories\
SEC\
Security\
SEQ\
Sequence\
SESAR\
Single European Sky ATM Research Programme\
SID\
Standard Instrument Departure\
SJU\
SESAR Joint Undertaking (Agency of the European Commission)\
STA\
Scheduled Time of Arrival\
STAR\
Standard Terminal Arrival Route\
STO\
Scheduled Time Over\
SWIM\
System-Wide Information Management \
TBC\
To Be Completed\
TBD\
To Be Decided\
TBFM\
Time Based Flow Management\
TBO\
Trajectory Based Operations\
TDD\
Tactical Delay Distribution\
TiBO\
Time Based Operations\
TLDT\
Target Landing Time\
TMA\
Terminal Control Area\
TOBT\
Target Off Block Time\
TOC\
Top Of Climb\
TOD\
Top of Descent\
TOM\
Time Over Metering point\
TP\
Trajectory Prediction or Predictor \
TSAT\
Target Start Up Approval Time\
TTA\
Target Time of Arrival at Runway\
TTG\
Time To Gain\
TTL\
Time to Lose\
TTO\
Target Time Over\
TTOT\
Target Take-Off Time\
UAC\
Upper Area Control\
UNL\
Unlimited\
V1, V2\'85 V7\
Concept Lifecycle Model Phases V1 to V7\
VALP\
Validation Plan\
VALR\
Validation Report\
VDL\
VHF Datalink\
WAN\
Wide Area Network\
XMAN\
Cross Border Arrival Management\
\
}