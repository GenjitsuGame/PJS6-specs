
# Proposition de PJS6 : Discord MMO

Participants
----------------
- Auteur : Pascal LUTTGENS,_<<pascal.luttgens@hotmail.fr>>_
- Tuteur : Mourad OUZIRI,_<<mourad.ouziri@parisdescartes.fr>>_


----------


Enoncé du sujet
-----------
###Ce qui devra être réalisé

Le projet consiste à réaliser un jeu massivement multijoueur en ligne pour les utilisateurs du logiciel de communication [discord](https://discordapp.com/). Les utilisateurs interagiront donc avec une application que je vais programmer, un [bot (sens 2)](http://www.linternaute.com/dictionnaire/fr/definition/bot/) dont le but est d'interpréter les entrées utilisateur et d'effectuer des requêtes sur le serveur de jeu.

Le jeu en lui-même consiste a faire évoluer son personnage au travers de combats tour par tour contre l'intelligence artificielle ou contre d'autres joueurs, le but étant d'être capable de finir par battre les adversaires les plus dur du jeu (de nouveaux adversaires pourront êtres rajouté par ajouter de la progression).

Un nombre de bot illimité pourra être mit en place pour interpréter les messages des utilisateurs mais ceux-ci devront être authentifiés auprès du serveur de jeu pour pouvoir effectuer des requêtes. Ceci implique qu'il faudra créer un moyen d'authentifier les clients.

La partie cliente sera [open source](https://github.com/GenjitsuGame/bot-mmo-client) mais pour des raisons de sécurité, la partie serveur restera privée et sera remise via un git privé à la fin du projet.

###Extensions envisagées

- Mettre en place des contrôles sur les opérations fonctionnelles côtés serveur pour vérifier leur légitimité (contrôle anti-triche) et permettre ainsi à quiconque le désirerait d'utiliser son propre client.

- Mettre en place un système d'intégration continue qui permette d'accepter ou de rejeter des contributions si elles ne passent pas les tests ou les règles de codage définies

- Enrichir le site internet permettant aux utilisateurs de créer leur propre API avec des informations sur le jeu ou autres idées qui me viendraient par la suite.

- Contribuer à [Discord.io](https://github.com/izy521/discord.io), la bibliothèque que j'utilise pour utiliser les webservices de discord, j'ai déjà ouvert une [pull request](https://github.com/izy521/discord.io/pull/36) pour fixer un bug que j'ai rencontré mais je compte essayer d'y ajouter de nouvelles features si l'occasion se présente et ainsi contribuer pour la première fois à un projet open source.

- Utiliser des thniques permettant d'avoir une base de donnée dite évolutive (ou "scalable").

### Les difficultés potentielles

- Arriver à construire et maintenir une architecture qui permette de contribuer facilement au projet (Patterns de développement, documentation, tests...)

- Déployer l'application en ligne de manière à ce qu'elle soit utilisable par tous.

- Ecrire une application gérant un grand nombre de traitements concurrents.

- Définir des interactions fluides entre le bot et l'utilisateur de manière à ce que l'aspect "texte" du jeu ne paraissent pas ennuyeux.

- Sécuriser l'applications à tous les niveaux possible (clés d'api + secret pour les webservices, gestions des comptes des utilisateurs de l'api...).

- Faire en sorte que les utilisateurs de discord joue à mon jeu.

- Garder la liste des dépendances à jour et savoir réagir lors des mises à jour des webservices de Discord ou de Discord.io, ceux-ci étant toujours en développement et étant donc relativement instables.

###Lien avec le projet professionnel

Les applications développées dans les cadre de ce projet seront écrite avec [nodejs](https://nodejs.org/en/) qui est une technologie très à la mode pour développer des serveurs exposant des webservices, car il est naturellement très rapide et permet de traiter un grand nombre de requête simultanément à condition de respecter certaines règles. A côté de cela, je compte me servir du site web que je vais développer pour apprendre [un nouveau framework css différent de bootstrap](http://foundation.zurb.com/) et [une nouvelle bibliothèque javascript](https://facebook.github.io/react/) qui viendra completer les compétences que j'ai acquises côté front-end notamment grâce au framework [angularJS](https://angularjs.org/).

 J'envisage pendant les grandes vacances et pendant les années à venir (probablement en école d'ingénieur en alternance) de travailler dans le web et d'être en mesure d'utiliser ou apprendre facilement les technologies actuellement recherchées en entreprise. Ce projet est donc une opportunité parfaite pour y arriver. De plus, si il est réussi, il pourra me servir comme support afin d'attester mes compétences lors d'entretiens ou autre.


Cahier des charges
------------------

[lien vers le cahier des charges]

Logiciels et matériel nécessaire au développement
-------------------------------------------------------------

- [Node.js](https://nodejs.org/en/)

- [mongoDB](https://www.mongodb.org/)

- [Discord](https://discordapp.com)


> Written with [StackEdit](https://stackedit.io/).