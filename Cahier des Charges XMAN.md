#Introduction
L’IHM 4Me répond à un besoin d’intégration de plusieurs services non connecté aux systèmes opérationnels sur la position de contrôle. L’application 4Me est   à la fois destinée à l’accueil d’applicatif existant comme XMAN et aux applicatifs futurs. 4Me devra être le support de nouveaux concepts opérationnels en expérimentation. Les IHM 4Me sont paramétrées par secteur et par regroupement de secteur, celles ci doivent donc correspondre au secteur réellement ouvert sur la position de contrôle.
Ce document a pour but d’identifier et d’exprimer les besoins pour la réalisation de l’IHM présentant aux différents acteurs opérationnels et techniques les informations nécessaires à l’intégration des différents services ATM Light.
##Documents applicables :
[1] 
[2] 
[3] Note d’Architecture Technique
[4] 
##Terminologie :
Voir Annexes 2 et 3.
##Présentation du système
##Finalité, mission et objectifs du système
- Finalité du système : Pour les applicatifs définis, la finalité du système est d’intégrer des applicatifs indépendants dans une seule IHM et de fournir à l’utilisateurs des données sur l’etat des services ainsi que des notifications d’action.
- Missions : Pour chaque  service  concerné, le système permettra :
o	d’informer les acteurs opérationnels de la nécessité d’une action,
o	d’informer les acteurs opérationnels de l’état de service des applicatifs
-Objectifs du système évaluables : Présentation de 100% des données de chaque service

##Parties prenante
###DSNA/DTI
	Définition des exigences et de l’architecture techniques coté DSNA
###Service Technique
####Installation et maintenance de l'outil.
###Service Exploitation
####Projet XMAN
- Gestion de projet
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
Les contrôleurs utilisent l’IHM directement sur les positions de contrôle où elle est déployée sur un écran « 4ME » à vocation multiservices qui est dédiées à des applications non connectées au système opérationnel.
Les CDS et ACDS utilisent l’IHM sur les postes « 4ME » déployés à l’îlot central. Les clients IHM déployés sur ces postes ont des besoins et fonctionnalités spécifiques. Ils peuvent être considérés comme des clients-maîtres.
Le service technique utilise en salle de paramétrage, un client IHM spécifique permettant le monitoring des services d’acquisition de données et  la relance de l’applicatif. 
Même si le niveau de criticité est faible, l’outil est utilisé de façon opérationnelle. A ce titre, il doit respecter les règles de développement en vigueur à la DSNA (METLOG).
L'intégrité et la disponibilité des informations sont importantes dans le domaine ATC toutefois en ce qui concerne les services proposés par 4Me :
- La perte totale des informations n’a pas d’impact sécurité : l’indisponibilité du système est notifiée aux centres impactés, 
- La corruption détectable des informations n’a pas d’impact sécurité, l’information erronée étant annulée par les contrôleurs ou les équipages avant application. Cette situation conduit les opérateurs à déclarer le système comme indisponible et ramène au cas précédent.
- La corruption non détectable des informations a un impact limité sur la sécurité qui est lié à une éventuelle augmentation des coordinations avec les centres en aval qui auraient une vision différente de la situation.

La plupart des utilisateurs opérationnels n'ont pas de connaissance informatique poussée et il n’est pas prévu d’outil de supervision pour la maintenance opérationnelle au service technique. Des informations de diagnostic simples sur l’état connu du service sont nécessaires pour que les acteurs opérationnels puissent effectuer les coordinations nécessaires avec les centres avals et la maintenance opérationnelle. Pour cette dernière, des fonctionnalités simples de relance à chaud depuis le client en salle de paramétrage sont à prévoir.

##Cycle de vie
Pour ce qui concerne le déploiement et la mise en service opérationnelle au CRNA/Est, l'outil sera conçu, développé, installé, exploité et maintenu par le CRNA/Est.

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

Sur les plages horaires 06h30 à 22h00 UTC (heure d’hiver) et 05h30 à 21h00 UTC (heure d’été), les procédures XMAN EGLL sont en vigueur.
Grâce à la prise en compte des données ETFMS, l’AMAN EGLL commence à élaborer ses séquences 85 min (environ 550NM) avant la piste. Le délai calculé à la piste est alors partagé entre les différents acteurs : LATC (Terminal Center), LACC (Area Center) et un centre en route dont Reims UAC pour le flux d’arrivée via ABNUR.
La table ci-après résume la stratégie de répartition du délai :

La répartition du délai est appliquée au niveau du webservice de l’AMAN et le fichier obtenu après requête contient donc pour chaque vol le délai total et le délai Reims.
###Scenario 2 :
L’horizon d’activité pour XMAN EGLL a été fixé avec les partenaires à 350NM de la piste. A l’intérieur de cet horizon, les secteurs des centres amont appliquent les réductions de vitesse qui permettent d’absorber le délai qui leur est attribué.

Une réduction de vitesse est proposée aux contrôleurs pour absorber le délai attribué à Reims UAC. Ellen’est pas fournie par le message d’information de gestion des arrivées et doit donc être le résultat d’un calcul local. Dans un premier temps, une approche simpliste pourra être utilisée selon les principes suivants :

###Scenario 3 :
Les contrôleurs du centre amont renseignent l’IHM des réductions de vitesse qu’ils ont implémentées de façon à ce que l’information soit partagée entre les différents acteurs opérationnels au niveau de ce centre. Dans un premier temps, cette information reste interne au centre amont et n’est pas partagée avec le centre aval.
###Scenario 4 : 
###Scenario 5 :
Pour faciliter les analyses post-opératoires des dysfonctionnements, et répondre aux interrogations des contrôleurs sur le comportement des outils, il est plus efficace de rejouer une situation sur l’IHM que de procéder à l’analyse fastidieuse des fichiers.
##Synthèse des scénarios de travail
|Id|Point faible|Origine (indiquer le ou les scénarios mettant en valeur le point)|Expression du besoin|
|---|---|---|---|
|1|Pas d’acquisition possible des données produites par l’AMAN et mises à disposition au niveau du webservice par l’intermédiaire des connections existantes (Msg OLDI AMA par ex)  |Scénario n°1|L'outil permet de d’acquérir et d’afficher les données d’information de gestion des arrivées au niveau du webservice mis en place à cet effet.|
|2|Pas de proposition de vitesse produite par l’AMAN.|Scénario n°2|L'outil permet de proposer aux contrôleurs une conversion du délai à absorber en une proposition de réduction de point de Mach.|
I3
Pas de possibilité dans le système ATM actuel de renseigner et partager les instructions de contrôle de vitesse transmises aux équipages.
Scénario n°3
L'outil permet aux contrôleurs de renseigner les instructions de réduction de point de Mach transmises aux équipages et de les partager entre les différentes IHM.
4
Pas d’archivage des données du côté du centre amont en particulier pour ce qui concerne les instructions de contrôle de vitesse transmises aux équipages
Scénario n°4
L’outil permet d’enregistrer et de stocker les données d’information de gestion des arrivées acquises auprès du webservice ainsi que les instructions de réduction de point de Mach transmises aux équipages y compris le lieu, l’heure et le secteur concerné au moment de l’application.
5
Pas de rejeu possible des données d’information de gestion des arrivées reçues dans le passé
Scénario n°5
L’outil permet de rejouer des données d’information de gestion des arrivées reçues dans le passé et stockées localement.
Tableau 1 : synthèse des points faibles et besoins correspondants
ID
Point fort
Origine
Expression du besoin
1
Les contrôleurs intègrent les informations de gestions des arrivées et  propositions de réduction de point de Mach dans leur analyse. Ils valident la pertinence de leur prise en compte en fonction de leur charge de travail et de la situation aérienne globale
Scénario 1, 2et 3
L'outil fournit une information complémentaire à celles qui sont déjà accessibles par l’ATC et qui restent LA référence pour ce qui concerne les conditions de sortie. Elles ne permettent sur la base du principe « Best effort » que d’améliorer l’efficacité « carburant » des vols à l’arrivée.
2
La disponibilité de l’AMAN et duwebservice est réputée bonne.
Spécifications AMAN et Webservice
Du point de vue du centre aval, l’AMAN et le webservice associée sont des systèmes opérationnels ayant un niveau de criticité relativement fort et ainsi supervisés pour atteindre une disponibilité élevée.
Tableau 2 : synthèse des points forts et besoins correspondants

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

##Relations entre fonctions et 4ME
Les relations entre les différentes fonctions et les EME sont représentées sur la pieuvre ci-après :











##Justification des fonctions et critères de valeur 
Fonction
ID point faible
Critère de valeur
FP 1
1, 4, 5
Acquérir les informations de gestion des arrivées à une fréquence d’au moins 1 message correct par minute.
Acquérir les informations RADAR pour les vols de la séquence pour lesquels elles sont disponibles dans 80% des cas.
Afficher les données choisies pour  100% des messages correctement acquis auprès du webservice
FP 2
2, 4, 5
Production d’une proposition de réduction de vitesse selon l’algorithme proposé pour 100% des vols présents dans la séquence contenue dans les messages correctement acquis.
FP 3
3, 4
100% des informations saisies par les contrôleurs sont correctement enregistrées et partagées.
FP 4
NA
Les CDS, ACDS, opérateur de maintenance doivent avoir accès à des fonctions privilégiées.
FP5
4, 5
100% des informations reçues et celles saisies par les contrôleurs sont correctement enregistrées et stockées.
FP6
5
L'outil permet de rejouer une situation passée pour l'afficher dans la même interface de visualisation.
FC1
NA
En cas d’interruption prolongée de la réception des messages d’information de gestion des arrivées, l’outil doit indiquer le non rafraichissement des données sans pour autant provoquer l’arrêt de l’applicatif. L’applicatif doit être tolérant à l’absence de données RADAR. 
FC2
NA
L’outil doit être développé de façon générique de façon à pourvoir être étendu rapidement à d’autres aéroports (LSZH par exemple) 
FC3
NA
L’IHM doit proposer aux contrôleurs une vision claire des vols soumis aux procédures XMAN. Elle permet notamment de renseigner les instructions transmises en un seul clic. Par ailleurs, l’IHM sur les secteurs de contrôle ne doit  faire appel à aucune saisie clavier.
Tableau 3 : Origine des fonctions et critères de valeur



#Besoins
##Modèle conceptuel des données du domaine
Le diagramme ci-après permet de se représenter les différentes entités mises en œuvre et les relations entre elles. Il ne présume en rien des classes réellement utilisées dans le code.


##Cas d’utilisation (Use Cases)
La figure ci-dessous représente les cas d'utilisations que devra réaliser le futur outil :

Cas d’utilisation
Description
CU1 – Calculer Mach Réduction
Fournir aux utilisateurs une proposition de réduction de point de Mach qui correspond au délai alloué pour chaque vol. Voir Annexe 1 pour une description de l'interface souhaitée.ex : ade
CU2 – Générer des archives
Créer des archives de manière automatique (tout ce qui est reçu et calculé) et manuelle (sur action utilisateur).
CU3 – Rejouer des archives
Permettre à des utilisateurs de rejouer des archives afin de pouvoir observer une situation passée. L'outil de visualisation utilisé sera le même que celui utilisé en temps réel.
CU4 – Paramétrer 
Permettre à un utilisateur de paramétrer l'application du point de vue super-utilisateur (ex : ON/OFF procédures XMAN; Procédures Minimum Clean Speed)
CU5 – Relancer
Permettre à un utilisateur de maintenance opérationnelle une analyse simple de l’état des services pour une relance rapide de l’applicatif.
Tableau 4 : Description des Cas d'Utilisation du système
5.3	Synthèse des besoins
Dans le tableau ci-dessous, sont regroupés tous les besoins associés au système.
Niveau de priorité : 1 = le plus prioritaire, 5 = le moins prioritaire
Identifiant
Besoin
Justification
Priorité
B1
Fonctions


B1.1
Afficher verticalement la liste des vols à destination de EGLL qui sont dans la zone de responsabilité du CRNA/Est classés selon l’heure estimée de passage à ABNUR de la plus petite à la plus grande.
FP1, CU1
1
B1.2
Un paramétrage client permet d’effacer les vols lorsqu’ils sont sortis de l’emprise géographique du secteur auquel est affecté l’IHM.
FP1, CU 1
3
B1.3
Afficher la configuration piste à EGLL
Atelier XMAN
4
B1.4
Afficher l’heure UTC courante
Atelier XMAN
2
B1.5
Pour chaque vol, on indique :
•	Delay Total courant
•	Indicatif (ARCID)
•	Flight Level courant (Mode C)
•	Heure calculée comme objectif à ABNUR par l’AMAN
•	Délai alloué à Reims selon la stratégie de répartition du délai
FP1, CU1
1
B1.6
Les champs ARCID, Mode C, TT@ABNUR, Reims Delay permettent d’identifier les états suivants :
•	Vols en dehors de la plage horaire de mise en œuvre des procédures XMAN  (ARCID en blanc et « zZzzZz » dans les autres champs)
•	Vols situés entre l’horizon d’éligibilité (ie présent dans la séquence) et l’horizon d’activité (350NM de EGLL) (ARCID et Mode C en blanc et absence de valeur TT@ABNUR et Reims Delay)
•	Vols avec un délai Reims nul (toutes valeurs en blanc)
•	Vols avec un délai Reims à résorber sans action réalisée (toutes valeurs en rouge)
•	Vols pour lesquels une action a été réalisée (toutes valeurs en vert)

FP1, CU1
1
B1.7
La valeur du Mode C est NA s’il n’y a pas de données RADAR disponible pour le vol considéré.
FP1, CU1
3
B1.8
Un codage couleur est appliqué à la valeur de délai total :
•	Jaune : délai total ≤ 5’
•	Orange : 6’ ≤ délai total ≤ 7’
•	Rouge : 7’ ≤ délai total
FP1, CU1, Atelier XMAN
2
B1.9
Pour chaque vol, en fonction du délai Reims, l’opérateur est informé de la réduction de point de Mach proposée pour absorber le délai considérer selon la table au §3.4
FP2, CU1
1
B1.10
Pour chaque vol, l’opérateur peut indiquer la valeur de la réduction de point de Mach qui a été transmise à l’aéronef.
FP3, CU1
1
B1.11
Toutes les informations entrées à l’IHM par un opérateur sur un vol donné doivent être partagées sur l’ensemble des IHM affichant ce vol.
FP3, CU1
1
B1.12
Un codage couleur doit permettre d’identifier si l’instruction transmise correspond ou pas à la proposition initiale.
FP3, CU1
2
B1.13
L’opérateur doit pouvoir indiquer si l’instruction transmise a été modifiée suite à impossibilité pour l’équipage d’accepter la proposition initiale.
FP3, CU1
2
B1.14
Pour les vols ayant un délai Reims non nul, une alarme visuelle doit indiquer pour chaque secteur si aucune action n’a été réalisée 20NM après la présentation initiale du délai ou 20NM après l’entrée secteur si la présentation initiale du délai a été faite dans un secteur amont.
FP1, CU1
3
B1.15
En cas d’erreur de saisie, l’opérateur doit pouvoir remettre l’IHM à l’état immédiatement précédent.
Atelier XMAN, CU1
3
B1.16
Pour chaque vol, l’identification du secteur qui a transmis la dernière instruction de vitesse doit être partagée, sur toutes les IHM affichant le vol.
FP3, CU1
1
B1.17
Un paramétrage client permet de particulariser les IHM ACDS, CDS et Technique avec des fonctionnalités supplémentaires.
FP4, CU4
3
B1.18
Depuis les clients CDS et ACDS, il est possible de faire afficher à la demande sur l’ensemble des IHM un message en surimpression pour indiquer qu’il a été décidé par le couple CDS/ACDS de ne pas appliquer les procédures XMAN.
FP4, CU4
2
B1.19
Un message en surimpression s’affiche automatiquement pour indiquer que les données ne sont plus mises à jour.
FC1
1
B1.20
Depuis les clients CDS et ACDS, il est possible de forcer une indication « Minimum Clean Speed » à la place des propositions de réduction de point de Mach.
FP4, CU4
2
B1.20
Le système devra proposer une supervision simple ou des informations techniques permettant un diagnostic de son état.
FP4, CU5
4
B2
Performances attendues


B2.1
Acquérir les informations de gestion des arrivées à une fréquence d’au moins 1 message correct par minute.
FP1, CU1
1
B2.2
Afficher les données choisies pour  100% des messages correctement acquis auprès du webservice
FP1, CU1
1
B2.3
Production d’une proposition de réduction de vitesse selon l’algorithme proposé pour 100% des vols présents dans la séquence contenue dans les messages correctement acquis.
FP1, CU1
1
B2.4
Acquérir les informations RADAR pour les vols de la séquence pour lesquels elles sont disponibles dans 80% des cas.
FP1, CU1
4
B2.5
Production d’une proposition de réduction de vitesse selon l’algorithme proposé pour 100% des vols présents dans la séquence contenue dans les messages correctement acquis.
FP2, CU1
1
B2.6
100% des informations saisies par les contrôleurs sont correctement enregistrées et partagées.
FP3, CU1, CU2
1
B2.7
100% des informations reçues et celles saisies par les contrôleurs sont correctement enregistrées et stockées.
FP4, CU2
2
B3
Interfaces


B3.1
L’outil doit être développé de façon générique de façon à pourvoir être étendu rapidement à d’autres aéroports (LSZH par exemple)
FC2
3
B4
Scénarios opérationnels


B4.1
Le système permet de réaliser le cas d’utilisation CU1
CU1 et Annexe 1
1
B4.2
Le système permet de réaliser le cas d’utilisation CU2  
CU2
1
B4.3
Le système permet de réaliser le cas d’utilisation CU3  
CU3
3
B4.4
Le système permet de réaliser le cas d’utilisation CU4  
CU4
3
B4.5
Le système permet de réaliser le cas d’utilisation CU5
CU5
4
B5
Contraintes


B5.1
Le développement du système respecte la METLOG
Environnement et contexte opérationnel
2
B5.2
En cas d’interruption prolongée de la réception des messages d’information de gestion des arrivées, l’outil doit indiquer le non rafraichissement des données sans pour autant provoquer l’arrêt de l’applicatif.L’applicatif doit être tolérant à l’absence de données RADAR.
FC1
1
B5.3
L’IHM doit proposer aux contrôleurs une vision claire des vols soumis aux procédures XMAN. Elle permet notamment de renseigner les instructions transmises en un seul clic. Par ailleurs, l’IHM sur les secteurs de contrôle ne doit  faire appel à aucune saisie clavier.
FC3 et Annexe 1
1
Tableau 5 : Tableau de synthèse des besoins

Annexe 1 : Description de l’interface secteur


Annexe 2: Glossaire
Term
Definition
Active Advisory Area
Located between the Frozen Horizon and the Active Advisory Horizon and encompasses the different minimum stability threshold levels which ANSP’s may require to begin sending advisories to upstream centres
Active Advisory Horizon
The point from which XMAN advisories are acted upon
4D Contract
An ATC clearance that prescribes the containment of the trajectory in all 4 dimensions for the period of the contract during which the uncertainty associated with future predicted position does not increase with the prediction horizon.
4D Trajectory
A set of consecutive segments linking waypoints and/or points computed by FMS (airborne) or by TP (ground) to build the vertical profile and the lateral transitions; each point defined by a longitude, a latitude, a level and a time.
Actor
An implementation independent unit of responsibility that performs an action to achieve an effect that contributes to a desired end state.
Airborne Delay
Delay incurred in the air, either en-route or when holding.
Airspace
A defined three dimensional region of space relevant to air traffic.
Air Traffic Management
The aggregation of the airborne functions and ground-based functions (air traffic services, airspace management and air traffic flow management) required to ensure the safe and efficient movement of aircraft during all phases of operations.
Air Traffic Service
A generic term meaning variously, flight information service, alerting service, air traffic advisory service, air traffic control service (area control service, approach control service or aerodrome control service).
Air Traffic Services Unit
A generic term meaning variously, air traffic control unit, flight information centre or air traffic services reporting office.
Arrival Management Service
Arrival Management Service is provided through procedures used to establish sequences and related times e.g. as planned by an arrival manager.
Arrival Manager
An AMAN is a planning system to improve arrival flows at one or more airports by calculating the optimised approach / landing sequence and Target Landing Times (TLDT) and where needed times for specific fixes for each flight, taking multiple constraints and preferences into account.
Business Trajectory
A 4D trajectory which expresses the business or mission intentions of the user with or without constraints. It includes both ground and airborne segments of the aircraft operation (gate-to-gate) and is built from, and updated with, the most timely and accurate data available.
Collaborative Decision Making
A set of applications aimed at improving flight operations through the increased involvement of airspace users, ATM service providers, airport operators and other stakeholders in the process of air traffic management.
An environment in which the consequences of decisions taken are visible to all partners.
Concept of Operation
The tool used by an organisation to establish the desired approach it wishes to take to realise a system or service. The CONOPS documents the high level decisions and agreement that define the approach and the organisational structure needed to put that approach into operation.
Constraint
Any restriction brought to the preferred trajectory of an aircraft, being either a tactical constraint such as ATCO instruction, or a strategic constraint derived from the operations of the network.
Any limitation on the implementation of an AMAN Information Extension to En-route Sectors Concept of Operations operational improvement, or a limitation on reaching the desired level of service. We use this term generically to refer to time, speed, lateral and vertical data issued to the aircraft that restrict the options of the flight crew or FMS on how the aircraft is to be flown.
Constraint Waypoint
Waypoint for which a time constraint has been agreed.
Continuous Descent Operation
An operation, enabled by airspace design, procedure design and ATC facilitation, in which an arriving aircraft descends continuously, to the greatest possible extent, by employing minimum engine thrust, ideally in a low drag configuration, prior to the final approach fix /final approach point.
Controlled Time of Arrival
An ATM imposed time constraint at a point associated with the arrival of a flight.
Controlled Time Over
An ATM imposed time constraint over a point.
Departure Manager
A DMAN isa planning system to improve departure flows at one or more airports by calculating the Target Take Off Time (TTOT) and Target Start Up Approval Time (TSAT) for each flight, taking multiple constraints and preferences into account.
Eligibility Horizon
The point from which AMAN receives data and begins processing a sequence
ETA min/max
ETA min/max is a reliable earliest/latest ETA at a waypoint; wind/temp error is also taken into account in order to guarantee that any CTA defined within associated ETA min/max interval will be satisfied with high probability (95%).
The ETA min/max can be reported using ADS-C
Extended TMA (E-TMA)
The E-TMA corresponds to ACC terminal sector(s) (between Top Of Descent (ToD) and the Initial Approach Fix (IAF)) which make(s) the transition between the En-Route and the TMA sectors which encompass the Approach airspace (between IAF and Final Approach Fix (FAF) or transfer to the Tower).
In the present document, arrival management starts in E-TMA to feed TMA entry points.
Flight Object
The system instance view of a flight. It is the flight object that is shared between the IOP stakeholders.
Flight Plan
Specified information provided to air traffic services units, relative to an intended flight or portion of a flight of an aircraft.
Frozen Horizon
The point at which the AMAN landing sequence is fixed and cannot be changed automatically by AMAN
Ground Delay
Delay incurred on the ground, either at the gate or on the taxiway.
Interoperable
Characteristic indicating the ability to exchange, integrate and manage content between systems.
In Horizon Departures
Flights departing from Airports within the AAH of the Destination Airport
Level
A generic term relating to the vertical position of an aircraft in flight and meaning variously, height, altitude or flight level.
Level Constraint
The constraint defined by an objective to set the cleared flight level (CFL) for the flight.
Managed Airspace
Airspace in which all traffic is known to the Air Traffic System
Net-centric
Participating as a part of a continuously-evolving, complex community of people, devices, information and services interconnected by a communications network to achieve optimal benefit of resources and better synchronisation of events and their consequences. (Wikipedia)
Network Operations 
Plan
The Network Operations Plan is a set of collaborative applications providing access to traffic demand, airspace and airport capacity and constraints and scenarios to assist in managing diverse events. The aim of the NOP is to facilitate the processes needed to reach agreements on demand and capacity.
Operating Environment
An environment with a consistent type of flight operations.
Operational Concept
A proposed system in terms of the user needs it will fulfil, its relationship to existing systems or procedures and the ways it will be used. It is used to obtain consensus among the acquirer, developer, support, and user agencies on the operational concept of a proposed system.
Performance-Based Navigation
Area navigation based on performance requirements for aircraft operating along an ATS route, on an instrument approach procedure or in a designated airspace.
Pop Up Flights
Flights which are added into the sequence, and thus have delay and XMAN advisories assigned to them, only when they get airborne and not before due lack of accurate data
Pre-Planned Departures
Flights where ACDM / DPI information available thus could be added into the sequence before departure
Queue Management
The tactical establishment and maintenance of a safe, orderly and efficient flow of traffic. It includes the handling of queues, both in the air and on the ground. It operates on individual flights and is closely related to, and sometimes indistinguishable from, the Separation Provision process. It aims to facilitate the highest achievable capacity of the ATM System and to manage delays in a fuel-efficient and environmentally acceptable manner.
Reference Business 
Trajectory
The business trajectory which the airspace user agrees to fly and the ANSP and Airports agree to facilitate (subject to separation provision). Most times indicated in the RBT are estimates, some may be target times (TTA) to facilitate planning and some of them may become constraints (CTA, CTO) to assist in queue management when appropriate, e.g. at XMAN/AMAN horizon.
Required Navigation Performance
A statement of the navigation performance necessary for operation within a defined airspace.
Required Time of 
Arrival
Only refers to the aircraft FMS RTA function.
SARA
Speed and Route Advisory. An ATM tool that gives advice on speed and routing for inbound traffic to an airport.
SESAR Programme
The programme which defines the Research and Development activities and Projects for the SJU.
SJU Work Programme
The programme which addresses all activities of the SESAR Joint Undertaking Agency.
System Wide 
Information 
Management
A distributed processing environment which replaces data level interoperability and closely coupled interfaces with an open, flexible, modular and secure data architecture totally transparent to users and their applications.
Time Based Operation
Time-based Operations is the basis of the SESAR Concept. It focuses on flight efficiency, predictability and the environment. The goal is a synchronised European ATM system where partners are aware of the business and operational situations and collaborate to optimise their operations.
Top of Descend
The Top of Descend is the computed transition from the cruise phase of a flight to the descend phase, the point at which the planned descent to final approach altitude is initiated.
Trajectory Based Operations
SESAR Trajectory-based Operations focuses on a further-evolved flight efficiency, predictability and environment and adds capacity. The goal is a trajectory-based ATM system where partners optimise “business and mission trajectories” through common 4D trajectory information and user defined priorities in the network.
Trajectory Prediction
The trajectory prediction is continually updated and corresponds to what the aircraft is predicted to fly.
Traffic Metering
Traffic metering is the process of organising aircraft into a flow of aircraft with a specific rate.
Traffic Sequencing
Traffic sequencing is the process of organising aircraft into a specific order.
Vectoring

Air traffic controllers may have to vector aircraft on their course, e.g. in the frame of a tactical intervention involving a deviation from the planned route for safety reasons, or in a more systematic way – as is often the case in terminal airspace, to sequence aircraft towards the runway(s). 
Open-loop vectors, as opposed to closed-loop vectors, correspond to the case when no indication is given as to the duration or limit of the ATC vector instruction, nor how the aircraft will re-join its initial route. Typically, a simple heading instruction is an open-loop vector, while a “Direct-to” instruction is a closed-loop vector. 
Throughout this document, the term vectoring without additional indication refer to open-loop vectors.
XMAN
Cross Border Arrival Management (or Extended Arrival Management): Describes the extension of Arrival Management procedures across FIR borders with the help of upgraded AMAN systems and information provision to adjacent ATS units


Annexe 3: Abréviations et Acronymes
Term
Definition
AAA
Active Advisory Area
AAH
Active Advisory Horizon
ABI
Advance Boundary Information (OLDI)
ACARS
Aircraft Communications Adressing and Reporting System
A-DPI
Departure Progress Message with Actual Off-Block time
ACC
Area Control Centre
ACFT
Aircraft
ACK
Acknowledge
ACT
Activation Message (OLDI)
ADS-B/C
Automatic Dependent Surveillance – Broadcast/Contract
AIP
Aeronautical Information Publication
AFP
ATC Flight Plan Proposal
AMA
Arrival Management Message (OLDI)
AMAN
Arrival Manager (dedicated system support software) 
ANSP
Air Navigation Service Provider
AOI
Area of Interest
AOC
Airline Operations Centre
AOR
Area of Responsibility
APP
Approach control unit
ASAS
Airborne Separation Assistance System
ATC
Air Traffic Control
ATCO
Air Traffic Controller
ATD
Actual Time of Departure
ATFCM 
Air Traffic Flow and Capacity Management
ATM
Air Traffic Management
ATO
Actual Time Over
ATS
Air Traffic Services
ATSU
Air Traffic Service Unit
BADA
Base of Aircraft Data
CB
Cumulonimbus
CDA
Continuous Descent Approach
CDM
Collaborative Decision Making
CDO
Continuous Descend Operations
CHMI
Collaborative HMI
CNS
Communication Navigation Surveillance
CONOPS
Concept of Operations
COP
Coordination Point
CPDLC
Controller-Pilot Data Link Communications
CPR
Compact Position Reporting Message
CTA
Controlled Time of Arrival
CTO
Controlled Time Over/ Calculated Time over COP
CTOT
Calculated Take-Off Time 
CWP
Controller Working Position
CTA
Controlled Time of Arrival
DCB
Demand – Capacity Balancing
DCT
Direct
DFS
Deutsche Flugsicherung GmbH
DMAN
Departure Manager
DPI
Departure Planning Information
DSNA
Direction des Services de la Navigation Aérienne
EAT
Estimated/Expected Approach Time
ECAC
European Civil Aviation Conference
E-DPI
Early DPI Message based on expected aircraft ready time
EEC
EUROCONTROL Experimental Centre
EET
Estimated Elapsed Time
EFD
ETFMS Flight Data
EH
Eligibility Horizon
ELDT
Estimated Landing Time
ENR
En-route
ENV
Environment
EOBT
Estimated Off Block Time
E-OCVM
European Operational Concept Validation Methodology
E-TMA
Extended-Terminal Manoeuvring Area
ETA
Estimated Time of Arrival
ETFMS
Enhanced Tactical Flow Management System
ETO
Estimated Time Over
ETOT
Estimated Take-Off Time
EUROCONTROL
European Organisation for the Safety of Air Navigation
FABEC
Functional Airspace Block Europe Central
FAF
Final Approach Fix
FH
Frozen Horizon 
FDPS
Flight Data Processing System
FIR
Flight Information Region
FIXM
Flight Information Exchange Model
FL
Flight Level, unit of altitude (expressed in 100's of feet)
FLAS
Flight Level Allocation Scheme
FMS
Flight Management System
FPL
Flight Plan
FSA
First System Activation Message 
FUM
Flight Update Message
HF
Human Factor
HMI
Human Machine Interface
HR
Human Resources
IAF
Initial Approach Fix
IAS
Indicated Air Speed
IBP
Industry Based Platform
ICAO
International Civil Aviation Organisation
IFPS
Integrated Initial Flight Plan System
IMH
Initial Metering Horizon
IMP
Initial Metering Point
IOP
Interoperability
KPA
Key Performance Area
KPI
Key Performance Indicator
Kts
Knots
LOA
Letter Of Agreement
LVNL
Luchtverkeersleiding Nederland (Air Traffic Control the Netherlands)
LVP
Low Visibility Procedures
MET
Meteorological Information
MONA
ATC Monitoring Aids
MOPS
Method of Operations
MP
Metering Point
MUAC
Maastricht Upper Area Control Centre
NATS
National Air Traffic Services
NM
Nautical Miles
NOP
Network Operations Plan
OCD
Operational Concept Document
ODT
Operational Requirements and Data Processing Team
OLDI
On-Line Data Interchange
OR
Operational Requirement
OSED
Operational Service and Environment Description
PAC
Pre-Activation Message (OLDI)
PBN
Performance Based Navigation
P-RNAV
Precision Area Navigation
RADNET
Radar Data Network
RBT
Reference Business Trajectory
RDA
Runway Delay Allocation
RDPS
Radar Data Processing System
REV
Revision Message
RNP
Required Navigation Performance
R/T
Radio Telephony
RTA
Required Time of Arrival
RTD
Required Time of Departure
RTE
Route
RTS
Real Time Simulation
RWY
Runway
SA
Situation Awareness
SAAM
System for traffic Assignment &Analysis at Macroscopic level
SAF
Safety 
SARA
Speed And Route Advisories
SEC
Security
SEQ
Sequence
SESAR
Single European Sky ATM Research Programme
SID
Standard Instrument Departure
SJU
SESAR Joint Undertaking (Agency of the European Commission)
STA
Scheduled Time of Arrival
STAR
Standard Terminal Arrival Route
STO
Scheduled Time Over
SWIM
System-Wide Information Management 
TBC
To Be Completed
TBD
To Be Decided
TBFM
Time Based Flow Management
TBO
Trajectory Based Operations
TDD
Tactical Delay Distribution
TiBO
Time Based Operations
TLDT
Target Landing Time
TMA
Terminal Control Area
TOBT
Target Off Block Time
TOC
Top Of Climb
TOD
Top of Descent
TOM
Time Over Metering point
TP
Trajectory Prediction or Predictor 
TSAT
Target Start Up Approval Time
TTA
Target Time of Arrival at Runway
TTG
Time To Gain
TTL
Time to Lose
TTO
Target Time Over
TTOT
Target Take-Off Time
UAC
Upper Area Control
UNL
Unlimited
V1, V2… V7
Concept Lifecycle Model Phases V1 to V7
VALP
Validation Plan
VALR
Validation Report
VDL
VHF Datalink
WAN
Wide Area Network
XMAN
Cross Border Arrival Management

