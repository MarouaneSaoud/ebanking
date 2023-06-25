# Compte Rendu📫
# E-banking app

## Author

- [Saoud Marouane ](https://www.github.com/MarouaneSaoud)

## Plan
- Le contexte generale de l'application
- Architecture du Projet 
- Quelque API consommer
- Interface Graphique

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

## Architecture du Projet

#### Post

```http
  POST /accounts/credit
```

| Parameter          | Type   | Description                                    |
|:-------------------|:-------|:-----------------------------------------------|
| `banque_operation` | `post` | **Required** effectuer une opération de crédit |

```http
  POST /accounts/debit
```

| Parameter          | Type   | Description                                   |
|:-------------------|:-------|:----------------------------------------------|
| `banque_operation` | `post` | **Required** effectuer une opération de debit |

```http
  POST /accounts/transfer
```

| Parameter          | Type   | Description                                      |
|:-------------------|:-------|:-------------------------------------------------|
| `banque_operation` | `post` | **Required** effectuer une opération de transfer |
```http
  POST /accounts/saveSavingAccount
```

| Parameter      | Type   | Description                            |
|:---------------|:-------|:---------------------------------------|
| `bank_account` | `post` | **Required** ajouter un compte epargne |

```http
  POST /accounts/saveCurrentAccount
```

| Parameter      | Type   | Description                             |
|:---------------|:-------|:----------------------------------------|
| `bank_account` | `post` | **Required** ajouter un compte courrant |

```http
  POST /customers
```

| Parameter  | Type   | Description                    |
|:-----------|:-------|:-------------------------------|
| `customer` | `post` | **Required** ajouter un client |

#### Get item

```http
  GET /accounts/{accountId}/pageOperations
```

| Parameter | Type  | Description                                                |
| :-------- |:------|:-----------------------------------------------------------|
| `iaccountId`      | `get` | **Required**. afficher la liste des operations d'un compte |

```http
  GET customer/accounts/{customerId}
```

| Parameter | Type  | Description                                             |
| :-------- |:------|:--------------------------------------------------------|
| `iaccountId`      | `get` | **Required**. afficher la liste des comptes d'un client |

```http
  GET customers/search?keyword=
```

| Parameter | Type  | Description                                           |
|:----------|:------|:------------------------------------------------------|
| `keyword` | `get` | **Required**. chercher un client par un mot clé (nom) |

#### Delete item

```http
  Delete customers/{id}
```

| Parameter | Type  | Description                                           |
|:----------|:------|:------------------------------------------------------|
| `id`      | `delete` | **Required**. supprimer un client par son identifient |

## Interface Graphique

#### L'interface de recherche et d'affichage des clients dans notre application e-banking offre aux administrateurs la possibilité de trouver facilement les informations relatives à un client spécifique. Elle présente une mise en page claire et conviviale, avec un champ de recherche permettant aux utilisateurs de saisir le nom client.
![App Screenshot](/image/customers.png)
#### L'interface d'ajout d'un client dans notre application e-banking est conçue pour permettre aux utilisateurs de saisir facilement les informations nécessaires pour créer un nouveau compte client. L'interface présente un formulaire clair et intuitif, divisé en différents champs pour recueillir les détails pertinents du client.
![App Screenshot](/image/new-customer.png)
#### L'interface des opérations bancaires dans notre application e-banking permet aux utilisateurs de visualiser les opérations associées à un compte spécifique, tout en offrant des fonctionnalités pour effectuer de nouvelles opérations.
#### L'interface présente une liste d'opérations affichant les détails essentiels tels que la date, le type d'opération (débit, crédit ou transfert) et le montant de chaque opération. Pour faciliter la gestion des opérations, l'interface propose également une pagination pour diviser les résultats en plusieurs pages. Cela permet aux utilisateurs de naviguer facilement entre les différentes pages d'opérations, en particulier si le compte a un grand nombre d'opérations.
![App Screenshot](/image/account-operations.png)
#### L'interface "Customer Accounts" dans notre application e-banking permet aux utilisateurs de visualiser la liste des comptes associés à un client spécifique, tout en offrant une fonctionnalité de pagination pour faciliter la navigation.
#### L'interface présente une liste clairement organisée des comptes du client, affichant des informations telles que le type de compte (compte d'épargne, compte courant, etc.), le numéro de compte, le solde actuel et d'autres détails pertinents. Pour éviter de surcharger l'écran avec un grand nombre de comptes, l'interface utilise la pagination, ce qui signifie que seules un certain nombre de comptes sont affichés à la fois. Les utilisateurs peuvent naviguer entre les différentes pages de comptes en utilisant des boutons de pagination ou en saisissant directement le numéro de page souhaité.
![App Screenshot](/image/customers.png)
#### La page "New Account" dans notre application e-banking permet aux utilisateurs de créer un nouveau compte bancaire pour un client existant en fournissant les informations nécessaires.
#### L'interface de la page "New Account" présente un formulaire clair et intuitif avec des champs à remplir pour collecter les détails du nouveau compte. Les champs peuvent inclure des informations telles que le type de compte (compte d'épargne, compte courant, etc.), le solde initial, les options de découvert autorisé (le cas échéant), et d'autres paramètres spécifiques au compte.
![App Screenshot](/image)
