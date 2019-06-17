# Entraînement checkpoint 3

Le checkpoint 3 vise à valider les compétences sur Node.js / Express.

Pour te lancer, clone ce repo puis crée une branche au format `ville_nom_prenom`, que tu pousseras après chaque commit.

Essaie au maximum d'écrire les choses par toi-même. Tu peux très bien reprendre du code (des quêtes, projets, etc.) mais évite le copier-coller direct, afin de t'habituer à écrire tout ce qui est nécessaire.

Tu pourras tester tes routes avec Postman.

## Quiz

Quelques questions :
* Que signifie CRUD ?
* À quelle type de requête SQL est associée chaque lettre de l'acronyme CRUD ?
* Dans Express, quelles sont les différentes façons de récupérer des données de la requête ?
  * `req.data`
  * `req.params`
  * `req.query`
  * `req.info`
  * `req.body`
* Dans Express, comment récupérer des paramètres passés dans l'URL comme `?topic=JavaScript&title=React` ?
* Dans Express, quelle est la ligne, juste après l'initialisation de l'app, qui permet de pouvoir récupérer des données JSON dans `req.body` ?
* Comment envoyer un code statut HTTP autre que 200 avec Express ? (deux réponses possibles)
  * `res.status(code)`
  * `res.httpStatus(code)`
  * `res.withCode(code)`
  * `res.sendStatus(code)`

## Etape 1 - Mise en place

Initialise une application Express. Il faut créer un `package.json` puis installer les dépendances :
* Express
* Body parser
* MySQL

Crée ensuite l'application, que tu pourras appeler `server.js`. Tu auras besoin de mettre en place la connexion à MySQL, ce que tu pourras faire dans un fichier dédié, qui sera importé depuis les fichiers qui mettent place les routes.

> N'oublie pas que les dépendances de l'app ne **doivent pas être commitées !**

## Etape 2 - Modéliser la base de données

Cette étape ne sera pas présente dans le checkpoint (le modèle de BDD sera fourni).

Modélise d'abord sur papier si tu préfères, et sinon dans MySQL, une base de données permettant de gérer un simple site d'e-commerce. Elle devra permettre de gérer :
* Les catégories, chaque catégorie ayant un nom
* Les produits, chaque produit ayant :
  * un nom
  * un slug : son nom converti en "URL-friendly", par exemple "Lenovo ThinkPad T430 SSD 240Go" deviendra `lenovo-thinkpad-t430-ssd-240go`.
  * une description
  * un prix
  * une image

Il faudra faire le lien entre un produit et une catégorie (chaque produit ne pourra appartenir qu'à une catégorie)

## Etape 3 - Créer les routes

Tu devras créer les routes suivantes :

* Catégories
  * Création d'une nouvelle catégorie
  * Lecture de toutes les catégories
* Produits
  * Création d'un produit (en lui associant une catégorie)
  * Mise à jour d'un produit (y compris association à une nouvelle catégorie en fournissant l'id de celle-ci).
  * Lecture d'un produit
  * Lecture de tous les produits

Organise ces routes avec un routeur Express.

## Etape 4 - Bonus

Tu peux ajouter les routes suivantes :
* Catégories
  * Mise à jour d'une catégorie
  * Effacement d'une catégorie
* Produits
  * Sur les routes de création et de mise à jour d'un produit, faire en sorte que son `slug` soit mis à jour automatiquement, en le calculant à partir du titre (possibilité d'utiliser un module comme [slugify](https://www.npmjs.com/package/slugify))
  * Effacement d'un produit
  * Ajouter à la route de lecture de tous les produits la possibilité de la filtrer par catégorie (en passant l'id de celle-ci dans l'URL).
