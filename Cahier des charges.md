Cahier des charges
===================


----------


Introduction
-------------

Ce document a pour but de présenter le projet, ses objectifs et ses contraintes, de donner une description précise de ses fonctionnalités ainsi que de son architecture et enfin de son déroulement.

Le choix du sujet étant libre, il n'y a aucune contrainte technique imposée. Cependant, ce projet utilise [discord](https://discordapp.com) et si ce service venait à être indisponible, il serait alors impossible de mener à bien le projet.

### Concept

Ce projet a pour but de créer un jeu massivement multijoueur destinés aux utilisateurs de Discord, une plateforme de communication. Il s'agit de mettre en place une architecture permettant à des centaines voir milliers d'utilisateurs de jouer en même temps via l'interface de discord, de rendre possible aux utilisateurs qui le désire d'héberger leur propre client afin de permettre la customisation et de réduire nos coûts d'hébergement et enfin, d'exposer une API permettant d'obtenir des données sur le jeu.


Technologies utilisées
-----------------------

### [Discord](https://discordapp.com)

Discord est une application de communication déstinée principalement aux joueurs, mais qui convient parfaitement aussi à des communautés ou encore à quiconque désirant pouvoir communiquer textuellement ou vocalement et tout cela gratuitement.
Son interface fluide, ses fonctionnalités et sa gratuité le prédestine à être utilisé par un grand nombre d'utilisateurs et développer une application sur cette plateforme permet ainsi de l'exposer à ceux-ci.

Discord propose à chaque utilisateur de pouvoir créer son propre serveur de communication hébergé sur leurs serveurs. Une fois crée, l'utilisateur peut alors créer différents salons de discussion texte ou vocal et inviter des utilisateurs à le rejoindre via des codes d'invitation.

Nous utiliserons ces fonctionnalités dans le cadre de ce projet notamment pour l'interaction entre les utilisateurs et le jeu.

### [Node.js](https://nodejs.org)

Node.js est un environnement d'exécution pour javascript construit sur [V8](https://developers.google.com/v8/). Son atout principal est qu'il est entièrement non bloquant ce qui lui permet de supporter un grand nombre de requêtes concurrentes.
Node.js est installé avec son gestionnaire de package, [npm](https://www.npmjs.com/), qui est d'après eux le plus large ecosystème de bibliothèques open source au monde.
Node permet de développer itérativement et ainsi de prototyper rapidement des fonctionnalités pour par la suite les rendre plus robustes et complètes.


### [Heroku](https://www.heroku.com/)

Heroku est une plateforme de déploiement qui va nous permettre d'héberger nos divers applications en ligne afin de les rendre accessibles aux utilisateurs du jeu sur discord mais aussi aux contributeurs du client.
Il est possible d'heberger des applications gratuitement avec des contraintes qui nous satisferont lors de la phase de développement, comme le fait que les applications doivent être hors ligne pendant 6 heures sur une période de 24 heures.
Enfin, il est possible de synchroniser heroku et un dépôt github, permettant de redéployer l'application à chaque fois que du code est poussé sur le dépôt.


Spécifications fonctionnelles
-----------------------------

###





