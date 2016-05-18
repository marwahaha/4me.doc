[TOC]
#4Me 
 L'objectif de "4Me" est l'exploitation de différents services dans une même IHM dite *multiservices*.
 Les informations sont traitées par l'IHM "4Me" de façon à distribuer les informations uniquement sur les secteurs qui en ont l'usage et au moment opportun.
 
 Chacun des services est adapté aux différents utilisateurs.
 4 types d'utilisateurs sont définis :
 
##SPVR OPS
Le client **SPVR OPS** est le client du Chef de Salle situé à droite de l'écran ARTEMIS.
##SPVR Tech
Le client de **SPVR Tech** est le client du superviseur technique, sa version est en cours de développement et son utilisation sera détaillée dans une prochaine version du manuel utilisateur.
 
##FMP
  Le client **SPVR OPS** est le client de l'ACDS ou de l'Extended ATC Planner, ses fonctionnalités sont limitées dans la première version de 4Me, mais un développement futur permettra de spécialiser l'IHM FMP, pour répondre aux besoins d'échange d'informations entre la FMP et les CWP.
##CWP
  Les clients **CWP** sont les clients "positions de contrôle". 
 Ils sont disposés en haut de l'écran radar du controleur organique et sont pilotés par une souris dédiée. Il n'y a pas de clavier physique sur les positions de controle pour le pilotage de 4Me.
  
  Chacune des positions de contrôle ouvertes filtre les services et les données en fonction des besoins opérationnels.
  
 Les droits des utilisateurs sont différents pour chaque service et seront décrits dans le manuel utilisateur ci dessous.
 
#4Me Core
##Présentation générale
  
 4Me Core correspond à la partie centrale de l'IHM, elle est constituée de deux bandeaux : le bandeau supérieur et le bandeau latéral.
  4Me Core est définie pour afficher les notifications, forcer le rafraîchissement de la page, et accéder aux différents services 4Me.
  La partie 4Me Core est commune pour tous les utilisateurs.
##Fonctionnalités
###Bandeau Supérieur
 ![Imgur](http://i.imgur.com/cXiRM2u.png)
 
 
Le bandeau supérieur comporte deux parties :
 
- Information Corner, à gauche
- Status Corner, à droite
 
####Information Corner
![Imgur](http://i.imgur.com/KMYweSFm.png)
  
Le coin supérieur gauche *"Information Corner"* contient les informations relatives au statut du client 4Me(PXX) Sector: 
  
- 4Me 
- Numero de la position
- Secteur ouvert (le cas échéant) 
- Date et Heure
  
Afin de bénéficier de la spécialisation des services, il est recommandé de vérifier lors de chaque relève et de chaque dégroupement que l'**Information corner** est cohérent avec le couple secteur/position.
  
####Status Corner
Le coin supérieur droit *"Status Corner"* contient des boutons d'action de 4Me Core
 
#####Bouton Refresh :
En cas de comportement anormal de 4Me le bouton **Refresh** permet de rafraîchir la page en cours. 
  
La page est rafraîchie automatiquement en permanence à chaque nouvelle action, ou chaque mise à jour des données.
Si un comportement anormal de 4Me est détecté le premier réflexe de l'utilisateur est de rafraichir la page.Un clic sur le bouton **Refresh** permet dans la plupart des cas de résoudre le dysfonctionnement. En cas d’échec de la procédure, il est nécessaire d'en avertir le chef de salle.
  
#####Bouton d'information de statut de service :
  
Ce bouton cliquable indique l'état de fonctionnement de 4Me.
Un clic sur le bouton d'information de service permet de connaitre plus en detail le type de dysfonctionnement détecté.
  
![Service Status Button](http://i.imgur.com/Zm9oMOWs.png) Fonctionnement normal

RAJOUTER LE BOUTON Fonctionnement Dégradé
  
![Alarm Service Status](http://i.imgur.com/SWGfsrls.png) Dysfonctionnement détecté.
  
L'état des  services 4 Me (4Me-Core, XMAN, ARCID, MAPPING) est affiché par ce bouton.
  
Le bouton de dysfonctionnement s'affiche dès qu'un des services rencontre un dysfonctionnement. 
Un clic sur ce bouton ouvre une fenêtre détaillant les différents états de service.
  
- **CWP :** Sur les positions de contrôle, le principe est d'éviter toute recherche de panne. Un seul niveau d'information est affiché pour connaitre le ou les services 4Me affectés par le dysfonctionnement.
Dans le cas où un seul service serait affecté, les autres peuvent continuer à être utilisés.
Si le Core connaît un dysfonctionnement, 4Me n'est plus utilisable. Si un refresh ne solutionne pas le problème, il est nécessaire d'en avertir le chef de salle qui prendra les dispositions nécessaires.
 
![Imgur](http://i.imgur.com/ZVopWuum.png)
 
 
- **SPVR OPS**: Sur la position du Chef de salle deux niveaux d'information sont disponibles.
  
![Imgur](http://i.imgur.com/bCTGgdbm.png)
  
Le premier niveau est identique à celui décrit pour les CWP, le deuxième niveau, plus détaillé, décrit les pannes possibles.
  
Ce niveau de détail permet une discussion plus facile avec le superviseur technique et améliore le niveau de compréhension de l'état du système par le chef de salle.
  
- **SPVR TECH**: L'IHM du superviseur technique étant en cours de développement son fonctionnement sera décrit dans les prochaines versions du *manuel utilisateur 4Me*
![Imgur](http://i.imgur.com/hXRDKZ0.png)

 
Les pannes possibles et supervisées sont les suivantes : 
 
- NA : Non Available
- Monitored : Supervisée par 4Me

|Service   |  4meCore | MAPPING  | XMAN  | ARCID  |
|---|---|---|---|---|
| Perte Connexion  | NA  | NA  | Monitored AMAN connexion | Monitored B2B NM connexion  |
| Panne Serveur  | Monitored  |  Monitored | Monitored  | Monitored   |
| Panne Acquisition ELVIRA  | NA  | NA  | Monitored  | NA   |
 
 
Exemple de dysfonctionnement XMAN :
 
![Imgur](http://i.imgur.com/q4LfL0um.png)
  
###Bandeau Latéral
La liste des services disponibles sur le client 4Me (XMAN-ARCID-MAPPING) est affichée sur le bandeau latéral.  
  
![Imgur](http://i.imgur.com/ImQ6nlhm.png)
  
Un clic sur le service permet le basculement sur la page du service associé.
  
Le service grisé correspond au service en fonction.
  
####Notifications
Les notifications ne sont utilisées dans la première version que pour le service XMAN. 

Une pastille orange associée à un chiffre indique le nombre d'actions XMAN à réaliser.
 
Ce nombre d'action XMAN à réaliser correspond au nombre d'avions à réduire qui sont à l’intérieur du volume d'intérêt du secteur.
  
![Imgur](http://i.imgur.com/qc0O0KVm.png)
  
Lorsque toutes les actions XMAN ont été réalisées, la notification disparaît du bandeau latéral.
# MAPPING
## Présentation générale
Le service MAPPING permet de dégrouper ou regrouper les IHM 4Me.
Dans l'optique de spécialiser les services et les affichages sur les écrans 4Me, il est indispensable d'assurer la cohérence de 4Me avec l'état réel de dégroupement des secteurs de contrôle.
  
Dès que la correspondance secteur/position/client 4Me est assurée, les options de spécialisation de l'IHM deviennent possibles.
  
L'objectif de 4Me est de pouvoir présenter seulement les informations adaptées au secteur de contrôle, et d'éviter l'affichage d'informations inutiles sur la position de contrôle.
  
Ainsi, le mapping de la salle de contrôle est un principe fondamental pour l'utilisation de 4Me.
  
Pour réaliser la cohérence secteur ouvert/client 4Me, le service MAPPING propose d'associer à chaque position un secteur, tout comme le fait X-SALGOS ou bien ARTEMIS.
  
![Imgur](http://i.imgur.com/BLndae9.png)
 

## Fonctionnalités
###Configuration de la salle de contrôle
####Modification de la configuration de la salle de contrôle 
La salle de contrôle est représentée graphiquement sur le service MAPPING, seuls les zones 1-2-3 de la salle de contrôle sont affichées.
Le positionnement graphique correspond à la vue des secteurs physiques lorsque le chef de salle regarde l'écran 4Me.
  
Le regroupement/dégroupement d'un ou plusieurs secteurs se fait par la sélection de la position choisie dans une logique d'addition.
La logique d'addition repose sur le principe d'ajout de secteurs nominaux. 
Pour créer un regroupement, on sélectionne donc la position recevante et on y ajoute le ou les secteurs que l'on souhaite regrouper.
Pour dégrouper un secteur, on sélectionne la position sur laquelle on souhaite ouvrir un nouveau secteur et on y ajoute le ou les secteurs que l'on souhaite dégrouper.
  
Un clic sur la position permet l'ouverture d'une boite d'action.
![Imgur](http://i.imgur.com/3zE3ugU.png)

Afin de faciliter la sélection multiple des secteurs, un algorithme de suggestion de regroupement/dégroupement permet de proposer des raccourcis correspondant aux ouvertures usuelles.
  
Les boutons en bleu turquoise sont des boutons de suggestion.
  
![Imgur](http://i.imgur.com/O1Q0Yid.png)
 
Cette proposition "*intelligente*" des choix de regroupement/dégroupement est basée sur la zône de la position choisie, sur la position physique et sur la configuration actuelle de la salle de contrôle.
  
 Ces suggestions dynamiques évoluent en fonction de la configuration déjà ouverte et de la CWP choisie.
  
Si le regroupement/dégroupement prévu est disponible dans les suggestions, un clic permet de le valider.
Il n'est pas nécessaire de confirmer le choix, la sélection de la suggestion vaut confirmation.
  
En cas d'erreur, le retour arrière se fait comme une nouvelle action de regroupement/dégroupement.
  
Dans les rares cas ou la suggestion n'apparaîtrait pas, la boite de regroupement/dégroupement permet de "créer" la configuration souhaitée. La logique retenue dans le service MAPPING est l'ajout de secteurs. Une fois la compilation des secteurs nominaux effectuée, une confirmation est nécessaire afin de valider le choix.
  
![RGRBox](http://i.imgur.com/cYkpJpQ.png)
  
Le bouton **Cancel** permet de revenir à la configuration actuelle. 
Le bouton **Confirm** permet de confirmer la configuration choisie.
 
![Imgur](http://i.imgur.com/H400P5z.png)
  
Seul le client **SPVR OPS**  du chef de salle peut modifier la configuration de la salle de contrôle.
  
Dans l'*Information corner* la configuration choisie s'affiche dynamiquement avec le signe **P31=>KHYR** qui signifie qu'après validation la Position 31 sera associée au secteur KHYR.
  
![Imgur](http://i.imgur.com/YaNZL00.png)
####Algorithme de suggestion de regroupement/dégroupement
  
L'algorithme de suggestion propose les solutions d'ouverture ou de regroupement secteur les plus adaptées aux besoins opérationnels.
  
Le principe repose sur une analyse instantanée de la configuration des secteurs ouverts et sur la position sélectionnée par le chef de salle pour effectuer le regroupement/dégroupement.
  
L'algorithme proposera donc en priorité des regroupements/dégroupements URME dans la zone 2 et des regroupements/dégroupements URMN dans la zone 3

###Position indisponible
 ![CWP Enabled](http://i.imgur.com/spoGPxb.png)
  
 Le Mapping 4Me permet de rendre indisponible un client 4Me.
  
Dès qu'une CWP est déclarée indisponible, 4Me doit aussi être rendu indisponible afin d'assurer la cohérence de la configuration de salle avec les systèmes.
Un clic sur la position suivi d'un glissement du toggle **CWP Enabled** permet de rendre indisponible la position.
De même pour rendre disponible une position indisponible, un glissement de toggle **CWP Enabled** rend la position à nouveau disponible.
  
![Imgur](http://i.imgur.com/GET6qkqm.png)
  
![Imgur](http://i.imgur.com/uWwnizbm.png)
  
Après le clic sur le toggle, une confirmation de l'action par le bouton **Confirm** est nécessaire.
  
![Imgur](http://i.imgur.com/H400P5z.png)
Lorsque la position a été déclarée indisponible elle apparaît en gris.
  
![Disabled CWP](http://i.imgur.com/lcWb7Hgm.png)
 
###Affichage instantané du nombre de secteurs ouverts
La somme des secteurs ouverts est affichée dans la partie centrale de l'IHM MAPPING. 
 
Ce nombre équivaut à la somme instantanée des secteurs ouverts.
  
![TotalOpenedSectors](http://i.imgur.com/vzEy8wD.png)
  
###RGR : affichage de la configuration de la salle de contrôle sur les CWP
L'affichage de la configuration ouverte est disponible sur toutes les CWP par un clic sur le service **MAPPING** dans le bandeau latéral.
  
![Imgur](http://i.imgur.com/thQKzFR.png)
  
L'information de la configuration de la salle de contrôle est disponible en permanence sur les CWP. 
  
Les clients CWP ne disposent d'aucun droit de modification de la configuration de la salle.
  
Attention : *Cette information à jour ne doit pas être utilisée à des fins de coordination.*
  
#XMAN
##Présentation générale
L’IHM **XMAN-4Me** présente une liste de vols sur les clients **CWP** des positions de contrôle.
 
![XMAN](http://i.imgur.com/nbVJv6W.png)
 
Elle affiche la liste des vols à destination des terrains XMAN qui sont dans l'aire d’intérêt du secteur associé. 
 
Ces vols sont classés selon l’heure estimée de passage à ABNUR telle que prévue par l’ETFMS. Les vols rentrent par le bas et sortent par le haut de la liste. A l'exception des cas de dépassement, elle correspond donc au classement du tableau de strips de chacun des secteurs traversés.
 
Un paramétrage par secteur permet d'effacer les vols qui ne sont plus en compte, à la sortie du secteur, par le haut de la liste. 
 
### Bloc d’informations
 De façon générale, l’ensemble des informations renseignées par les contrôleurs sur l’IHM XMAN est partagé entre les différents secteurs.
 
Cela permet à l’ensemble des acteurs de connaître les actions réalisées et l’instant de leur réalisation. Cette information est complétée par la colonne ci-contre qui indique le secteur qui les a appliquées.
  
La fonctionnalité de « Mapping » permet de connaître le secteur qui a effectivement réalisé la réduction XMAN.
  
Lorsque le vol est entré dans le volume d’affichage mais pas encore entré dans l’aire d’activité XMAN le délai total est affiché mais l’advisory ne se déclenchera qu’à l’entrée dans l’aire d’activité XMAN.	
En dehors des plages d’activité XMAN même si le délai total est supérieur à 7mn aucun advisory ne sera présenté sur les positions 4Me.
  
Il s’agit des 5 premières colonnes de l’IHM XMAN :
  
- **ARCID - ADES** : Indicatif de l'avion en L1 et Aéroport de destination en L2
- **Delay** : Total Delay, délai total du vol calculé par l'AMAN
- **FL** : Actual Flight Level (Mode C) fourni par le serveur ELVIRA
- **COP / TTO** : Point de Coordination Reims (COP) / Heure calculée comme objectif de survol du COP par l’AMAN (TTO)
 
![Imgur](http://i.imgur.com/fJiD1urm.png)
 
Il est important de rappeler ici que lorsque le vol entre dans les 350NM de distance à la piste, les valeurs TTO@ABNUR et Reims Delay continuent d’évoluer en fonction des données de l’AMAN de Londres. Elles sont totalement dynamiques.
 
Le codage couleur pour le délai total est le suivant
 
- **Vert** : délai ≤ 7 
 ![Green](http://i.imgur.com/P6YBt8Zm.png)
 
- **Jaune** : 5 ≤ délai ≤7 
 ![Imgur](http://i.imgur.com/tDPd3Trl.png)
 
- **Rouge** : 7 ≤ délai
 ![Imgur](http://i.imgur.com/5k4fAJrl.png)
 
Le niveau de vol actuel est désormais disponible grâce à l’introduction des données radar ELVIRA. 
### Bloc des instructions de contrôle
Les boutons cliquables du pavé numérique représentent des centièmes de Mach (x dans 0.0x). 
S’il n’y a pas de délai Reims, l’ensemble de la ligne de boutons est en gris (neutre),
 
![Imgur](http://i.imgur.com/UNGYR8Ym.png)
  
Lorsqu’un délai Reims est alloué, l’IHM XMAN propose une réduction de vitesse et le bouton associé devient orange  (à faire). 
Les autres boutons deviennent blancs et sont cliquables.
Le fond de l'étiquette passe en surveillance bleue pour souligner l'étiquette sur laquelle il est nécessaire d'agir.

![Imgur](http://i.imgur.com/gR8lxYtl.png)
 
Si le contrôleur applique la réduction de vitesse proposée, il renseigne l’IHM XMAN en cliquant sur le bouton et celui-ci devient vert (réalisé). Dans ce cas les autres boutons redeviennent gris.
![Imgur](http://i.imgur.com/Z0MWy31l.png)
 
 
S’il choisit d’appliquer une autre vitesse, il renseigne l’IHM XMAN, le bouton correspondant à la vitesse choisie devient vert tandis que le bouton correspondant à la vitesse proposée reste jaune.
Le fond de l'étiquette reste en surveillance bleu pour souligner qu'il est toujours nécessaire d'agir une fois la situation ATC résolue.
![Imgur](http://i.imgur.com/T1oI4ozl.png)
  
Si la vitesse appliquée est différente de celle proposée par l’IHM XMAN suite à un refus équipage, le système est renseigné par le bouton avion qui passe au vert lorsque sélectionné.
![Imgur](http://i.imgur.com/P7ygXiF.png)
  
En cas d’erreur de saisie, le bouton UNDO permet de remettre les boutons à l’état immédiatement précédent de l’IHM XMAN. 
![Undo](http://i.imgur.com/K3PjgXns.png)
 
 
##Fonctionnalités
###Notifications
La notification XMAN affiche le nombre d'actions XMAN à réaliser par secteur.
 
![Imgur](http://i.imgur.com/qc0O0KVm.png)
 
Un clic sur la pastille permet le basculement sur la page XMAN
###Hightlight Pending Action
Une fonction de surbrillance des actions à faire permet de sur-visualiser les vols 
La fonction « *Highlight Pending Action*» est toujours activée pour les vols pour lesquels il reste une information de réduction de vitesse à transmettre à l'équipage. Cette fonction met en surbrillance le fond de l’étiquette du vol ou une action XMAN est demandée et n’est pas encore réalisée. 

Le fond de l'étiquette change en fonction du statut de l'action.
  
Le fond des étiquettes des vols est :

- **Gris** si aucune action XMAN n'est demandée
- **Gris** si l'action XMAN demandée a été réalisée par le contrôleur
   
  ![Imgur](http://i.imgur.com/Z0MWy31l.png)
   
- **Bleu** si une action XMAN est demandée
- **Bleu** si une réduction XMAN différente de l'advisory a été donnée par le contrôleur.
  
![Imgur](http://i.imgur.com/T1oI4ozl.png)
   
### Filtrage
En mode nominal le filtrage **CWP** par défaut est le suivant 

- Filtrage vertical : toutes couches
- Filtrage géographique : géographique uniquement.

Le filtrage **CDS** est le suivant :

- Filtrage vertical : toutes couches
- Filtrage géographique : visualisation totale
 
  
|Filtrage|  CWP | FMP  | SPVR OPS | SPVR TECH  |
|---|---|---|---|---|
| Nominal  | Geo Filter  | All Flights | All Flights| All Flights |
| Optionel  | Geo + Vertical 
| | All Flights |  None | None  | None   |
 
### Options de filtrage :
Le bandeau supérieur XMAN contient 3 boutons de filtrage :

- All Flights
- Geo Filter
- Geo + Vertical
 
![Imgur](http://i.imgur.com/CWBBVNR.png)
#### Geo Filter : Filtrage Géographique 
  
![Imgur](http://i.imgur.com/hX1hgQzm.png)
Le filtrage « géographique » se fait sur l’aire d'intérêt du secteur. En cas de regroupement, l’aire d’intérêt des blocs regroupés est la somme des aires d’intérêt des secteurs regroupés.  
  
L’aire d’intérêt du secteur est l’aire dans lequel les avions seront affichés. Ces aires d’intérêt sont définies par bloc secteur et par terrain XMAN.
  
Ce filtrage est sélectionné par défaut sur les positions de contrôle **CWP**.
#### Geo+Vertical : Filtrage Vertical
![Imgur](http://i.imgur.com/jITgU09m.png)
  
Le filtrage « vertical » se fait sur le volume d'intérêt du secteur ouvert. Grace à la fonction « mapping », chaque écran 4Me est associé à un secteur, chaque secteur est associé à son volume d’intérêt correspondant à « l’aire d’intérêt secteur » et aux limites verticales du secteur. En cas de regroupement le volume d’intérêt des blocs regroupés est la somme des volumes d’intérêt des secteurs regroupés.  
  
Le filtrage sur le volume d’intérêt secteur permet l’affichage d’une liste d’avions XMAN épurée à son minimum et ne présentant que les avions qui entreront dans le secteur associé.
###Filtrage All Flights
![Imgur](http://i.imgur.com/nw3tsUFm.png)
 
Le filtrage All Flights affiche tous les vols à destination de EGLL qui sont à l'intérieur de la *"Display Area"*
Ce filtrage est sélectionné par défaut sur les positions chef de salle **SPVR OPS** et ACDS **FMP**.
#### Filtrage par ADES : 
![Imgur](http://i.imgur.com/gg7cJRq.png)
 
Le passage de la souris sur l’aéroport de destination *« mouse over »* en colonne 1 de la liste XMAN filtre tous les avions à destination de cet aéroport. Cette fonction a une utilité limitée dans le cadre actuel où seulement London Heathrow est soumis à restriction XMAN mais elle prépare l’avenir et en particulier l’intégration de Zurich dans le projet XMAN, prévue au premier trimestre 2017.
  
![Imgur](http://i.imgur.com/EODOBGVs.png)
#### Filtrage par COP : 
![Imgur](http://i.imgur.com/9yqERSn.png)
 
 Le passage de la souris sur le point de coordination COP « mouse over » en colonne 4 de la liste XMAN filtre tous les avions qui convergent vers ce COP. 
 
![Imgur](http://i.imgur.com/M4CO9zFs.png)
###Filtrage par FL
Le passage de la souris sur le FL *« mouse over »* en colonne 3 de la liste XMAN filtre tous les avions au même FL. 
![Imgur](http://i.imgur.com/RZZIvyM.png)
Le niveau sélectionné s'affiche en bleu et les vols non concernés sont grisés.
![Imgur](http://i.imgur.com/JQjwYUCm.png)
 
## XMAN Fonctionnalités SPVR OPS
L’IHM SPVR OPS est légèrement différente des IHM sur les positions de contrôle. 
Elle partage les mêmes données mais supporte des fonctionnalités de supervision opérationnelle supplémentaires
Aucun filtre géographique ou vertical n’est disponible.
Les filtres par COP, par niveau et par destination restent eux disponibles sur l’IHM SPVR OPS.
### XMAN Off
Le bouton « XMAN Off » permet l’affichage sur toutes les IHM d’un bandeau indiquant qu’il ne faut pas appliquer de réduction de vitesse. 
![Imgur](http://i.imgur.com/svMhkgjm.png) 
  
![Imgur](http://i.imgur.com/ReMyM2jm.png)
Les advisories ne sont plus affichés sur les CWP.
  
Un bandeau affichant la mention **« XMAN EGLL has been turned off by the supervisor »** s’affiche sur toutes les positions de contrôle.
  
Les réductions de vitesse déjà effectuées restent sur l’IHM à des fins de propagation de l’information vers les secteurs suivants mais elle ne peuvent plus être modifiées.
  
![Imgur](http://i.imgur.com/YEBTrEd.png)
### MCS Minimum Clean Speed
En situation inhabituelle, LACC peut demander les vols en « Minimum Clean Speed », après coordination avec le CDS, le bouton MCS  situé en haut de l’IHM est activé. 
 
Seul le chef de salle peut activer la procédure MCS sur l'IHM 4Me.
 
![Imgur](http://i.imgur.com/b8chqsIm.png)
  
![Imgur](http://i.imgur.com/eI01txxm.png)
  
L’IHM propose alors systématiquement **MCS** comme vitesse à appliquer sur les clients **CWP**.
Un clic sur le bouton **MCS** permet de renseigner 4Me une fois que l’instruction est transmise aux équipages, ainsi les secteurs suivants auront connaissance de la contrainte de vitesse appliquée à l'appareil.
  
![Imgur](http://i.imgur.com/rTKocRw.png)
  
La logique de couleur est la même que pour XMAN
 
- Orange : **Action à faire**
- Vert : **Action réalisée**
  
Lorsque la procédure **MCS** est activée, plus aucun advisory XMAN n'est affiché sur les **CWP**.  Seuls les **MCS** doivent être transmises aux équipages.
  
![Imgur](http://i.imgur.com/DNw0CKd.png)
  
#e4DP : ETFMS 4D Profile
##Présentation Générale
Le service e4DP permet l'accès au profil 4D ETFMS, c'est à dire au plan de vol accepté par l'ETFMS.
Un clic sur le service e4DP permet d'ouvrir la page e4DP.
Un premier volet de recherche permet l'accès au profil 4D ETFMS du vol.
##Fonctionnalités
###Champ recherche
![Imgur](http://i.imgur.com/We2Kcwcm.png)
  
4Me ne dispose pas de clavier physique sur la position.
Pour accéder au champ recherche, un clic sur *loupe* ou dans le champ *Search Callsign* ouvre le clavier virtuel suivant.
![Imgur](http://i.imgur.com/qdkNbkt.png)
  
###Auto Completion
![Imgur](http://i.imgur.com/WIEuyDbm.png)
Afin de faciliter la saisie du callsign un algorithme d'autocomplétion a été développé.
Toutes les 30 secondes, 4Me e4DP fait une requète auprès de NM en chargeant toute la liste des avions dans le *traffic volume* **RMS**.
4Me e4DP connaît donc tous les vols à l'interieur du traffic volume RMS. Dès la saisie du premier caractère, e4DP affiche la liste des vols comportant ce caractère. Un clic de sélection sur le vol recherché permet d'ouvrir le profil 4D ETFMS.
  
Néanmoins il se peut que le vol recherché soit absent du traffic volume RMS. Dans ce cas, une saisie des 8 caractères maximum standard OACI sera nécessaire pour accéder au plan de vol.
###Result
Dans le cas où plusieurs plans de vol correspondant au même ARCID existent dans l'ETFMS, ces différents plans s'affichent dans l'onglet **Results**.
Les indications ADES-ADEP permettent le choix du profil ETFMS recherché.
###History
L'onglet **History** garde en mémoire les dernières recherches effectuées à l'échelle de toutes les positions 4Me de Reims. 
Dès qu'un callsign a été saisi une fois sur un client 4Me, un clic de sélection suffit pour accéder au plan de vol de l'avion concerné.
  
###Point profile Presentation
Le profil 4D e4DP est affiché sur forme de table :
  
|Estimate| Point| FL |Trend|
|---|---|---|---|
|Heure estimée sur le waypoint selon le profil CTFM| BALISE|Niveau prévu à la balise|Tendance évolutive|
  
Un pavé d'information générale rassemble les données spécifiques du vol :
  
- ARCID : Identificatif de l'avion
- ADEP -> ADES
- EOBT DATE and HOUR
- Delay : Total NM Delay 
- Last Updated : dernière pise à jour du plan de vol.
 
 ![Imgur](http://i.imgur.com/DjMl4Rom.png)
 
 Description des champs
  
 |Estimate| Point| FL |Trend|
 |---|---|---|---|
 |Heure estimée sur le waypoint selon le profil CTFM| BALISE|Niveau prévu à la balise|Tendance évolutive|
 ![Imgur](http://i.imgur.com/mpaUztT.png)
####Force Refresh

![Imgur](http://i.imgur.com/aefwkHxm.png)

Pour rafraichir le plan de vol un clic sur le bouton ci dessous, force une nouvelle requète du plan de vol auprès du NM.

