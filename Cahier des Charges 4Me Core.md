#Introduction
L’IHM 4Me répond à un besoin d’intégration de plusieurs services non connecté aux systèmes opérationnels sur la position de contrôle. L’application 4Me est à la fois destinée à l’accueil d’applicatif existant comme XMAN et aux applicatifs futurs comme ARCID. 

4Me devra être le support de nouveaux concepts opérationnels en expérimentation. Les IHM 4Me sont paramétrées par secteur et par regroupement de secteur, celles ci doivent donc correspondre au secteur réellement ouvert sur la position de contrôle.
Ce document a pour but d’identifier et d’exprimer les besoins pour la réalisation de l’IHM présentant aux différents acteurs opérationnels et techniques les informations nécessaires à l’intégration des différents services ATM Light.
##Documents applicables :
[1] Cahier Des Charges XMAN 4Me
[2] Cahier Des Charges XMAN ARCID
[3] Note d’Architecture Technique
[4] 
##Terminologie :
Voir Annexes 2 et 3.
##Présentation du système
##Finalité, mission et objectifs du système
###Finalité du système : 
- Pour les applicatifs définis, la finalité du système est d’intégrer des applicatifs indépendants dans une seule IHM et de fournir à l’utilisateurs des données sur l’etat des services ainsi que des notifications d’action à réaliser.
###Missions :
Pour chaque  service  concerné, le système permettra :
- permettre à l'utilisateur l'utilisation de chaque service.
- d’informer les acteurs opérationnels de la nécessité d’une action.
- d’informer les acteurs opérationnels de l’état de service des applicatifs.
###Objectifs du système évaluables :
Présentation de 100% des données de chaque service.

##Parties prenante
###DSNA/DTI
	Définition des exigences et de l’architecture techniques coté DSNA
###CRNA-Est
-Gestion de Projet
###Service Technique
####Installation et maintenance de l'outil.
###Service Exploitation
####Projet 4Me
- Définition des besoins (Ateliers Développement Outils)
- Analyse et Conception (Sub ETU)
####Subdivision ETU
- Suivi de l’outil après MESO
- Analyse post-opératoire sur la base des logs de l’outil.

####Chef de Salle 
Utiliser l’IHM 4Me SPVR pour mapper correctement les IHM Secteur 4Me en salle de contrôle et assurer ainsi la correspondance entre les secteurs ouverts sur la position de contrôle et l’IHM 4Me Secteur.
####ACDS
Utilise l’IHM 4Me pour y intégrer les données ad hoc correspondant aux services dont il a la responsabilité.
####CWP
Secteurs de contrôle mettent en œuvre les procédures relatives aux services intégrés dans 4Me. Ce sont les utilisateurs principaux de l’IHM.
##Environnement & Contexte opérationnel
Les contrôleurs utilisent l’IHM directement sur les positions de contrôle où elle est déployée sur un écran « 4ME » à vocation multiservices qui est dédié à des applications non connectées au système opérationnel.

Les CDS et ACDS utilisent l’IHM sur les postes « 4ME » déployés à l’îlot central. Les clients IHM déployés sur ces postes ont des besoins et fonctionnalités spécifiques. Ils peuvent être considérés comme des clients-maîtres.

Le service technique utilise en salle de paramétrage, un client IHM spécifique permettant le monitoring des services d’acquisition de données et  la relance de l’applicatif. 

Même si le niveau de criticité est faible, l’outil est utilisé de façon opérationnelle. A ce titre, il doit respecter les règles de 
développement en vigueur à la DSNA (METLOG).

L'intégrité et la disponibilité des informations sont importantes dans le domaine ATC toutefois en ce qui concerne les services proposés par 4Me :
- La perte totale des informations n’a pas d’impact sécurité : l’indisponibilité du système est notifiée aux centres impactés, 
- La corruption détectable des informations n’a pas d’impact sécurité, l’information erronée étant annulée par les contrôleurs ou les équipages avant application. Cette situation conduit les opérateurs à déclarer le système comme indisponible et ramène au cas précédent.
- La corruption non détectable des informations a un impact limité sur la sécurité qui est lié à une éventuelle augmentation des coordinations avec les centres en aval qui auraient une vision différente de la situation.

La plupart des utilisateurs opérationnels n'ont pas de connaissance informatique poussée et il n’est pas prévu d’outil de supervision pour la maintenance opérationnelle au service technique. 

Des informations de diagnostic simples sur l’état connu du service sont nécessaires pour que les acteurs opérationnels puissent effectuer les coordinations nécessaires avec les centres avals et la maintenance opérationnelle. Pour cette dernière, des fonctionnalités simples de relance à chaud depuis le client en salle de paramétrage sont à prévoir.

##Cycle de vie
Pour ce qui concerne le déploiement et la mise en service opérationnelle au CRNA/Est, l'outil sera conçu, développé, installé, exploité et maintenu par le CRNA/Est.
L'outil pourra etre mis à disposition des autres centres de la DSNA mais leur conception, developpement, installation, exploitation et maintenance seront réalisé par le centre en question.

#Analyse de l’existant
##Presentation Générale du webservice (cas de EGLL)
Pour le centre de LACC (Swanwick) où il est installé, le webservice est un nouveau composant du système ATFM. Le serveur SWIM-WS reçoit de l’AMAN chaque message d’information de gestion des arrivées comprenant la séquence et le délai sous la forme d’un message au format xml. Il publie ensuite ce message auprès de clients extérieurs qui en font la requête (principe de Request/Reply) via différents réseaux.

L’architecture réseau pour la DSNA est la suivante : (Cf Note d’AT produite par DTI/ESA)

##Schema descriptif des messages d’information de gestion des arrivees
Chaque message d’information de gestion des arrivées à requérir auprès du webservice comprend notamment :
- L’information de séquence à la piste
- La stratégie d’utilisation des pistes
- Les informations de délai total ou partagé
-  Les heures souhaitées de passage au COP, à l’IAF et au seuil de piste
Le service est dépendant de l’AMAN du NATS qui produit le message pour ce service.
Le schéma de complet de description de la charge utile est le suivant :

##Description de l’interface 
- Bandeau d’état de service :
- Bandeau latéral de service :
- Pavé d’applicatif:

##Scénario de travail
###Scenario 1

###Scenario 2 :

###Scenario 3 :

###Scenario 4 : 

###Scenario 5 :
Pour faciliter les analyses post-opératoires des dysfonctionnements, et répondre aux interrogations des contrôleurs sur le comportement des outils, il est plus efficace de rejouer une situation sur l’IHM que de procéder à l’analyse fastidieuse des fichiers.
##Synthèse des scénarios de travail
### Synthèse des points faibles et besoins correspondants
|Id|Point faible|Origine (indiquer le ou les scénarios mettant en valeur le point)|Expression du besoin|
|---|---|---|---|
|1|Pas d’acquisition possible des données produites par l’AMAN et mises à disposition au niveau du webservice par l’intermédiaire des connections existantes (Msg OLDI AMA par ex)  |Scénario n°1|L'outil permet de d’acquérir et d’afficher les données d’information de gestion des arrivées au niveau du webservice mis en place à cet effet.|
|2|Pas de proposition de vitesse produite par l’AMAN.|Scénario n°2|L'outil permet de proposer aux contrôleurs une conversion du délai à absorber en une proposition de réduction de point de Mach.|
|3|Pas de possibilité dans le système ATM actuel de renseigner et partager les instructions de contrôle de vitesse transmises aux équipages.|Scénario n°3|L'outil permet aux contrôleurs de renseigner les instructions de réduction de point de Mach transmises aux équipages et de les partager entre les différentes IHM.|
4|Pas d’archivage des données du côté du centre amont en particulier pour ce qui concerne les instructions de contrôle de vitesse transmises aux équipages|Scénario n°4|L’outil permet d’enregistrer et de stocker les données d’information de gestion des arrivées acquises auprès du webservice ainsi que les instructions de réduction de point de Mach transmises aux équipages y compris le lieu, l’heure et le secteur concerné au moment de l’application.
5|Pas de rejeu possible des données d’information de gestion des arrivées reçues dans le passé|Scénario n°5|L’outil permet de rejouer des données d’information de gestion des arrivées reçues dans le passé et stockées localement.

###Synthèse des points forts et besoins correspondants
ID|Point fort|Origine|Expression du besoin
---|---|---|---|
1|Les contrôleurs intègrent les informations de gestions des arrivées et  propositions de réduction de point de Mach dans leur analyse. Ils valident la pertinence de leur prise en compte en fonction de leur charge de travail et de la situation aérienne globale|Scénario 1, 2et 3|L'outil fournit une information complémentaire à celles qui sont déjà accessibles par l’ATC et qui restent LA référence pour ce qui concerne les conditions de sortie. Elles ne permettent sur la base du principe « Best effort » que d’améliorer l’efficacité « carburant » des vols à l’arrivée.
2|La disponibilité de l’AMAN et duwebservice est réputée bonne.|Spécifications AMAN et Webservice|Du point de vue du centre aval, l’AMAN et le webservice associée sont des systèmes opérationnels ayant un niveau de criticité relativement fort et ainsi supervisés pour atteindre une disponibilité élevée.


#	Analyse Fonctionnelle
##Éléments du Milieu Extérieur (EME) :
- Contrôleurs Exécutif ou Planneur sur position de contrôle (CWP)
- Chef de Salle et ACDS
- Subdivision Études
- Service Technique
##Fonctions principales :
-FP1 : Afficher une sélection des éléments présents dans les messages d’information de gestion des arrivées complétée d’éléments de données RADAR
-FP2 : Produire une proposition de réduction de point de Mach fonction du délai attribué au centre DSNA concerné.
-FP3 : Recueillir et partager entre toutes les IHM, les instructions de réduction de point de Mach transmises par les contrôleurs aux équipages.
-FP4 : Permettre à des clients-maître de piloter des fonctions particulières (ON/OFF, relance …)
-FP5 : Enregistrer et stocker les données relatives à la gestion des arrivées aux fins d’analyses post-opératoires et de rejeux.
-FP6 : Rejouer une situation antérieure

##Fonctions contraintes :
-FC1 : Être tolérant à l’interruption de la production des messages d’information de gestion des arrivées par le webservice distant ou à l’interruption de réception de données RADAR.
-FC2 : L'outil devra pouvoir être adaptatif pour inclure ultérieurement des informations de gestion des arrivées pour d’autres aéroports.
-FC3 : Offrir une interface simple d’utilisation.

##Relations entre fonctions et EME
Les relations entre les différentes fonctions et les EME sont représentées sur la pieuvre ci-après :


##Justification des fonctions et critères de valeur 
###Origine des fonctions et critères de valeur

|Fonction|ID point faible|Critère de valeur|
|---|---|---|
|FP 1|1, 4, 5|Acquérir les informations de gestion des arrivées à une fréquence d’au moins 1 message correct par minute. Acquérir les informations RADAR pour les vols de la séquence pour lesquels elles sont disponibles dans 80% des cas. Afficher les données choisies pour  100% des messages correctement acquis auprès du webservice|
|FP 2|2, 4, 5|Production d’une proposition de réduction de vitesse selon l’algorithme proposé pour 100% des vols présents dans la séquence contenue dans les messages correctement acquis.|
|FP 3|3, 4|100% des informations saisies par les contrôleurs sont correctement enregistrées et partagées.|
|FP 4|NA|Les CDS, ACDS, opérateur de maintenance doivent avoir accès à des fonctions privilégiées.|
|FP5|4, 5|100% des informations reçues et celles saisies par les contrôleurs sont correctement enregistrées et stockées.|
|FP6|5|L'outil permet de rejouer une situation passée pour l'afficher dans la même interface de visualisation.|
|FC1|NA|En cas d’interruption prolongée de la réception des messages d’information de gestion des arrivées, l’outil doit indiquer le non rafraichissement des données sans pour autant provoquer l’arrêt de l’applicatif. L’applicatif doit être tolérant à l’absence de données RADAR. 
|FC2|NA|L’outil doit être développé de façon générique de façon à pourvoir être étendu rapidement à d’autres aéroports (LSZH par exemple) 
|FC3|NA|L’IHM doit proposer aux contrôleurs une vision claire des vols soumis aux procédures XMAN. Elle permet notamment de renseigner les instructions transmises en un seul clic. Par ailleurs, l’IHM sur les secteurs de contrôle ne doit  faire appel à aucune saisie clavier.

#Besoins
##Modèle conceptuel des données du domaine
Le diagramme ci-après permet de se représenter les différentes entités mises en œuvre et les relations entre elles. Il ne présume en rien des classes réellement utilisées dans le code.

##Cas d’utilisation (Use Cases)
La figure ci-dessous représente les cas d'utilisations que devra réaliser le futur outil :

###Description des Cas d'Utilisation du système
|Cas d’utilisation|Description|
|---|---|
|CU1 – Calculer Mach Réduction|Fournir aux utilisateurs une proposition de réduction de point de Mach qui correspond au délai alloué pour chaque vol. Voir Annexe 1 pour une description de l'interface souhaitée.ex : ade|
|CU2 – Générer des archives|Créer des archives de manière automatique (tout ce qui est reçu et calculé) et manuelle (sur action utilisateur).|
|CU3 – Rejouer des archives|Permettre à des utilisateurs de rejouer des archives afin de pouvoir observer une situation passée. L'outil de visualisation utilisé sera le même que celui utilisé en temps réel.|
|CU4 – Paramétrer |Permettre à un utilisateur de paramétrer l'application du point de vue super-utilisateur (ex : ON/OFF procédures XMAN; Procédures Minimum Clean Speed)|
|CU5 – Relancer|Permettre à un utilisateur de maintenance opérationnelle une analyse simple de l’état des services pour une relance rapide de l’applicatif.|

##Synthèse des besoins
###Tableau de synthèse des besoins
Dans le tableau ci-dessous, sont regroupés tous les besoins associés au système.
Niveau de priorité : 1 = le plus prioritaire, 5 = le moins prioritaire

|Identifiant|Besoin|Justification|Priorité|
|---|---|---|---|
|B1|Fonctions||
|B1.1|Afficher verticalement la liste des vols à destination de EGLL qui sont dans la zone de responsabilité du CRNA/Est classés selon l’heure estimée de passage à ABNUR de la plus petite à la plus grande.|FP1, CU1|1|
|B1.2|Un paramétrage client permet d’effacer les vols lorsqu’ils sont sortis de l’emprise géographique du secteur auquel est affecté l’IHM.|FP1, CU 1|3|
|B1.3|Afficher la configuration piste à EGLL|Atelier XMAN|4|
|B1.4|Afficher l’heure UTC courante|Atelier XMAN|2|
|B1.5|Pour chaque vol, on indique :Delay Total courant Indicatif (ARCID) Flight Level courant (Mode C) Heure calculée comme objectif à ABNUR par l’AMAN Délai alloué à Reims selon la stratégie de répartition du délai|FP1, CU1|1
|B1.6|Les champs ARCID, Mode C, TT@ABNUR, Reims Delay permettent d’identifier les états suivants :Vols en dehors de la plage horaire de mise en œuvre des procédures XMAN  (ARCID en blanc et « zZzzZz » dans les autres champs) Vols situés entre l’horizon d’éligibilité (ie présent dans la séquence) et l’horizon d’activité (350NM de EGLL) (ARCID et Mode C en blanc et absence de valeur TT@ABNUR et Reims Delay) Vols avec un délai Reims nul (toutes valeurs en blanc) Vols avec un délai Reims à résorber sans action réalisée (toutes valeurs en jaune) Vols pour lesquels une action a été réalisée (toutes valeurs en vert)|FP1, CU1|1
B1.7|La valeur du Mode C est NA s’il n’y a pas de données RADAR disponible pour le vol considéré.|FP1, CU1|3
B1.8|Un codage couleur est appliqué à la valeur de délai total : Blanc: délai total ≤ 5’ Jaune : 6’ ≤ délai total ≤ 7’ Orange : 7’ ≤ délai total|FP1, CU1, Atelier XMAN|2
B1.9|Pour chaque vol, en fonction du délai Reims, l’opérateur est informé de la réduction de point de Mach proposée pour absorber le délai considérer selon la table au §3.4|FP2, CU1|1
B1.10|Pour chaque vol, l’opérateur peut indiquer la valeur de la réduction de point de Mach qui a été transmise à l’aéronef.|FP3, CU1|1
B1.11|Toutes les informations entrées à l’IHM par un opérateur sur un vol donné doivent être partagées sur l’ensemble des IHM affichant ce vol.|FP3, CU1|1
B1.12|Un codage couleur doit permettre d’identifier si l’instruction transmise correspond ou pas à la proposition initiale.|FP3, CU1|2
B1.13|L’opérateur doit pouvoir indiquer si l’instruction transmise a été modifiée suite à impossibilité pour l’équipage d’accepter la proposition initiale.|FP3, CU1|2
B1.14|Pour les vols ayant un délai Reims non nul, une alarme visuelle doit indiquer pour chaque secteur si aucune action n’a été réalisée 20NM après la présentation initiale du délai ou 20NM après l’entrée secteur si la présentation initiale du délai a été faite dans un secteur amont|FP1, CU1|3
B1.15|En cas d’erreur de saisie, l’opérateur doit pouvoir remettre l’IHM à l’état immédiatement précédent.|Atelier XMAN, CU1|3
B1.16|Pour chaque vol, l’identification du secteur qui a transmis la dernière instruction de vitesse doit être partagée, sur toutes les IHM affichant le vol.|FP3, CU1|1
B1.17|Un paramétrage client permet de particulariser les IHM ACDS, CDS et Technique avec des fonctionnalités supplémentaires.|FP4, CU4|3
B1.18|Depuis les clients CDS et ACDS, il est possible de faire afficher à la demande sur l’ensemble des IHM un message en surimpression pour indiquer qu’il a été décidé par le couple CDS/ACDS de ne pas appliquer les procédures XMAN.|FP4, CU4|2
B1.19|Un message en surimpression s’affiche automatiquement pour indiquer que les données ne sont plus mises à jour.|FC1|1
B1.20|Depuis les clients CDS et ACDS, il est possible de forcer une indication « Minimum Clean Speed » à la place des propositions de réduction de point de Mach.|FP4, CU4|2
B1.20|Le système devra proposer une supervision simple ou des informations techniques permettant un diagnostic de son état.|FP4, CU5|4
B2|Performances attendues||
B2.1|Acquérir les informations de gestion des arrivées à une fréquence d’au moins 1 message correct par minute.|FP1, CU1|1
B2.2|Afficher les données choisies pour  100% des messages correctement acquis auprès du webservice|FP1, CU1|1
B2.3|Production d’une proposition de réduction de vitesse selon l’algorithme proposé pour 100% des vols présents dans la séquence contenue dans les messages correctement acquis.|FP1, CU1|1
B2.4|Acquérir les informations RADAR pour les vols de la séquence pour lesquels elles sont disponibles dans 80% des cas.|FP1, CU1|4
B2.5|Production d’une proposition de réduction de vitesse selon l’algorithme proposé pour 100% des vols présents dans la séquence contenue dans les messages correctement acquis.|FP2, CU1|1
B2.6|100% des informations saisies par les contrôleurs sont correctement enregistrées et partagées.|FP3, CU1, CU2|1
B2.7|100% des informations reçues et celles saisies par les contrôleurs sont correctement enregistrées et stockées.|FP4, CU2|2
B3|Interfaces||
B3.1|L’outil doit être développé de façon générique de façon à pourvoir être étendu rapidement à d’autres aéroports (LSZH par exemple)|FC2|3
B4|Scénarios opérationnels||
B4.1|Le système permet de réaliser le cas d’utilisation CU1|CU1 et Annexe 1|1
B4.2|Le système permet de réaliser le cas d’utilisation CU2|CU2|1
B4.3|Le système permet de réaliser le cas d’utilisation CU3|CU3|3
B4.4|Le système permet de réaliser le cas d’utilisation CU4|CU4|3
B4.5|Le système permet de réaliser le cas d’utilisation CU5|CU5|4
B5|Contraintes|||
B5.1|Le développement du système respecte la METLOG|Environnement et contexte opérationnel|2
B5.2|En cas d’interruption prolongée de la réception des messages d’information de gestion des arrivées, l’outil doit indiquer le non rafraichissement des données sans pour autant provoquer l’arrêt de l’applicatif.L’applicatif doit être tolérant à l’absence de données RADAR.|FC1|1|
|B5.3|L’IHM doit proposer aux contrôleurs une vision claire des vols soumis aux procédures XMAN. Elle permet notamment de renseigner les instructions transmises en un seul clic. Par ailleurs, l’IHM sur les secteurs de contrôle ne doit  faire appel à aucune saisie clavier.|FC3 et Annexe 1|1|


