# Compte Rendu📫
# E-banking app

## Author

- [Saoud Marouane ](https://www.github.com/MarouaneSaoud)

## Plan
- Le contexte generale de l'application
- Architecture du Projet 

## Le contexte generale de l'application
 Notre application permet aux administrateurs de gérer les comptes bancaires en ligne de manière pratique et sécurisée. En utilisant une combinaison de technologies telles que Spring MVC pour le backend et Angular pour le frontend, nous avons mis en place une architecture multicouche bien structurée. Du côté backend, nous avons développé des fonctionnalités telles que la création de nouveaux clients, l'ouverture de différents types de comptes bancaires tels que les comptes d'épargne et les comptes courants, ainsi que la gestion des opérations financières telles que le débit, le crédit et le transfert d'argent entre les comptes, etc ... Du côté frontend, nous avons créé une interface utilisateur conviviale avec Angular, offrant aux administrateurs une expérience intuitive pour rechercher des clients, afficher les informations des comptes et effectuer des opérations financières. On a travaillé pour concevoir, développer et tester chaque fonctionnalité, en nous assurant de fournir une application e-banking complète et fiable.

## Architecture du Projet
Architecture du Backend :
Dans notre application Spring MVC, on a utilisé une architecture multicouche courante pour le backend. Voici les principales couches de notre architecture :

#### Couche de Présentation (Presentation Layer) : Cette couche est responsable de la gestion des requêtes HTTP entrantes et des réponses sortantes. Dans votre cas, vous avez utilisé des contrôleurs REST pour gérer les requêtes provenant du frontend et renvoyer les réponses appropriées. Les contrôleurs REST sont responsables de la coordination entre les couches inférieures et supérieures.

#### Couche de Service (Service Layer) : La couche de service contient la logique métier de votre application. Elle traite les requêtes reçues des contrôleurs REST, effectue les opérations nécessaires, utilise les entités et les DTO pour gérer les données et retourne les résultats aux contrôleurs.

#### Couche d'Accès aux Données (Data Access Layer) : Cette couche est responsable de l'accès aux données persistantes, généralement une base de données. Vous avez utilisé des repositories pour interagir avec la base de données. Les repositories fournissent des méthodes pour effectuer des opérations CRUD (Create, Read, Update, Delete) sur les entités de votre application.

#### Couche de Mappage (Mapping Layer) : Cette couche est utilisée pour la conversion des objets entre les entités et les DTO. Vous pouvez utiliser des bibliothèques de mappage telles que ModelMapper ou MapStruct pour faciliter cette conversion.

Architecture du Frontend :
Dans notre application Angular, On a également utilisé une architecture courante pour le frontend. Voici les principaux éléments de l'architecture :

#### Components : Les composants sont les blocs de construction de votre interface utilisateur. Chaque composant représente une partie de l'interface et contient la logique pour interagir avec les utilisateurs.

#### Services : Les services sont responsables de la gestion de la logique métier côté client. Ils communiquent avec le backend pour récupérer les données et effectuer des opérations via des appels HTTP.

#### Templates et Directives : Les templates Angular définissent la structure de votre interface utilisateur. Ils utilisent des directives pour ajouter des fonctionnalités et interagir avec les composants.

#### Routing : Angular propose un mécanisme de routage pour gérer la navigation entre les différentes pages et vues de votre application.

#### HTTP : Angular fournit un module HTTP pour effectuer des requêtes HTTP vers le backend et récupérer les données nécessaires.

En combinant ces éléments, vous créez une interface utilisateur interactive et réactive qui communique avec le backend pour récupérer les données et effectuer des opérations.



