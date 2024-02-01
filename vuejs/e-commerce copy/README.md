# E-COMMERCE : L'APPLICATION POUR LE E-COMMERCE

** BRIEF CLIENT **
Dans le cadre du développement de ses Activités la société Oulalala, spécialiste du [définir] souhaite mettre en place un site e-commerce moderne et dynamique.

该应用程序是为希望建立电子商务系统来管理 其库存 和 订单 的在线销售公司设计的。
L’application est destinée à une entreprise de vente en ligne qui souhaite mettre en place un système e-commerce pour gérer ses stocks et les commandes.

管理员可以添加、修改或删除产品。
他们还可以为产品添加、修改或删除类别。
必须能够搜索产品或类别(搜索引擎)
Les Administrateur peuvent ajouter, modifier ou supprimer des produits.
Ils peuvent également ajouter, modifier ou supprimer des catégories pour les produits.
Il doit être possible de rechercher des produits ou des catégories (moteur de recherche)

Les utilisateurs publiques :

- Doivent être en mesure de consulter les différents produits.
- Doivent être en mesure de rechercher les différents produits.(moteur de recherche).
- La plateforme doit permettre aux clients de se connecter et de s’inscrire. (simulé par le store app)
  公众用户: -必须能够咨询不同的产品。-必须能够搜索不同的产品。(搜索引擎)。
  —平台必须允许客户登录和注册。(由store app模拟)

Les utilisateurs connectés :

- Une fois qu’ils sont connectés, ils ont accès à la fonctionnalité "panier" et peuvent ajouter des produits à ce panier.
- Doivent être en mesure d’ajouter un produit à leur panier.
- Lorsqu’un utilisateur a ajouté un produit au panier, il devrait pouvoir le retirer.
- Peut passer une commande directement depuis son panier.
- Ont accès à leurs commandes passées
  已连接用户: 一旦连接，他们可以访问“购物车”功能，并可以添加产品到这个购物车。-必须能够添加产品到他们的购物车。-当用户将产品添加到购物车时，他应该能够删除它。-可以直接从购物车下订单。-可以访问他们过去的订单

** GESTION DE PROJET **

- Cahier des Charges
  - Définition Générale du Projet
  - Définir l'Arborescence
  - Définir la Liste des Fonctionnalités
  - Définir l'Architecture de l'application
- Gestion des Tâches
  - Définir les Tâches
  - Prioriser les Tâches
  - Suivre les Tâches
- Versionning et Développement
- Utilisation d'un Système de versionnement (Git)
  - Création d'une branche pour chaque fonctionnalité
    - Ajout/Modification/Suppression d'un élément dans une branche
  - Fusionner les branches sur la branche "dev" lorsque cela est possible sans conflit
  - Après vérification de la conformité, fusion de la branche "dev" sur la branche "main"
  - Utiliser un système de tags pour marquer des versions importantes ou releases
- Documentation technique
  - Le code doit être commenté au maximum, avec des explications claires et précises.
  - Un README.md doit décrire le projet, ses objectifs, son architecture, etc.
  - Maintenir la documentation à jour
- Tests unitaires et intégration
  - La liste des tests doit être fournie en même temps que les spécifications fonctionnelles correspondantes.
  - Les tests doivent couvrir toutes les parties du code
- Assurance qualité
  - Code Review: un développeur non expert examine le code d'un collègue
  - Revue par pairs: deux développeurs experts examinent le code d'un troisième développeur

** ARBORESCENCE DES DIRECTOIRES ET FILES **

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Compile and Minify for Production

```sh
npm run build
```

### Run Unit Tests with [Vitest](https://vitest.dev/)

```sh
npm run test:unit
```

### Run End-to-End Tests with [Cypress](https://www.cypress.io/)

```sh
npm run test:e2e:dev
```

This runs the end-to-end tests against the Vite development server.
It is much faster than the production build.

But it's still recommended to test the production build with `test:e2e` before deploying (e.g. in CI environments):

```sh
npm run build
npm run test:e2e
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```

### Raccourcis Utiles

@/ est un raccourcis vers le dossier ./src

#/ est un raccourcis vers le dossier ./src/components

Grace au fichier d'indexation index.js à la racine du dossier src/components/ il est désormais possible d'importer un composant directement comme l'eexemple suivant:

```sh
import {MyComponent} from '@/components'
```

```sh
import {MyComponent} from '#'
```

Grace au fichier d'indexation index.js à la racine du dossier src/stores/ il est désormais possible d'importer un store directement comme l'exemple suivant:

```sh
import {useMyStoreStore} from '@/stores'
```
