# Piiquante-API  - OpenClassrooms P6

Piiquante est un projet développé dans le cadre de la formation OpenClassrooms. 

Ce projet vise à créer une API pour une application web de critique des sauces piquantes appelée "Hot Takes". 

L'application permet aux utilisateurs de télécharger leurs sauces piquantes préférées et de liker ou disliker les sauces partagées par d'autres utilisateurs.


## Scénario

Vous travaillez en tant que développeur back-end indépendant et avez été contacté par la marque de condiments Piiquante pour développer l'API de leur nouvelle application web. 

Le front-end de l'application, développé en Angular, est déjà en place, et votre tâche consiste à créer une API sécurisée pour gérer les sauces, les utilisateurs et les interactions des utilisateurs avec les sauces.

## Technologies utilisées

- **Node.js**
- **Express.js**
- **MongoDB**
- **Mongoose**
- **JSON Web Token (JWT)**
- **BCrypt**

## Fonctionnalités Principales

- **CRUD des Sauces** : Créer, lire, mettre à jour et supprimer des sauces.
- **Authentification des Utilisateurs** : Système de gestion des utilisateurs avec enregistrement et connexion sécurisée.
- **Likes et Dislikes** : Permettre aux utilisateurs de liker ou disliker les sauces.
- **Sécurité Renforcée** : Protection des mots de passe et sécurisation des routes API.

## Installation

### Prérequis

Vous devez avoir **Node** et **npm** installés localement sur votre machine.

### Installation Backend

1. Clonez ce repository.
2. Installez les dépendances :
    ```bash
    npm install
    ```
3. Configurez les variables d'environnement :
    - Créez un fichier .env à la racine du projet.
    - Ajoutez les variables suivantes :
        ```env
        PORT=3000
        DB_URI=<votre_uri_mongodb>
        JWT_SECRET=<votre_secret_jwt>
        ```
4. Démarrez le serveur :
    ```bash
    npm start
    ```

Le serveur devrait fonctionner sur **localhost** avec le port par défaut *3000*.

## API

L'API gère les opérations CRUD pour les sauces, l'authentification des utilisateurs et les interactions (likes/dislikes). 

Voici les détails des **endpoints** disponibles :

### Utilisateurs

#### POST /api/auth/signup

- **Description** : Enregistre un nouvel utilisateur.
- **Corps de la demande** :
    ```json
    {
    "email": "string",
    "password": "string"
    }
    ```
- **Réponse** : Message de succès ou d'erreur.


#### POST /api/auth/login

- **Description** : Connecte un utilisateur.
- **Corps de la demande** :
    ```json
    {
    "email": "string",
    "password": "string"
    }
    ```
- **Réponse** : Token JWT et ID utilisateur.



### Sauces

#### GET /api/sauces

- **Description** : Retourne toutes les sauces.
- **Réponse** : Tableau d'objets sauces.


#### GET /api/sauces/{id}

- **Description** : Retourne une sauce spécifique par son ID.
- **Paramètres** : {**id**} - L'identifiant de la sauce.
- **Réponse** : Objet sauce correspondant à l'ID.


#### POST /api/sauces

- **Description** : Crée une nouvelle sauce.
- **Corps de la demande** : FormData avec les informations de la sauce et l'image.
- **Réponse** : Message de succès ou d'erreur.


#### PUT /api/sauces/{id}

- **Description** : Met à jour une sauce existante.
- **Paramètres** : {**id**} - L'identifiant de la sauce.
- **Corps de la demande** : FormData avec les informations mises à jour de la sauce et l'image.
- **Réponse** : Message de succès ou d'erreur.


#### DELETE /api/sauces/{id}

- **Description** : Supprime une sauce par son ID.
- **Paramètres** : {**id**} - L'identifiant de la sauce.
- **Réponse** : Message de succès ou d'erreur.


#### POST /api/sauces/{id}/like

- **Description** : Like ou dislike une sauce.
- **Paramètres** : {**id**} - L'identifiant de la sauce.
- **Corps de la demande** :
    ```json
    {
    "userId": "string",
    "like": number
    }
    ```
- **Réponse** : Message de succès ou d'erreur.



## Points Forts

- **API Sécurisée** : Utilisation de JWT pour l'authentification et BCrypt pour le hash des mots de passe.
- **Fonctionnalités Complètes** : Gestion complète des sauces avec des opérations CRUD, et système de likes/dislikes.
- **Code Bien Structuré** : Suivi des meilleures pratiques pour un code clair et maintenable.
- **Expérience Utilisateur Optimisée** : Intégration facile avec le front-end Angular pour une expérience utilisateur fluide.
- **Scalabilité** : Conception de l'API pour permettre une future extension en une boutique en ligne.

## Informations

Ce projet est destiné à démontrer mes compétences en développement web et n'est pas destiné à une utilisation commerciale.
