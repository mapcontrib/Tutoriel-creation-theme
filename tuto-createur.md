<!-- TOC depthFrom:1 depthTo:6 withLinks:1 updateOnSave:1 orderedList:0 -->

- [Tuto créateur de thèmes](#tuto-crateur-de-thmes)
	- [Se rendre sur l'instance](#se-rendre-sur-linstance)
	- [Se connecter avec son compte OpenStreetMap](#se-connecter-avec-son-compte-openstreetmap)
	- [Créer un nouveau thème](#crer-un-nouveau-thme)
	- [Configurer le thème](#configurer-le-thme)
		- [Se géolocaliser](#se-golocaliser)
		- [Configuration générale](#configuration-gnrale)
			- [Nom du thème, description et couleurs](#nom-du-thme-description-et-couleurs)
			- [Positionnement et géolocalisation](#positionnement-et-golocalisation)
			- [Géocodeur, Affichage des informations et Statistiques](#gocodeur-affichage-des-informations-et-statistiques)
		- [Fonds de carte](#fonds-de-carte)
	- [Créer une couche de données](#crer-une-couche-de-donnes)
		- [Cas de la requête overpass](#cas-de-la-requte-overpass)
		- [Tester sa requête](#tester-sa-requte)
			- [Le cache !](#le-cache-)
			- [Quelques bonnes pratiques](#quelques-bonnes-pratiques)
		- [Cas du fichier CSV](#cas-du-fichier-csv)
		- [Cas du fichier GeoJSON](#cas-du-fichier-geojson)
		- [Cas du fichier GPX](#cas-du-fichier-gpx)
	- [Configurer ses tags](#configurer-ses-tags)
	- [Définir les types de noeuds, "modèles"](#dfinir-les-types-de-noeuds-modles)
	- [Traduire son thème](#traduire-son-thme)

<!-- /TOC -->

# Tuto créateur de thèmes
À l'instar d'[OpenBeerMap](http://openbeermap.github.io), d'[OsmHydrant](http://osmhydrant.org/) et de [wheelmap](https://wheelmap.org), MapContrib vise à faciliter la contribution à OpenStreetMap, par la création de thèmes en fonction des TOC (Troubles Obsessionnels Cartographiques) propre à chacun.
Ces thèmes se basent sur :
- une requête overpass (technique pour aller interroger une copie synchronisée de la base de donnée OpenStreetMap),
- la définition de "types de noeuds",

Ce tutoriel vise à accompagner la création d'un thème.
Les pré-requis pour pouvoir le faire sont :

- l'envie et/ou le besoin,
- [un compte OpenStreetMap](https://www.openstreetmap.org/user/new),
- connaître les tags (clé / valeur) dans [l'ontologie OpenStreetMap](https://wiki.openstreetmap.org/wiki/FR:Page_principale),
- connaître une requête [OverPass](http://overpass-turbo.eu/),

## Se rendre sur l'instance

- Pour ce tutoriel, l'instance utilisée est https://mapcontrib.xyz.

![Page d'accueil](images/MapContrib_057.png)

## Se connecter avec son compte OpenStreetMap
- Se rendre dans la colonne de paramètres,

![Page d'accueil](images/MapContrib_008.png)

- Se connecter,

![Colonne](images/MapContrib_009.png)

- en utilisant son compte OpenStreetMap,

![Pop-up OpenStreetMap](images/MapContrib_010.png)

- Renseigner ses identifiants OpenStreetMap,

![Page de connexion OpenStreetMap](images/MapContrib_013.png)

- Accepter que MapContrib accède à votre compte OpenStreetMap,

![Autoriser accès MapContrib](images/MapContrib_014.png)

## Créer un nouveau thème

- Se rendre dans la colonne de paramètres,

![Page d'accueil connectée](images/MapContrib_015.png)

![Colonne connectée](images/MapContrib_016.png)

À noter :

- la possibilité de retrouver tous les thèmes que l'on a créé,
- la possibilité de retrouver ses favoris (des thèmes que l'on a créé ou pas, dont on souhaite garder la trace),

![Favoris 1](images/MapContrib_059.png)

![Favoris 1](images/MapContrib_060.png)

![Favoris 1](images/MapContrib_058.png)

## Configurer le thème

Un thème porte un titre, peut s'ouvrir sur un territoire particulier et possède quelques options générales décrites ci-dessous. Toutes ses options sont modifiables par la suite.

### Se géolocaliser

![Nouveau thème](images/MapContrib_023.png)

- le raccourci clavier Ctrl+f fonctionne

![Recherche Gap](images/MapContrib_024.png)

### Configuration

![Configuration](images/MapContrib_017.png)

![Configuration générale](images/MapContrib_018.png)

#### Nom du thème, description et couleurs


![Colonne configuration générale - partie 1](images/MapContrib_019.png)

- Nom du thème / apparaît à la fois dans l'url et en haut du thème
  - si vous changez le titre, même une ancienne url fonctionne car le titre n'est pas pris en compte, seul le code (unique) sert à trouver le thème,
  - pas d'inquiétudes donc vous pouvez changer le nom de votre thème quand vous voulez :)
- Description / permet de décrire le sujet de votre thème. Lorsque ce champ est rempli, un i apparaît à coté du nom du thème et permet d'accéder à la description.

![Colonne configuration générale - partie 1-1](images/MapContrib_061.png)

![Colonne configuration générale - partie 1-2](images/MapContrib_062.png)

![Colonne configuration générale - partie 1-3](images/MapContrib_063.png)

#### Positionnement et géolocalisation

![Colonne configuration générale - partie 2](images/MapContrib_020.png)

- Positionnement / Enregistrer les paramètres actuels / permet de conserver la géolocalisation et le niveau de zoom pour une personne arrivant sur le thème,
- Géolocalisation / va demander l'autorisation de se géolocaliser à toute personne arrivant sur le thème,

#### Géocodeur, Affichage des informations et Statistiques

![Colonne configuration générale - partie 3](images/MapContrib_021.png)

- Géocodeur / permet de définir le géocodeur utilisé lors des recherche (Ctrl+F). Par défaut, Photon est utilisé pour des raisons de fluidité.
- Affichage des informations / les informations des POI peuvent être affichés dans plusieurs types de fenêtres. Par défaut en colonne à droite, il est aussi possible de changer le comportement du thème en affichant :
  - des Infobulles ![infobulle](images/MapContrib_064.png),
  - des Fenêtres modales![Modales](images/MapContrib_065.png),

### Fonds de carte

- ![Fonds de carte - partie 1](images/MapContrib_055.png)

- ![Fonds de carte - partie 2](images/MapContrib_056.png)

	- Définition des fonds de cartes pour les contributeurs. Ces derniers auront la possibilité d'en choisir d'autres mais ceux définis par le créateur du thème sont mis en avant.

## Créer une couche de données

Plusieurs couches de données peuvent être créées. Cependant, quelques précautions avant de créer une dizaine de couches différentes:
- dans les cas des couches "overpass" : **trop de couches simultanées renvoient des erreurs, les serveurs overpass n'appréciant pas d'avoir trop de requêtes provenant d'une même adresse "IP"**,
- dans les cas d'autres types de couches : **trop de données peuvent aussi saturer l'explorateur internet, c'est coté client que se passe les calculs !**

Donc 4 types de données peuvent être ajoutés :
 - des données provenant directement d'OpenStreetMap à travers une requête overpass (c'est le coeur de MapContrib),

Mais aussi pour permettre de faire des comparaisons avec les données OSM :
 - des données dans un fichier csv comportant des titres de colonnes longitude et latitude,
 - par un fichier GeoJSON,
 - par un fichier GPX,

![Création couches - Partie 1](images/MapContrib_025.png)

![Création couches - Partie 2](images/MapContrib_026.png)

![Création couches - Partie 3](images/MapContrib_027.png)



### Nom, Description et Visibilité

![Création couches - Partie 4](images/MapContrib_028.png)

- **Nom** / définit le nom de cette couche, telle que cela apparaît pour les contributeurs,
- **Description** / permet de mieux renseigner le contenu de la couche, supporte également le markdown !
	- ![Création couches - Partie 4](images/MapContrib_067.png)
- **Visibilité** / va permettre au créateur de thème de préparer de nouvelles couches mais de ne pas les montrer aux contributeurs sur le thème,

### Représentation, Marqueur et Contenu des bulles

![Création couches - Partie 4](images/MapContrib_029.png)

#### Représentation

Sous forme de points groupables (par défaut) ou de carte thermique.
- ![Carte thermique](images/MapContrib_068.png)

- Options ![Carte thermique, options](images/MapContrib_069.png)

#### Marqueur
Les marqueurs de chaque couche sont personnalisables :
- au niveau de la couleur et de la forme
	- ![Couleurs et formes marqueurs](images/MapContrib_070.png)

- avec une bibliothèque d'icônes :
	- ![Bibliothèques d'icônes](images/MapContrib_071.png)

- ou un lien vers une image extérieure (assurez vous d'avoir les droits d'utilisation de l'image) :
	- ![Lien icône externe](images/MapContrib_072.png)

#### Contenu des bulles
Les données de la couche, quelque soit la source, peuvent être affichés de manière dynamique dans la "bulle" associée à chaque point.

Pour cela, il est important de définir le contenu des bulles.

Pour appeler une valeur dynamique, on utilisera la clé entre accolade : {clé} renvoie la valeur de manière dynamique.

- ![Contenu de la bulle](images/MapContrib_073.png)
- ![Résultat dynamique](images/MapContrib_074.png)

### Cas de la requête overpass
#### Zoom minimum, Requête OverPass et Cache
![Couche overpass - Partie 1](images/MapContrib_075.png)

- **Zoom minimum** / définit la valeur à laquelle la requête overpass se déclenche,
- **Requête OverPass** / Zone pour l'exécution de la requête
	- le temps de requête maximum (timeout) est limité à 120 secondes,
	- la taille maximale de données rapatriés est limitée à 1 Mo !
- **Le cache**
	- activer le cache présente des avantages et des inconvénients
		- les données se chargent plus rapidement (la requête overpass n'est pas exécuté, les données sont téléchargées depuis leur stockage en cache sur nos serveurs) mais se mettent à jour moins régulièrement (la requête est relancée une fois par jour pour mise à jour),
		- sur un thème dont le cache est activé, une étoile jaune signale l'ajout d'une donnée depuis ce thème (et seulement depuis ce thème),


### Tester sa requête
Selon le zoom minimum défini, la requête peut ne pas se déclencher à l'ouverture du thème. Il faudra alors zoomer pour permettre le déclenchement.

![Tester sa requête overpass - Partie 1](images/MapContrib_051.png)

![Tester sa requête overpass - Partie 1](images/MapContrib_052.png)

![Tester sa requête overpass - Partie 1](images/MapContrib_053.png)

### Cas des autres formats de fichiers pour les couches
**Nom, Description, Visibilité, Représentation (groupable ou thermique), Marqueur et Contenu des bulles** fonctionnent de la même manière. Seule la manière de voir des données diffèrent, par l'import d'un fichier depuis son ordinateur. Ces données ne seront ni modifiables, ni déplaçables et n'ont pas d'interactions avec la base de données OpenStreetMap.
Ces sources de données peuvent servir de comparaison, vérification de complétude par rapport à une autre source, ...

#### CSV
![Fichier CSV - Partie 1](images/MapContrib_005.png)

#### GeoJSON
![Fichier GeoJSON - Partie 1](images/MapContrib_006.png)

#### GPX
![Fichier GPX - Partie 1](images/MapContrib_007.png)

## Configurer ses tags

La configuration des tags va permettre par la suite de les utiliser :
- pour la traduction des types de noeuds ("modèles" / "presets") : voir paragraphe suivant)
- pour l'appel dynamique dans les bulles ("pop-ups") et donc pour la traduction dans les données dynamiques : cela permet ainsi d'avoir une interface sans aucun mot étranger (souvent un frein pour les contributeurs ni geek ni cartographe ni contributeur).

Vous pouvez créer autant de tags que nécessaire, cependant il faut garder le lien avec la requête overpass... Bien "penser" ce que l'on veut voir, améliorer, ajouter avant de se lancer dans la requête, les tags, les modèles, la traduction !

![Définir les tags - Partie 1](images/MapContrib_032.png)

![Définir les tags - Partie 2](images/MapContrib_033.png)

![Définir les tags - Partie 3](images/MapContrib_034.png)

- **Type** / permet de définir différents formats que l'on retrouvera ensuite dans les **Types de noeuds** et différentes présentations !
	- Cases à cocher
![Définir les tags - Cases à cocher](images/MapContrib_076.png)
	- liste déroulante avec traduction
![Définir les tags - Liste déroulante](images/MapContrib_077.png)

![Définir les tags - Partie 4](images/MapContrib_035.png)

![Définir les tags - Partie 5](images/MapContrib_036.png)

![Définir les tags - Partie 6](images/MapContrib_037.png)


## Définir les types de noeuds, "modèles"
Les types de noeuds permettent de définir à la fois :
- les tags pré-remplis qui pourront être utilisés pour compléter, qualifier des données existantes (fusion des tags entre le noeud existant et le type de noeud),
- les tags pré-remplis qui pourront être ajoutés lorsque un noeud est manquant,

![Définir les types de noeuds - Partie 1](images/MapContrib_038.png)

![Définir les types de noeuds - Partie 2](images/MapContrib_039.png)

![Définir les types de noeuds - Partie 3](images/MapContrib_040.png)

![Définir les types de noeuds - Partie 4](images/MapContrib_041.png)

![Définir les types de noeuds - Partie 5](images/MapContrib_042.png)

Cela se traduit donc pour le contributeur en un noeud "pré-rempli" :

![Ajouter un noeud - Partie 1](images/MapContrib_081.png)

![Ajouter un noeud - Partie 2](images/MapContrib_078.png)

![Ajouter un noeud - Partie 3](images/MapContrib_079.png)

![Ajouter un noeud - Partie 3](images/MapContrib_080.png)


## Traduire son thème

Après avoir rempli l'ensemble des informations il est possible de traduire les thèmes pour qu'il soit adapté en fonction de la langue du navigateur.
L'absence de traduction d'une langue entraîne l'utilisation des chaînes de caractères par défaut (donc par défaut remplir les champs comme indiqué ci-dessus, puis traduire seulement les éléments nécessaires / souvent **tags** !).
Si vous avez écrit en français sauf les tags, il n'est pas nécessaire de remplir les éléments de traduction concernant la configuration générale, les couches ou les types de noeuds. En l'absence de traductions, ceux sont les contenus écrit initiaux qui sont affichés.
Ces traductions seront nécessaires pour que cela fonctionne dans d'autres langues.

![Traduction - Partie 1](images/MapContrib_043.png)

![Traduction - Partie 2](images/MapContrib_044.png)

![Traduction - Partie 3](images/MapContrib_045.png)

![Traduction - Partie 4](images/MapContrib_046.png)

![Traduction - Partie 5](images/MapContrib_047.png)

![Traduction - Partie 5](images/MapContrib_049.png)
