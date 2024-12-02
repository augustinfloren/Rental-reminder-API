# Rental Reminder API

## Description

Cette API permet de gérer les rappels pour les locations de films. Elle est conçue pour envoyer des notifications par email aux clients à J-5 et J-3 avant la date de retour de leurs locations. Le système de tâches planifiées permet de s'assurer que les notifications sont envoyées au bon moment, en tenant compte des fuseaux horaires des clients.

## Fonctionnalités

- **Gestion des clients** : Ajouter, modifier, et lister les clients.
- **Gestion des locations** : Créer et gérer les locations de films.
- **Tâches planifiées** : Envoi d'emails de rappel à J-5 et J-3 avant la date de retour de chaque location.
- **API d'administration** : Lancer, lister et vérifier l'état des tâches planifiées manuellement.

## Prérequis

- PostgreSQL avec la base de données **Sakila** (disponible [ici](https://github.com/jOOQ/sakila/tree/main/postgres-sakila-db)).
- Node.js et NPM installés.

## Installation

1. Clonez ce dépôt :
    ```bash
    git clone https://github.com/votre-utilisateur/rental-reminder-api.git
    ```

2. Accédez au répertoire du projet :
    ```bash
    cd rental-reminder-api
    ```

3. Installez les dépendances :
    ```bash
    npm install
    ```

4. Configurez votre base de données PostgreSQL avec le schéma Sakila et les données.
   - Modifiez le fichier `ormconfig.json` ou la configuration de votre base de données pour vous connecter à PostgreSQL.

5. Lancez l'application :
    ```bash
    npm run start
    ```

6. La tâche planifiée s'exécutera selon la configuration et enverra des notifications par email à J-5 et J-3 avant la date de retour.

## Utilisation

L'API expose plusieurs points de terminaison pour gérer les clients, les locations, et les tâches planifiées :

- **POST /customers** : Crée un nouveau client.
- **PUT /customers/:id** : Met à jour un client existant.
- **POST /rentals** : Effectue une nouvelle location.
- **GET /rentals** : Liste toutes les locations.
- **GET /tasks** : Liste toutes les tâches planifiées.
- **POST /tasks/run** : Lance une tâche planifiée manuellement.

## Tâches Planifiées

Le service utilise le package `@nestjs/schedule` pour gérer les tâches planifiées. Deux tâches principales sont configurées pour envoyer des rappels par email à :

- **J-5 à 12h00**
- **J-3 à 12h00**

## Technologies

- **Backend** : Node.js, NestJS
- **Base de données** : PostgreSQL, TypeORM
- **Gestion des tâches planifiées** : @nestjs/schedule
- **Envoi d'emails** : Simulé avec des logs pour cet exercice
- **Tests** : Jest

## Contribuer

Les contributions sont les bienvenues ! Pour soumettre une amélioration ou un bug :

1. Forkez le projet.
2. Créez une branche pour votre fonctionnalité (`git checkout -b feature/ma-fonctionnalite`).
3. Commitez vos changements (`git commit -am 'Ajout d'une nouvelle fonctionnalité'`).
4. Poussez la branche (`git push origin feature/ma-fonctionnalite`).
5. Ouvrez une pull request.

## Licence

Ce projet est sous licence MIT - voir le fichier [LICENSE](LICENSE) pour plus de détails.
