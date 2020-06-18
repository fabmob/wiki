# Introduction au Wiki fabmob

Le Wiki tourne sur la plateforme MediaWiki, celle qui fait tourner Wikipedia.

## Principe du Wiki

Le principe d'un wiki, c'est que toutes les pages de contenu peuvent être modifiées par tout le monde, avec une modération *a posteriori*, donc reposant sur la confiance et la possibilité d'annuler facilement les modifications considérées comme mauvaises. 

C'est le contraire de la plupart des autres sites, où des administrateurs valident toutes les modifications *a priori*.

## Où est le code ? 

MediaWiki est une plateforme en PHP, qu'on personnalise en la configurant. 

Notamment avec :

- des extensions, qui ajoutent des fonctionnalités (exemple : ajouter un éditeur de contenu plus sympa) 

- un habillage (*skin*), par exemple pour adapter le menu du site et le mettre tout en haut.

Le code des wiki n'est pas souvent mis sur Github (il n'est donc pas encore ici) ni déployé automatiquement à chaque modification : en général, les développeurs interviennent directement sur le serveur par exemple pour ajouter une extension.

En attendant d'arriver à un déploiement continu, nous documentons l'installation ici.

## Ajouter des fonctionnalités

Cela fonctionne avec des *extensions*.

Pour lister les extensions installées chez nous, c'est ici : https://wiki.lafabriquedesmobilites.fr/wiki/Sp%C3%A9cial:Version

On peut alors réfléchir à en ajouter d'autres, ou développer de nouvelles pour combler d'autres besoins.

## Changer l'apparence du Wiki Fabmob

Nous utilisons cet habillage personnalisé FabMob : https://github.com/fabmob/dokostheme. 

Par exemple, [c'est ici](https://github.com/fabmob/dokostheme/blob/master/chameleon-component/FabmobButtonBar.php#L35) qu'on définit le bouton "Créer une ressource" tout en haut du Wiki.

L'objectif est de l'utiliser au minimum et de se resynchroniser avec thème standard [Chameleon](https://www.mediawiki.org/wiki/Skin:Chameleon).



