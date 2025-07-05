# Projet de Gestion de Bibliothèque Universitaire

Ce projet est une plateforme web de gestion de bibliothèque universitaire développée avec Node.js (Express.js) pour le backend, Next.js pour le frontend, et MySQL comme base de données relationnelle. Il vise à permettre aux étudiants et aux administrateurs de gérer efficacement les emprunts, les réservations et le catalogue de livres.

## Objectifs principaux

* Permettre aux étudiants :

  * De consulter le catalogue des livres
  * D'effectuer des recherches avancées (titre, auteur, genre)
  * De réserver et emprunter des livres
  * De laisser des notes et commentaires sur les livres

* Fournir aux administrateurs :

  * Un tableau de bord de gestion
  * La gestion des utilisateurs, livres, catégories et auteurs
  * Le suivi des emprunts, retours et retards
  * L'envoi automatique de notifications par email

## Architecture technique

* **Frontend :** Next.js 14 avec TypeScript, TailwindCSS pour le style
* **Backend :** Express.js (Node.js)
* **Base de données :** MySQL 8
* **Authentification :** JWT
* **Emails :** Nodemailer
* **Déploiement local :** Docker Compose (optionnel)

---

## Structure du projet

```
/backend          # API RESTful Express.js
  ├— src
  │   ├— controllers     # Contrôleurs (logique metier)
  │   ├— models          # Modèles de la base de données
  │   ├— routes          # Routes Express.js
  │   ├— services        # Services auxiliaires (email, auth, notifications)
  │   ├— middleware      # Middlewares (auth, validation)
  │   ├— config          # Configuration (DB, JWT)
  │   ├— utils           # Fonctions utilitaires
  └— server.js         # Point d'entrée serveur

/front            # Interface utilisateur Next.js
  ├— app             # Pages et layout
  ├— components      # Composants réutilisables
  ├— services        # Appels API centralisés
  ├— types           # Types TypeScript globaux
  ├— utils           # Fonctions utilitaires frontend
  ├— styles          # Styles CSS globaux
```

---

## Installation

### Prérequis

* Node.js 18+
* MySQL 8+
* npm ou yarn

### Backend

```bash
cd Backend
cp .env.example .env
npm install
npm run dev
```

La base de données MySQL doit être configurée selon le fichier `.env`. Tu peux exécuter les scripts SQL de création et de peuplement des tables.

### Frontend

```bash
cd Front
npm install
npm run dev
```

## Fonctionnalités principales

### Pour les étudiants

* Création de compte, connexion, gestion du profil
* Consultation du catalogue et des détails des livres
* Réservation d'ouvrages disponibles
* Emprunt et historique des emprunts
* Ajout d'avis et de notes sur les livres

### Pour les administrateurs

* Gestion complète du catalogue (ajout, modification, suppression)
* Gestion des catégories et des auteurs
* Suivi et gestion des emprunts et réservations
* Visualisation des utilisateurs
* Notifications par email aux utilisateurs en retard

## Base de données

La base suit une structure relationnelle classique avec les tables suivantes :

* **users** : étudiants, administrateurs, bibliothécaires
* **books** : livres du catalogue
* **categories** : catégories de livres
* **authors** : auteurs
* **book\_authors** : table de liaison many-to-many
* **reservations** : réservations d'ouvrages
* **loans** : emprunts
* **reviews** : avis/commentaires des utilisateurs
* **notifications** : notifications email
* **activity\_logs**, **system\_settings** : pour l'administration

Les scripts SQL d'initialisation sont disponibles dans `/backend/database/migrations/`.


