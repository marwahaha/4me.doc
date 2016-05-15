TOC]
#Récupération des données de l'AMAN
##Connexion AMAN
##Creation d'une base de données des vols XMAN
##Données nécessaires à l'IHM 4Me
#Récupération des données radar des avions
##Positions radar
##Données ModS

#Corrélation liste avion/positions radar
#Affichage des vols sur la liste XMAN
#Statut vol XMAN 
Au cours du vol un avion a destination d’un aéroport XMAN rencontrera plusieurs statut:
Les zones décrites ci dessous seront utilisées pour la gestion des advisory.

##Eligibility Area : 
A 550Nm de LHR le vol entre dans le volume « Eligibility Horizon », à partir de ce moment l’AMAN de Londres commence à calculer la sequence de tous les vols à l’intérieur de l’horizon et calcul une TTO au COP. La TTO au COP et le délai associé est transmise dans le fichier XML. Les vols ont un délai affecté mais ce délai n’est pas assez stable pour impliquer un advisory. Aucun advisory ne peut être affiché tant que le vol n’est pas entré dans le cercle des 350NM dit « Active Horizon ».

##Display Area : 
Lorsque les vols rentrent dans la « Display Area » ils sont affichés dans les listes de vol XMAN. Les vols en dehors de cette zone ne sont jamais affichés dans l’IHM. Sur l’IHM chef de salle et ftp 

##Action Area : 
A 350Nm à l’entrée de l’ « Active Horizon Area », les vols ayant un délais reims positif doivent être réduits. Dans l’active horizon area, les advisory sont poussés sur les secteurs. Une seule action area est définie par UAC et par flux XMAN.

##Frozen Area :
 Dans ce volume les advisory ne peuvent plus être modifié quel que soit la variation du délais.    Dans le cas de Londres, l’AMAN utilise des données ETFMS jusqu’a la couverture radar du NATS ou il commence à utiliser des données radar. Le changement de type de données créé une marche de délais et une instabilité. Pour éviter de répercuter ce phénomène technique sur les positions de contrôle, le délais est figé avant que l’AMAN puisse disposer des données radar.

# Definition des aires et volumes secteurs :
Les volumes et aires définis ci dessus sont utilisés pour les fonctions de filtrage.

##Aires d’intérêt secteur :
 Le volume d’intérêt du secteur est le volume dans lequel les avions seront affichés.

Ces aires d’intérêt sont définies par bloc secteur et par terrain XMAN.

Elle permettant le filtrage géographique par bloc. Le filtrage sur l’aire secteur n’a aucun intérêt cette fonction n’est donc pas développée.

Le filtrage « géographique » se fait sur l’aire intérêt secteur.
En cas de regroupement l’aire d’intérêt des blocs regroupés et la somme des aires d’intérêt des secteurs regroupés.  

##Volume intérêt secteur :
 Le volume intérêt secteur est défini par l’aire d’intérêt secteur et les limites verticales du secteur.
 
#Mecanisme amortisseur de délais
##Principe de stabilité
##
