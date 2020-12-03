# Introduction au Wiki fabmob

Le Wiki est basé sur la plateforme MediaWiki, celle qui a été créée pour et fait tourner Wikipedia.

## Principe du Wiki

Le principe d'un wiki, c'est que toutes les pages de contenu peuvent être modifiées par tout le monde, avec une modération *a posteriori*, donc reposant sur la confiance et la possibilité d'annuler facilement les modifications considérées comme mauvaises. 

C'est le contraire de la plupart des autres sites, où des administrateurs valident toutes les modifications *a priori*.

## Où est le code ? 

MediaWiki est une plateforme en PHP, qu'on personnalise en la configurant. 

Notamment avec :

- des extensions, qui ajoutent des fonctionnalités (exemple : ajouter un éditeur de contenu plus sympa) 

- un habillage (*skin*), par exemple pour adapter le menu du site et le mettre tout en haut, et des styles particuliers dans des fichiers CSS pour le contenu des pages

Le code des wiki n'est pas souvent mis sur Github (il n'est donc pas encore ici) ni déployé automatiquement à chaque modification : en général, les développeurs interviennent directement sur le serveur par exemple pour ajouter une extension.

Une raison à cela est que MediaWiki embarque en son coeur l'édition de contenu et la gestion de l'historique. 

Ce contenu peut être à la fois le texte à afficher sur un article par exemple, mais aussi la définition des *templates* de contenu eux-mêmes : par exemple on peut construire une catégorie de page "projet", puis une catégorie "domaine", dans lesquelles on renseignera des informations différentes et qu'on reliera entre-elles.

En attendant d'arriver à un déploiement continu, nous documentons l'état actuel du Wiki ici.

## Ajouter des fonctionnalités

Cela fonctionne avec des *extensions*.

Pour lister les extensions installées chez nous, c'est ici : https://wiki.lafabriquedesmobilites.fr/wiki/Sp%C3%A9cial:Version

On peut alors réfléchir à en ajouter d'autres, ou développer de nouvelles pour combler d'autres besoins.

## Changer l'apparence du Wiki Fabmob

### La structurante principale

Pour l'agencement, par exemple le menu principal, ou encore la page de connection, on utilise des habillages. 

Nous utilisons cet habillage personnalisé FabMob : https://github.com/fabmob/dokostheme. 

Par exemple, [c'est ici](https://github.com/fabmob/dokostheme/blob/master/chameleon-component/FabmobButtonBar.php#L35) qu'on définit le bouton "Créer une ressource" tout en haut du Wiki.

L'objectif est de l'utiliser au minimum et de se resynchroniser avec thème standard [Chameleon](https://www.mediawiki.org/wiki/Skin:Chameleon).

### L'apparence des pages de contenu

Il est défini notamment dans [Common.css](https://wiki.lafabriquedesmobilites.fr/wiki/MediaWiki:Common.css) qu'on peut modifier directement sur le Wiki en cliquant sur "Modifier le Wikicode".

Ensuite, on peut modifier l'affichage des catégories de pages (appelés `Modèles`) en manipulant directement le HTML qui sera affiché à l'utilisateur, par exemple les pages de catégorie "Commun" dans le modèle "Ressources" (oui, il faut le savoir ^^) [ici](https://wiki.lafabriquedesmobilites.fr/wiki/Mod%C3%A8le:Ressource). 

On peut mutualiser des bouts de HTML entre les différentes catégories de page en définissant d'autres plus petits [Modèles](https://www.mediawiki.org/wiki/Help:Templates).

Pour ne pas surcharger le style de Common.css, on peut définir des styles particuliers grâce à l'extension *TemplateStyles*. 

Par exemple, pour la catégorie de contenu "Projet" on peut changer le style [ici](https://wiki.lafabriquedesmobilites.fr/wiki/Mod%C3%A8le:Project/styles.css), il est chargé par ce bout de wikicode dans [Project](https://wiki.lafabriquedesmobilites.fr/wiki/Mod%C3%A8le:Project) mis après `<includeonly>` : `<templatestyles src="Project/styles.css" />`.


