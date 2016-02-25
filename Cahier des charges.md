# Cahier des charges

Introduction
-------------

Ce document a pour but de présenter le projet, ses objectifs et ses contraintes, de donner une description précise de ses fonctionnalités ainsi que de son architecture et enfin de son déroulement.

Le choix du sujet étant libre, il n'y a aucune contrainte technique imposée. Cependant, ce projet utilise [discord](https://discordapp.com) et si ce service venait à être indisponible, il serait alors impossible de mener à bien le projet.

### Concept

Ce projet a pour but de créer un jeu massivement multijoueur destinés aux utilisateurs de Discord, une plateforme de communication. Il s'agit de mettre en place une architecture permettant à des centaines voir milliers d'utilisateurs de jouer en même temps via l'interface de discord, de rendre possible aux utilisateurs qui le désire d'héberger leur propre client afin de permettre la customisation et de réduire nos coûts d'hébergement et enfin, d'exposer une API permettant d'obtenir des données sur le jeu.

----------

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


### [MongoDB](https://www.mongodb.org/)

MongoDB est une base de données "NoSQL". Il n'y a donc pas besoin de définir le schéma des tables et cette fléxibilité permet d'accélérer le développement lorsque l'on suit comme moi un modèle itératif.
De plus, MongoDB utilise un système d'index le rendant très performant lorsqu'il s'agit de faire des requêtes sur un grand nombre de lignes.

### [Foundation 6](http://foundation.zurb.com/)
 
Foundation est une famille de framework front-end qui facilitent la création et le design de site internet "responsive".

Spécifications
--------------

Les spécifications entre paranthèses sont uniquement envisagé à ce stade.
Les spécifications barrées ont déjà été réalisées avant le début officielle de ce projet.

### Le jeu

L'utilisateur pourra :

- Interaction avec le client
    - effectuer des actions via des commandes tapées dans le chat de discord.
    - annuler à tout moment une action en cours.
    - s'enregistrer sur les serveurs de jeu.

- Gestion des personnages
    - créer/supprimer un ou plusieurs personnages.
    - choisir le nom du personnage.
    - _(renommer son personnage après l'avoir crée.)_
    - choisir la race de son personnage.
    - choisir la classe de son personnage.
    - selectionner un de ses personnages pour jouer.

- Combat
    - se battre contre l'intelligence artificielle.
    - se battre contre d'autres joueurs.
    - _(se battre en équipe avec l'intelligence artificielle.)_
    - se battre en équipe avec d'autres joueurs.
    - choisir l'action qu'il désire effectuer via un menu contextuel au début de son tour.
    - gagner des objets à équiper ou permettant de fabriquer/améliorer de l'équipement.

- Social
    - ajouter/supprimer des amis de sa liste d'amis.
    - créer/rejoindre/quitter une guilde.

- Commerce 
    - acheter/échanger/vendre des objets du jeu.
    - utiliser des salons discord dédié au commerce du jeu.

- Métiers
    - apprendre un _(ou 2)_ métiers permettant d'aider sa progression dans le jeu.
    - fabriquer des objets qui pourront ensuite être utilisés ou revendus.

### Le client

Le client du jeu est un utilisateur automatisé de discord qui interprete et transmet les commandes des utilisateurs aux serveurs de jeu.

Il devra :

- être connecté à Discord afin de recevoir les messages des utilisateurs (voir : [Discord.io](https://github.com/izy521/discord.io)
- être paramétrable via un fichier de configuration.
- gérer les erreurs gracieusement.
- pouvoir afficher la liste des commandes et ce qu'elles font.
- gérer la limite imposée par Discord de _X_ messages par _X_ secondes.
- êffectuer des requêtes sur le serveur de jeu.
- permettre au joueur d'effectuer l'ensemble des fonctionnalités décrites dans les spécification du [jeu](#le jeu).

L'utilisateur du client pourra :

- _(obtenir une clé d'API et un secret nécessaire pour effectuer des requêtes sur le serveur.)_
 
### Le serveur de jeu

Le serveur de jeu contiendra la logique du jeu et exposera deux APIs :

- une API fonctionnelle afin de pouvoir effectuer des opérations sur le jeu.
- une API de donnée afin de pouvoir récupérer divers informations sur le jeu.

Ces deux APIs seront représentées par des scopes et leur accès nécessitera une clé d'api qui sera associé à un des deux scopes voir les deux en même temps.

Le serveur devra donc :

- pouvoir distribuer des clés d'API associés à un ou plusieurs scopes.
- être en mesure d'identifier les clients effectuant des appels d'API
- retourner des données au format JSON.
- implémenter la logique du jeu décrite dans les spécifications [mentionnées plus haut](#le jeu).

### Le "Master Bot"

Le master bot est une application utilisant, tout comme la partie cliente, la bibliothèque [Discord.io](https://github.com/izy521/discord.io) dans le but d'aider à la gestion du serveur Discord du jeu et de sa communauté.
Ce serveur a pour but d'informer la communauté du développement du jeu, des mises à jour mais aussi d'y organiser la partie commerce et sociale du jeu. ![](http://puu.sh/njNH0/554737e401.png)

Il devra :

- tenir informé les contributeurs de l'activité des dépots github des applications en open source.
- permettre de communiquer aux utilisateurs les annonces concernant le jeu.
- organiser les salons de commerce
- organiser les salons de recrutement et de recherche de groupe.

### Le site internet

Un site internet permettra d'obtenir les tokens nécessaires à l'utilisation de l'API.

Si le temps le permet, ce site proposera également d'autres fonctionnalités.

Le site devra :

- proposer un système d'authentification.
- permettre à l'utilisateur d'enregistrer une application pour laquelle il obtiendra une clé d'API et un secret.
- permettre à l'utilisateur de consulter la liste de ses applications enregistrée.
- permettre à l'utilisateur de renouveler ses tokens en fonctions des scopes désirés.
- _(proposer un forum.)_
- _(permettre de consulter la base de donnée du jeu.)_
- _(contenir un blog de développeur ou je partagerai les connaissances que j'ai apprise.)_


#### Remarque

Il est possible que des changement d'architectures soient efféctués si je change d'avis sur la façon de réaliser les spécifications décrites plus ci-dessus.

Aussi, dans la mesure du possible, un maximum de tests devront être réaliser afin de pouvoir certifié la qualité du produit et de facilité la contribution de la part d'autres utilisateurs.

-------------

Développement
-------------

La méthode de gestion de projet choisie sera inspirée des méthodes agiles.

Après avoir défini un ensemble de features à délivrer et les sous tâches les composants, celles-ci seront réparties sur plusieurs sprints de 1 semaines chacun qui me permettront d'évaluer ma vélocité et le travail qu'il me reste à faire.

Dans le cadre de ce projet, j'utiliserai les produits de la compagnie [JetBrains](https://www.jetbrains.com/).

- L'IDE [Webstorm](https://www.jetbrains.com/webstorm/) pour sa maturité et ses plugins permettant d'intégrer les autre outils que j'utilise.
- [YouTrack](https://www.jetbrains.com/youtrack/) pour les outils agiles, gestion du backlog, sprints...
- _([TeamCity](https://www.jetbrains.com/teamcity/) pour l'intégration (vérifier que les tests passent avant que le code soit poussé sur le dépôt, pouvoir faire des builds à partir des dépots et ainsi des releases...))_
- (GitHub)[https://github.com/] pour le versionning des parties open sources du projet.


__Un lien sera rajouté ici vers le youtrack du projet__